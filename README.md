# chrome-extension

*Learn javaScript while making projects* 
___
This project is as  the repo-name means, Basically a extension on my browser to save a tab just as a bookmark does.

## Add this extension to your browser to see how this works

   1. download this repo in your destop 
   2. go to chrome extensions and `load` this folder (if load option not available turn ON the developer mode)
   3. all set to go

---
### Concepts I came across / used

The first challenge was to store the input data as it keeps getting empty once the page is refreshed.

So, here **local Storage** is used :

to *add* item to local storage we use following syntax
```javascript
    localStorage.setItem("myLeads",myLeads) // myLeads = [url] to be stored as value of  the key myLeads 
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
        // add operation you wanna do here wrt url
    }
```
-  This requires that you request access to the `chrome.tabs` API in your *extension manifest*:
```json
  "permissions": [ 
        "tabs"
    ] 
```

---