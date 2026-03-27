# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

Answer: Its position relative from its original, increased, specifically from the top and left. It is also now overlapped with the main content box.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

Answer: The footer stays on the bottom despite attempting to scroll the page. The footer stays in that position due to "position: fixed" wherein it's remains fixed on the position you assign it to.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

Answer: When "position: absolute" was applied to the content box, it now sits beside the Sidebar. This shows that the property makes the position of the element relative to the one declared right before it.

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

Answer: The notice initially appears on top of the content but goes underneath it when swapped because z-index values essentially is how you assign the elements to a layer; a higher z-index/number indicates that it is layered on top of those with a lower z-index/number. If they have the same z-index, it means they're on the same layer.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    HTML & CSS:
    ```html
    <!DOCTYPE html>
    <html>
    <body>
        <div class="header">Header</div>
        <div class="sidebar">Sidebar</div>
        <div class="content">Main Content</div>
        <div class="notice">Notice!</div>
        <div class="footer">Footer</div>
    </body>
    </html>
    ```

    ``` css
    .content {
      position: absolute;
      top:66px;
      left:200px;
      background: lightyellow;
      width: 300px;
      height: 200px;
      z-index:1;
    }   
    .notice {
        position: absolute;
        top: 68px;
        left:430px;
        background: orange;
        padding: 10px;
        z-index:2;
    }
    ```

    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    Answer: Content is moved relative to its original position when assigned "position: relative". It moves relative to the viewport when assigned "position: fixed".

    * What do you observe on about the effect of z-index on .notice and .content boxes?
    Answer: It changes which layer the element is situated on; either on top, underneath, or the same layer as the other element as mentioned earlier.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

    Static positioning means it is the default position of the element when declared. Relative positioning is based on the default position of the element but can be moved with values such as top and left. Absolute positioning makes the element situated beside the element right before it and can be adjusted relative to the latter. Lastly, fixed positioning refers to the positioning of an object based on the viewport, not moving even when scrolling the page.

    b. How does absolute positioning depend on its parent element?

    c. How do you differentiate sticky from fixed (you can research on sticky)?

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.