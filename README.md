# chrome-extension

Learn javaScript while making projects 
The first challenge was to store the input data as it keeps getting empty once the page is refreshed.

So, here **local Storage** is used :

to *add* item to local storage we use following syntax
```javascript
    localStorage.setItem("myLeads",myLeads)
```

to *fetch* the data from the local storage
```javascript
    localStorage.getItem("myLeads")
```

`localStorage` only supports *strings*
so we add JSON to go from array to string and other way around
```javascript

    localStorage.setItem("myLeads",JSON.stringify(myLeads))  // to add item(as string) to localStorage 
    JSON.parse(localStorage.getItem("myLeads")) // to fetch the item(as array) from localStorage

```

To Get the **URL** of the current tab from a Google Chrome extension

```javascript
    chrome.tabs.query({active: true, currentWindow: true}, function(tabs){
        myLeads.push(tabs[0].url)
        <!-- add operation you wanna do here  wrt url -->
    }
```
-  This requires that you request access to the `chrome.tabs` API in your extension `manifest`:
```json
  "permissions": [ ...
        "tabs"
    ] 
```

## To use this extension or add more features

   - download this repo to your destop 
   - go to chrome extensions and *load* this folder (if load option not available turn ON the developer mode )
   - all set to go