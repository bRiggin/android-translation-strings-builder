# android-translation-strings Tool
I wanted to create an easy to use, lightweight tool that performs the difficult bit of creating the required string.xml translation files in an Android project.

This is a Python tool that converts an Android project's strings.xml file into a structured Excel spreadsheet. The spreadsheet can then be populated with translated strings and the Python tool can reverse the process and produce all required strings.xml files.

I hope someone else finds it helpful. 

## Getting Started

Simply download the translation_strings_tool.py file, open a Python terminal and change directories (cd) into the location of the tool.

The tool can be operated in two modes:  
* Deconstruction (-d), where the tool will deconstruct the data within a strings.xml file and structure it into an Excel spreadsheet. 
* Construction (-c), where the tool will create a strings.xml file for each of the Languages that has been included within the Excel file.

The tool is invoked as follows:

```
path/to/tool python translation_strings_tool.py MODE EXCEL_FILE SOURCE_PATH STORAGE_PATH
```

Where:

* MODE - Mode of operation, -d or -c (-h will bring up help information).
* EXCEL_FILE - The file name of the Excel spreadsheet that will be created or is being read from.
* SOURCE_PATH	- The directory of the file being read (Excel file or string.xml file).
* STORAGE_PATH - THe directory where the output file(s) will be stored. This is optional, if not included, output files will be stored at SOURCE_PATH.

Examples:

```
path/to/tool python translation_strings_tool.py -d testSpreadsheet "/Users/Desktop"
```
Will create testSpreadsheet.xlsx and will be stored at /Users/Desktop/testSpreadsheet.xlsx
```
path/to/tool python translation_strings_tool.py -c testSpreadsheet "/Users/Desktop" "/Users/Desktop/stringFiles"
```
Will create language folders at /Users/Desktop/stringFiles from /Users/Desktop/testSpreadsheet.xlsx

### Prerequisites

This tool was developed using Python 3.6.5 and utilises the following non-standard library:

* openpyxl

## Notes

This tool has been designed to handle the following strings.xml elements:

* Strings
* String-arrays
* Plurals

The tool has also be designed to capture string modifiers (\<b>\</b>, \<u>\</u>, etc).

Each constructed strings.xml file will be placed within it's own folder, the title of this folder will be dictated by the column heading for that language within the Excel spreadsheet. 

WARNING - This tool will automatically overwrite files with identical titles.

## License

This project is licensed under the MIT License - see the [LICENSE.md] file for details
