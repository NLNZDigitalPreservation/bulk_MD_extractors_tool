# bulk_MD_extractors_tool
Basic framework for throwing a folder of files at a series of metadata extractors, and recording the result

<h2> Set up <\h2>

To use this tool, you must set up any of the extractors you intend to use. 

Tika
https://tika.apache.org/download.html
`path_to_tika = r"C:\tools\tika/tika-app-1.25.jar"`
Point to the jar file.  

FITS
https://projects.iq.harvard.edu/fits/get-started-using-fits
`path_to_fits = r"C:\tools\fits-1.5.0\fits"`
Point to the batch file.

MediaInfo Tool
https://mediaarea.net/en/MediaInfo/Download
Make sure you install the CLI (commandline interface) version 
`path_to_mediainfo = r"C:\tools\mediainfo\MediaInfo.exe"`
Point to the exe file

Exiftool
`path_to_exiftool = r"exiftool"`
Either add the path to the exe to your envirnoment vars (as example), or point to the exe directly.   


You may not want to use all the tools - they're easy to remove from the workflow by commenting out the line that calls them. 

    if not os.path.exists(exiftool_logfile) or os.path.getsize(exiftool_logfile) == 0:
        if not os.path.exists(temp_file_name):
            stage_file(f, temp_file_name)
        do_exiftool(f, exiftool_logfile)

For example, to not use exiftool, replace the above section with:

    # if not os.path.exists(exiftool_logfile) or os.path.getsize(exiftool_logfile) == 0:
        # if not os.path.exists(temp_file_name):
            # stage_file(f, temp_file_name)
        # do_exiftool(f, exiftool_logfile)
