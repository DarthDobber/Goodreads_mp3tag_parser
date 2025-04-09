# Goodreads Mp3tag Parser

## Overview
This updated Goodreads Mp3tag parser has been designed to align closely with the Audible parser's functionality and output format. Due to Goodreads' inconsistent formatting of series information, the parser implements multiple pattern recognition approaches to extract series details accurately. While I can't guarantee perfect extraction for every book title format, my testing hasn't revealed any titles that break the extraction process. 

## Features
- Retrieves comprehensive book metadata from Goodreads
- Properly handles series information (identifies book numbers within a series)
- Creates sorted album titles for proper audiobook organization
- Extracts genres, publisher information, and ratings
- Fetches cover artwork URLs
- Formats titles consistently with author information

## Installation
1. Save this file to your Mp3tag sources folder:
   - Location: `%AppData%\Roaming\Mp3tag\data\sources`
   - Filename: `Goodreads.src`

## Usage
1. Select the audiobook files you want to tag in Mp3tag
2. Click on "Tag Sources" in the toolbar
3. Choose "Goodreads" from the list of sources
4. Enter the book title and/or author in the search field
5. Select the correct book from the search results
6. Review and apply the fetched metadata

## Tag Fields
The parser populates the following tags:
- **ALBUM**: Main book title (without series information)
- **ALBUMARTIST**: Author name
- **ARTIST**: Author name (duplicated for compatibility)
- **TITLE**: Formatted title with series information and author
- **SERIES**: Name of the series (if applicable)
- **SERIES-PART**: Book number within the series
- **YEAR**: Publication year
- **GENRE**: Book genres (separated by " \\ ")
- **RATING**: Goodreads rating
- **PUBLISHER**: Book publisher
- **COMMENT**: Book description
- **COVERURL**: URL to the cover image
- **CONTENTGROUP**: Formatted series information
- **ALBUMSORT**: Properly formatted for sorting (Series Name + Number + Title or Title only for standalone books)
- **WWWAUDIOFILE**: URL of page where results are scrapped.

## Series Handling
The parser intelligently extracts series information from titles with various formats:
- Titles with parentheses: "Book Title (Series Name #1)"
- Titles with commas: "Book Title, Book 1"
- Titles with various numbering styles: "#1", "Book 1", etc.

## Version History
- 2021-02-27: Initial Release by FidoFuz
- 2021-02-28: Miscellaneous Fixes
- 2023-02-27: Updated by SeaNap
- 2025-03-25 Updated by Darthdobber to mirror as best as possible the audible parser

## Troubleshooting
- If debug is enabled, logs will be written to:
  - `C:\Users\%user%\Desktop\goodreads\search_debug.txt`
  - `C:\Users\%user%\Desktop\goodreads\detail_debug.txt`
- To enable debugging or change the log location, uncomment the Debug lines in the script

## Note
This script is designed for personal use only. Please respect Goodreads' terms of service regarding web scraping and automated access.
