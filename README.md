# foulnames
The best way to automatically rename files with unusual characters in the filename.    
Uses GNU awk to automatically detect which characters are Unicode text, and which characters are odd punctuation or control characters.
      
      use: foulnames [OPTIONS] filename [more filenames...]

      foulnames is a little bash script to remove non-printable characters and control
      characters from filenames
      should run fine on any unix with GNU bash and stuff. 
      options: 
        -m NUM      allow foulnames to fix more than 4 files at a time. This was to prevent 
                    foulnames *.mp3 from fixing 900 files by accident.
        -i      pipe mode from stdin.  should remove all newlines and /.
                naturally the input only comes from a single filename which is piped in.  
                Yes, filenames can have newlines, and this is the solution.
        -t      preview the new filenames, but don't fix filenames


### Usage 

First run a trial run    
    `foulnames -t *`

Then rename every file    
    `foulnames * `

You may find that foulnames prevents you from renaming hundreds of files at once.    
set the limit higher with this option: ` -m 9000 `

Foulnames doesn't remove spaces or (), but it does replace smart quotes with regular quotes, and it replaces Unicode emoji's with '.'     
Foulnames replaces / with \\, but this is only useful in the -i mode.
