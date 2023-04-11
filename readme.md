<h1  style="text-align: center;">multiSearch Bookmarklet</h1>

<h4  style="text-align: center;"> A browser bookmarklet, that allows to easily search multiple searchengines/websites.</h4>

<br>


<p align="center">
<img src="assets/multiSearch.gif" width="80%" style="margin:0 0 20px 20px">
</p>

<p style="text-align: center; font-weight:bold;" dir="auto">
    <a href="#The/my-issue">The/my issue</a> •
    <a href="#The-bookmarklet">The Bookmarklet</a> •
    <a href="#How-to-use-it">How to use it</a> •
    <a href="#How-to-adjust/customize">How to adjust/customize</a> •
</p>
<br>
<hr>

<br><br>

## The/my issue

Some weeks ago I started to use [duckduckgo.com](https://duckduckgo.com/) as my default search engine, but realized that sometimes the google search results fit more to my needs.

My normal search procedure was to open a new tab, type my query and see the results on [duckduckgo.com](https://duckduckgo.com/). To search again on google I needed to (copy my search query) open a new tab, type the google url and retype the query again or paste it from the clipboard.

I was annoyed and thought about to optimize this "process" to save some clicks.

<br><br>


<img src="assets/multiSearch.gif"  align="right" width="400"  style="margin:0 0 20px 20px">

## The bookmarklet

The bookmarklet, which basically is just a normal boomark in my bookmark bar, allows me to re-search on google (and other pages) with just two clicks. On the  other website its works vice versa. 

When you've searched anything on youtube yuo can just click the bookmarklet and search for the query on any of the other websites with just one click.

<p><br><br><br><br></p>

<br>

## How to use it

1. create new bookmark in your browser
2. give it a name
3. add the following (minifyed) javascript in the URL field (yes, just copy/paste the whole code into the field)
4. click the bookmark on DuckDuckGo, Google, Youtube or Amazon

```javascript
javascript:(()=>{if(!document.getElementById('multisearch')){let searchOptions={Google:['google.com/search?q=%27,%27#1a73e8'],DuckDuckGo:['duckduckgo.com/?q=','#E37151'],Youtube:['youtube.com/search?q=','#f00'],Amazon:['amazon.de/s?k=','#f69b22']};let box=document.createElement('div');box.id='multisearch';document.body.appendChild(box);let style=document.createElement('style');style.innerHTML='#multisearch{width:98%;position:fixed;z-index:9999;left:50%;top:0;transform:translate(-50%, -100%);box-sizing:border-box;padding:10px;display:flex;gap:5px;border-radius:0 0 8px 8px;font-family:Arial,Helvetica,sans-serif;animation:showsearch .3s ease forwards;background-color:rgba(255,255,255,.5);border-left:1px solid rgba(255,255,255,.2);border-right:1px solid rgba(255,255,255,.2);border-bottom:2px solid rgba(255,255,255,.2);-webkit-backdrop-filter:blur(5px);backdrop-filter:blur(5px);box-shadow:0 0 20px -5px rgba(0,0,0,.5)}@keyframes showsearch{100%{transform:translate(-50%, 0)}}#multisearch input{width:220px;margin-left:5px;padding:0 10px 0 10px;box-sizing:border-box;color:#333;border:1px solid #ced4da;background-color:#fff}#multisearch input:focus{border-color:#86b7fe;box-shadow:0 0 0 .25rem rgba(13,110,253,.25);outline:0}#multisearch.error input:focus{border-color:#dc3545;box-shadow:0 0 0 .25rem rgba(220,53,69,.25)}#multisearch span{background-color:rgba(0,0,0,.7490196078);color:#fff;padding:10px 17px 11px 36px;box-sizing:border-box;cursor:pointer;background-repeat:no-repeat;background-position:7px center;background-size:auto 60%}#multisearch input,#multisearch span{border-radius:2px;font-size:14px !important;line-height:1}.Google{background-image:url("data:image/svg+xml;base64,PHN2ZyBpZD0iRWJlbmVfMSIgZGF0YS1uYW1lPSJFYmVuZSAxIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIj48ZGVmcz48c3R5bGU+LmNscy0xe2ZpbGw6IzQyODVmNDt9LmNscy0ye2ZpbGw6IzM0YTg1Mzt9LmNscy0ze2ZpbGw6I2ZiYmMwNTt9LmNscy00e2ZpbGw6I2VhNDMzNTt9PC9zdHlsZT48L2RlZnM+PHBhdGggY2xhc3M9ImNscy0xIiBkPSJNNTAuOTIsNDEuNjVWNTkuNDNINzUuNjNhMjEuMTUsMjEuMTUsMCwwLDEtOS4yMiwxMy44MmwxNC45LDExLjU3QzkwLDc2LjgsOTUsNjUsOTUsNTFhNTMuMDgsNTMuMDgsMCwwLDAtLjgzLTkuMzlaIi8+PHBhdGggY2xhc3M9ImNscy0yIiBkPSJNMjUuMTgsNTguNzRsLTMuMzYsMi41N0w5LjkzLDcwLjU4aDBhNDUuOSw0NS45LDAsMCwwLDQxLDI1LjM0YzEyLjQsMCwyMi43OS00LjA5LDMwLjM5LTExLjExTDY2LjQsNzMuMjVBMjcuNiwyNy42LDAsMCwxLDI1LjIsNTguNzdaIi8+PHBhdGggY2xhc3M9ImNscy0zIiBkPSJNOS45MywyOS40MmE0NS40Miw0NS40MiwwLDAsMCwwLDQxLjE2UzI1LjIsNTguNzIsMjUuMiw1OC43MmEyNi44LDI2LjgsMCwwLDEsMC0xNy40NVoiLz48cGF0aCBjbGFzcz0iY2xzLTQiIGQ9Ik01MC45MiwyMi4zN2EyNSwyNSwwLDAsMSwxNy41Nyw2Ljg0TDgxLjY0LDE2LjA2YTQ0LDQ0LDAsMCwwLTMwLjcyLTEyLDQ1LjgyLDQ1LjgyLDAsMCwwLTQxLDI1LjM0TDI1LjIsNDEuMjhBMjcuNDIsMjcuNDIsMCwwLDEsNTAuOTIsMjIuMzdaIi8+PC9zdmc+")}.Youtube{background-image:url("data:image/svg+xml;base64,PHN2ZyBpZD0iRWJlbmVfMSIgZGF0YS1uYW1lPSJFYmVuZSAxIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIj48ZGVmcz48c3R5bGU+LmNscy0xe2ZpbGw6cmVkO30uY2xzLTJ7ZmlsbDojZmZmO308L3N0eWxlPjwvZGVmcz48cGF0aCBjbGFzcz0iY2xzLTEiIGQ9Ik05NS4wOCwyNi42MmExMS42NCwxMS42NCwwLDAsMC04LjIyLTguMjNjLTcuMjUtMS45NC0zNi4zNC0xLjk0LTM2LjM0LTEuOTRzLTI5LjA4LDAtMzYuMzMsMS45NEExMS42NCwxMS42NCwwLDAsMCw2LDI2LjYyQzQsMzMuODYsNCw0OSw0LDQ5UzQsNjQuMTQsNiw3MS4zOWExMS42NSwxMS42NSwwLDAsMCw4LjIyLDguMjJjNy4yNSwxLjk0LDM2LjMzLDEuOTQsMzYuMzMsMS45NHMyOS4wOSwwLDM2LjM0LTEuOTRhMTEuNjUsMTEuNjUsMCwwLDAsOC4yMi04LjIyQzk3LDY0LjE0LDk3LDQ5LDk3LDQ5Uzk3LDMzLjg2LDk1LjA4LDI2LjYyWiIvPjxwYXRoIGNsYXNzPSJjbHMtMiIgZD0iTTQxLjIxLDYzLDY1LjM4LDQ5bC0yNC4xNy0xNFoiLz48L3N2Zz4=")}.DuckDuckGo{background-image:url("data:image/svg+xml;base64,PHN2ZyBpZD0iRWJlbmVfMSIgZGF0YS1uYW1lPSJFYmVuZSAxIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2aWV3Qm94PSIwIDAgMTAwIDEwMCI+PGRlZnM+PHN0eWxlPi5jbHMtMSwuY2xzLTExe2ZpbGw6bm9uZTt9LmNscy0ye2NsaXAtcGF0aDp1cmwoI2NsaXAtcGF0aCk7fS5jbHMtM3tmaWxsOiNkNWQ3ZDg7fS5jbHMtNHtmaWxsOiNmZmY7fS5jbHMtNXtmaWxsOiMyZDRmOGU7fS5jbHMtNntmaWxsOnVybCgjVW5iZW5hbm50ZXJfVmVybGF1Zl8yKTt9LmNscy03e2ZpbGw6dXJsKCNVbmJlbmFubnRlcl9WZXJsYXVmXzItMik7fS5jbHMtOHtmaWxsOiNmZGQyMGE7fS5jbHMtOXtmaWxsOiM2NWJjNDY7fS5jbHMtMTB7ZmlsbDojNDNhMjQ0O30uY2xzLTExe3N0cm9rZTojZmZmO3N0cm9rZS13aWR0aDo1LjE5cHg7fTwvc3R5bGU+PGNsaXBQYXRoIGlkPSJjbGlwLXBhdGgiPjxjaXJjbGUgY2xhc3M9ImNscy0xIiBjeD0iNTAiIGN5PSI0OS42IiByPSI0NC4wNyIvPjwvY2xpcFBhdGg+PGxpbmVhckdyYWRpZW50IGlkPSJVbmJlbmFubnRlcl9WZXJsYXVmXzIiIHgxPSIxODg2LjY4IiB5MT0iMjQ4Ny43MSIgeDI9IjE4OTMuOTQiIHkyPSIyNDg3LjcxIiBncmFkaWVudFRyYW5zZm9ybT0idHJhbnNsYXRlKC0xODU1LjMzIC0yNDUzLjM2KSIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiPjxzdG9wIG9mZnNldD0iMC4wMSIgc3RvcC1jb2xvcj0iIzYxNzZiOSIvPjxzdG9wIG9mZnNldD0iMC42OSIgc3RvcC1jb2xvcj0iIzM5NGE5ZiIvPjwvbGluZWFyR3JhZGllbnQ+PGxpbmVhckdyYWRpZW50IGlkPSJVbmJlbmFubnRlcl9WZXJsYXVmXzItMiIgeDE9IjE5MDkuNTIiIHkxPSIyNDg1LjUiIHgyPSIxOTE2LjE0IiB5Mj0iMjQ4NS41IiB4bGluazpocmVmPSIjVW5iZW5hbm50ZXJfVmVybGF1Zl8yIi8+PC9kZWZzPjxnIGNsYXNzPSJjbHMtMiI+PHBhdGggY2xhc3M9ImNscy0zIiBkPSJNNTkuNDMsOTVjLTIuMTItNC4xNC00LjE2LTcuOTQtNS40Mi0xMC40Ni0zLjM2LTYuNzItNi43My0xNi4xOS01LjItMjIuMy4yOC0xLjExLTMuMTYtNDEuMTEtNS41OS00Mi40QTUwLjY1LDUwLjY1LDAsMCwwLDMxLjYsMTZjLTIuMTItLjM0LTIuNi4yNS0zLjQ5LjM5Ljg0LjA4LDQuODMsMi4wNSw1LjYsMi4xNi0uNzcuNTMtMy4wNSwwLTQuNTEuNjNhMi45MSwyLjkxLDAsMCwwLTEuMjcsMi4xOGM0LjE1LS40MiwxMC42NSwwLDE0LjQ5LDEuNy0zLjA2LjM1LTcuNy43NC05LjcsMS43OS01LjgsMy4wNS04LjM2LDEwLjE5LTYuODMsMTguNzVzOC4yNCwzOS43MSwxMC4zOCw1MC4xMVM2MywxMDEuOTEsNTkuNDIsOTVaIi8+PHBhdGggY2xhc3M9ImNscy00IiBkPSJNNjIuNTIsOTZjLTIuNTUtNS4wNi01LjE2LTkuOS02LjY2LTEyLjktMy4zNy02LjczLTYuNzItMTYuMi01LjItMjIuMzEuMjktMS4xMS4yOS01LjY1LDEuMjEtNi4yNSw3LjEzLTQuNjYsNi42Mi0uMTYsOS40OS0yLjI1YTcuODksNy44OSwwLDAsMCwzLjE3LTQuMTVjMS44My02LjQyLTIuNTUtMTcuNi03LjQ1LTIyLjQ5YTEzLDEzLDAsMCwwLTYuNzktMy4xMiwxNC45NCwxNC45NCwwLDAsMC01LjItNC4xNEEyNC40MiwyNC40MiwwLDAsMCwyOS42MSwxNmMuODUuMDgsMi43NiwxLjgxLDMuNTMsMS45Mi0xLjE3LjgtNC4yOC43LTQuMjYsMi40NmEyNS4zNywyNS4zNywwLDAsMSwxMi41OCwyLDIzLjE4LDIzLjE4LDAsMCwwLTcuODksMi4xNWMtNS44MiwzLjA1LTcuMzQsOS4xNi01LjgyLDE3LjcyUzM2LDgxLjg4LDM4LjE0LDkyLjI2czI3LjU1LDEwLDI0LjM5LDMuNzRaIi8+PC9nPjxjaXJjbGUgY2xhc3M9ImNscy01IiBjeD0iMzcuNjkiIGN5PSI0Mi41OCIgcj0iMy4yMSIvPjxjaXJjbGUgY2xhc3M9ImNscy00IiBjeD0iMzkuMTIiIGN5PSI0MS41MSIgcj0iMC44MyIvPjxjaXJjbGUgY2xhc3M9ImNscy01IiBjeD0iNTkuMTQiIGN5PSI0MC42OCIgcj0iMi43NSIvPjxjaXJjbGUgY2xhc3M9ImNscy00IiBjeD0iNjAuMzciIGN5PSIzOS43NiIgcj0iMC43MSIvPjxwYXRoIGNsYXNzPSJjbHMtNiIgZD0iTTM4LjYxLDMzLjI5YTUuMzMsNS4zMywwLDAsMC00Ljc3LjM4Yy0yLjM1LDEuNDctMi4yNiwzLTIuMjYsM3MtMS4yNS0yLjc4LDIuMDctNC4xNFMzOC42MSwzMy4yOSwzOC42MSwzMy4yOVoiLz48cGF0aCBjbGFzcz0iY2xzLTciIGQ9Ik02MC44MSwzMy4wN2E3LjU4LDcuNTgsMCwwLDAtMy4xLTFjLTIuNzcsMC0zLjUyLDEuMjUtMy41MiwxLjI1cy40Ni0yLjkxLDQtMi4zM0EzLjU4LDMuNTgsMCwwLDEsNjAuODEsMzMuMDdaIi8+PHBhdGggY2xhc3M9ImNscy04IiBkPSJNNDcuNTIsNTVjLjMyLTIsNS4zNC01LjYyLDguOS01Ljg0QTM0LjczLDM0LjczLDAsMCwwLDY0LDQ4LjIzYzMtLjcsMTAuNjMtMi42MSwxMi43NC0zLjU5czExLjEuNDgsNC43Nyw0YTEwMi43NiwxMDIuNzYsMCwwLDEtMTUuNCw1LjkyYy01LjI3LDEuNTgtOC40Ni0xLjUxLTEwLjIyLDEuMDktMS4zOSwyLjA2LS4yOCw0Ljg4LDYsNS40Niw4LjUxLjc5LDE2LjY2LTMuODMsMTcuNTYtMS4zN1M3Mi4yLDY1LjI3LDY3LjIsNjUuMzcsNTIuMTQsNjIuMDcsNTAuNjMsNjEsNDcuMSw1Ny41MSw0Ny41Miw1NVoiLz48cGF0aCBjbGFzcz0iY2xzLTkiIGQ9Ik01MS4zNiw4MC42NHMtMTEuOTQtNi4zOC0xMi4xNC0zLjgsMCwxMy4xNSwxLjM5LDE0UzUyLDg1LjYyLDUyLDg1LjYybC0uNi01Wm00LjU4LS40MXM4LjE3LTYuMTcsMTAtNS43OCwyLjE4LDEzLjE1LjU5LDEzLjc2UzU1LjU3LDg1LDU1LjU3LDg1TDU2LDgwLjIzWiIvPjxwYXRoIGNsYXNzPSJjbHMtMTAiIGQ9Ik00OC40Nyw4MS4zMWMwLDQuMTgtLjYsNiwxLjE5LDYuMzdzNS4xOCwwLDYuMzgtLjc5LjItNi4xNy0uMi03LjE3LTcuMzctLjIxLTcuMzcsMS41OVoiLz48cGF0aCBjbGFzcz0iY2xzLTkiIGQ9Ik00OS4yNCw4MC4zOWMwLDQuMTgtLjYsNiwxLjE4LDYuMzZzNS4xNywwLDYuMzgtLjguMi02LjE2LS4yLTcuMTYtNy4zNy0uMi03LjM3LDEuNTlaIi8+PGNpcmNsZSBjbGFzcz0iY2xzLTExIiBjeD0iNTAiIGN5PSI0OS42IiByPSI0NSIvPjwvc3ZnPg==")}.Amazon{background-image:url("data:image/svg+xml;base64,PHN2ZyBpZD0iRWJlbmVfMSIgZGF0YS1uYW1lPSJFYmVuZSAxIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIj48ZGVmcz48c3R5bGU+LmNscy0xe2ZpbGw6I2YzOTcwMDt9LmNscy0ye2ZpbGw6I2ZmZjt9PC9zdHlsZT48L2RlZnM+PHBhdGggY2xhc3M9ImNscy0xIiBkPSJNOS40MSw3NC4xMUE1OS4zMiw1OS4zMiwwLDAsMCwzOS41Nyw5Myw1Miw1MiwwLDAsMCw3MSw4OS41NmE0NC40Myw0NC40MywwLDAsMCwxMy4xOC05LjIzLDEuMjQsMS4yNCwwLDAsMC0uMzktMS42OCwyLjM4LDIuMzgsMCwwLDAtMS41OCwwLDc5LjU2LDc5LjU2LDAsMCwxLTIzLDcuNzNBNzEuMDcsNzEuMDcsMCwwLDEsMzQuMSw4NC42Myw4OC4wOSw4OC4wOSwwLDAsMSwxMC42LDcyLjc1YTEsMSwwLDAsMC0xLjE5LDEuMzZaIi8+PHBhdGggY2xhc3M9ImNscy0xIiBkPSJNNzYuMjMsNzZhMzMuMjksMzMuMjksMCwwLDEsOS42Ni0uNDNsLjEzLDBBMiwyLDAsMCwxLDg3LjQ3LDc4YTQwLDQwLDAsMCwxLTMsOSwuNTEuNTEsMCwwLDAsLjMzLjYzLjUuNSwwLDAsMCwuNDQtLjA4LDE2LjMsMTYuMywwLDAsMCw2LjEzLTEyLjY1LDIuNDQsMi40NCwwLDAsMC0yLTIuNiwxOSwxOSwwLDAsMC0xMy41OCwyLjgxLjUuNSwwLDAsMCwuNDQuODhaIi8+PHBhdGggY2xhc3M9ImNscy0yIiBkPSJNNTkuODcsNjMuNTRhMzIuNiwzMi42LDAsMCwxLTUuNzEsNUEyNi43MSwyNi43MSwwLDAsMSw0MSw3Mi4yYTE5LjcsMTkuNywwLDAsMS0xMS4zNC0zLjksMTkuMDYsMTkuMDYsMCwwLDEtNS40LTE5LjdBMjIuMTMsMjIuMTMsMCwwLDEsMzcuMTUsMzUsNzIuNjMsNzIuNjMsMCwwLDEsNTcuODEsMzJWMjQuNjZhNy40NSw3LjQ1LDAsMCwwLTYuNDgtNi4zNCwxMS44OSwxMS44OSwwLDAsMC02LjE1LjgsOS42MSw5LjYxLDAsMCwwLTUuMzUsNi44MSwyLjM0LDIuMzQsMCwwLDEtMi40OCwxLjMybC0xMC0uODhhMi4yNSwyLjI1LDAsMCwxLTEuNjYtMiwyMC4zNSwyMC4zNSwwLDAsMSw3LjIzLTEyLjQ2QTI4LjUsMjguNSwwLDAsMSw1MC43Miw2YTI5LDI5LDAsMCwxLDE2LjYyLDUuNDRBMTcsMTcsMCwwLDEsNzMuNCwyNS4yM1Y1MC41NUExNi41MywxNi41MywwLDAsMCw3NSw1Ni42OWwzLjEzLDQuNTdhMi41LDIuNSwwLDAsMSwwLDIuMmwtOS4yNiw3LjhhMi40NiwyLjQ2LDAsMCwxLTIuNS0uMDhBNDguNjMsNDguNjMsMCwwLDEsNTkuODcsNjMuNTRaTTU3Ljc4LDQwLjU5YTUwLjUsNTAuNSwwLDAsMC04LjY5LjU3LDEyLjQxLDEyLjQxLDAsMCwwLTguMjEsNi4yLDEyLjMyLDEyLjMyLDAsMCwwLC42LDEwLjYsOCw4LDAsMCwwLDkuMywyLjQsMTUuNDcsMTUuNDcsMCwwLDAsNy0xMC45MlY0MC41OSIvPjwvc3ZnPg==")}';box.appendChild(style);let inputfield=document.createElement('input');inputfield.setAttribute('autofocus','');function findSearchQuery(){var query;let host=window.location.hostname;if(host.includes('google')){console.log('This is Google');var txtA=document.getElementsByTagName('textarea')[0];var input=document.getElementsByTagName('input')[0];if(txtA){if(txtA.value){var query=txtA.value}}else if(input){if(input.value){var query=input.value;}}}else if(host.includes('youtube')){console.log('This is Youtube');var y=document.querySelectorAll('#search');for(i=0;i<y.length;i+=1){if(y[i].nodeName=='INPUT'){if(y[i].value){var query=y[i].value}}}}else if(host.includes('duckduckgo')){console.log('This is Duck Duck Go');var d=document.querySelectorAll('#search_form_input')[0]||document.querySelectorAll('#search_form_input_homepage')[0];if(d.value){var query=d.value }}else if(host.includes('amazon')){console.log('This is Amazon');var a=document.querySelectorAll('#twotabsearchtextbox')[0];if(a.value){var query=a.value}}return query}var searchQuery=findSearchQuery();if(!searchQuery){inputfield.placeholder='No query found. Type something!';box.classList.add('error')}else{inputfield.value=searchQuery}function createBtn(searchengine,specs){console.log(specs);let btn=document.createElement('span');btn.innerHTML=searchengine;btn.classList.add(searchengine);box.appendChild(btn);btn.addEventListener('click',function(){window.open('https://www.'+specs[0]+inputfield.value,'_blank')})}for(let option in searchOptions){createBtn(option,searchOptions[option])}box.appendChild(inputfield)}else{document.getElementById('multisearch').remove()}})();
```

<br><br>

## How to adjust/customize
I've build the bookmarklet within the index.html and style.(s)css file.

The styles from the (s)css file needs to be included manually into the according javascript part of the index.html, once you've finsihed your adjustments in the style.(s)css file.

Afterwards take the JS part add "javascript:" at the beginning and minify everything. Now you can use it as bookmarklet.
```
javascript:
```

Detailed Tutorials about how to create bookmarklets can be found on google
