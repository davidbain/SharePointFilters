# SharePointFilters
A-Z filter buttons for SharePoint

These filter buttons allow you to filter a SharePoint list by item name. For example, selecting A shows all items 
starting with 'A'. They work by modifying the simple SharePoint URL to filter the list, meaning a filtered list is
also shareable via it's page URL. 

The buttons include their own CSS so the way they look (seen below) can be changed easily. Javascript is used to generate the buttons, instead of having a block of code for each letter. 

![image](http://imgur.com/7qU98vp.png)

So far these filter buttons have been tested as working on SharePoint Services 3.0 and above. 

To use these buttons, simply insert them into a web part on the same page as the SharePoint list to filter.

If you want to filter by something other than 'Title', change the filterColumn variable on line 38 to the column name. 

```
38      filterColumn = "Title";
```
