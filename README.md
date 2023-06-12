# My-GetLink-Project


## What does this code do?
#### Simply put, this code gets all the links and sublinks from a main URL and downloads them into a specified folder. Then from those links it checks which ones are PDF links and saves those pdfs into a separate specified folder.


## Limitations you should know

1. The first half of the code works for *any* website/url that you want to receive the links & sublinks for. All you have to change is the variable **'url_start'** to the url you want. 
*Changing folder names are optional.*

2. The second half of the code is the section fixated on downloading all the available pdfs from the main url using the list of links from the first half of the code.
The url I have used is unique which means every url that is a pdf contains the string **'showpublisheddocument'**.
Usually most other links that are PDFS would end in '.pdf' but there are still some links that do not use this layout.

This makes the second half of the code specific to the url that I have used: 'https://www.middlesexcountynj.gov/'. 




### How to Fix the PDF Limitation for Other URLs

If you wanted to use part of the code as well for another website/url you would have to change the lambda function that is present in line 89.

The following replacement for line 89 should suffice for most websites/urls 
* pdf_links = soup.find_all('a', href=lambda href: href and href.endswith('.pdf'))


If this change does not work, it means the website/URL you are trying to use is also unique and you must figure out the specific string that is present in each PDF link. 
Then you can simply change the original code on line 89 (not the replacement shown above) and replace **'showpublisheddocument'** with the string that you have found out.
