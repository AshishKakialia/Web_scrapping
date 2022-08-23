# libraries that i used

## selenium web driver
## pandas
## beautiful soup 4
## python language
## amazon links for web scrapping

1. imported all the libraries and installed web driver in the jupyter notebook

2. extract the 100 rows from the amazon_scrapping.xlsx file using pandas 

- data of the file stored in df varable
- using indexing stored the 100 ID, Asin and country stored these columns in different variables

3. for loop and web driver to create and load the link and beautifulsoup works get the content of the link

-used for loop for iterating the values of  Asin and country to complete the url
-with the help of web driver url will load
- with the help of beautiful soup. we can access the content like a traversal tree and parse the content
-check 404 or other errors if links are not working but due to mismatch value in every link 
code was not working smoothly and getting errors then i changed the strategy

4. changed strategy

- the content or tags in the links which are not working, it should be less as compare to the other working links.
- i run the code with soup.find('div') and print the len of the div tag.
- at the result number of div tags were more as compare other 404 error links.

5. program divided in kind of two sections

-one section extrating the content from the working links
- title, price, product details and image url extracted 
- title was easliy extracted with one line code soup.title.string
- price extracted by span tag with three different attributes(different string value of class)  before writing the code checked every tag by inspecting the amazon link and then choose these three tags and create a logic to extract the price and by zipping in the dictionary stored it in the final list(List_of_products). 
-product details extracted by using div tag and id attributes. After that remove unwanted characters. zip the values in the dictionary and stored in final list.
-image url extracted by div tag and img attributes. img attributes are differents in working links so created the logic with if condition and used the command .children to get the access to child tag of the div tag. in the child tag use src value to get the image link.


- second section check the number of div tags in 404 error length is 3 or 5  and length of div tag in working links was showing 0, that's why condition of second section is not equal to zero. so zip that link with 'not available ' string in dictionary and stored in final list.


dumb the final list in json and created the resultant.json file.
