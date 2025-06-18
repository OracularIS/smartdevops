# Filter Issue Data 

This section covers the available methods for filtering issue data in Smart DevOps helping you quickly find the information you need.

## Filter Issue Data through Portal
The Portal offers two ways to filter issue data. Each method is described below.

### 1. Filteration - General Tab

You can filter issues using the input fields available in the **General** tab. Here's how it works for each field:

- **User ID**

    Enter the exact User ID you want to filter by, then click **Find**. The grid will show all issues assigned to that user.
   
    <div style="text-align: left;">
     <img src="./assets/image71.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- **Issue ID** 

    Enter the full issue ID and click **Find** to display the specific issue.
   
    <div style="text-align: left;">
     <img src="./assets/image72.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- **Description** 

    Enter the **complete** description text to retrieve matching issues. Partial keywords will not return results.

    <div style="text-align: left;">
     <img src="./assets/image73.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- **Status** 

     Select the desired status from the dropdown (Active (A), Inactive (I), or Complete (C)), then click **Find** to filter accordingly.
        
    <div style="text-align: left;">
     <img src="./assets/image74.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

### 2.  Filteration - Quick Grid Filter
The **search box** located at the top-right corner of the data grid is used to filter records based on columns within the grid.

Here is how filtering works:

- Start typing in the search box.
- When you type a keyword (e.g., `test`), the system displays matching column options like:
  - Issue Assignment Sequence
  - Issue Description
  - Issue ID
  - Status Code
  - User ID

      <div style="text-align: left;">
     <img src="./assets/image75.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- Select the desired column from the list  e.g., `test` in Issue Description.

    <div style="text-align: left;">
     <img src="./assets/image84.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- The system will then filter the **rows in the grid** where that keyword (e.g., `test`) appears in the selected **column only**.

    <div style="text-align: left;">
     <img src="./assets/image85.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>



### Filter data using Wildcards

While filtering data in the Quick Grid Filter, you can use the `*` wildcard in the search bar to make your search more flexible:

- To find issues where the description **starts with** a certain word, use: `word*`  
  → Example: `test*` will match "test case", "testing", etc.
      <div style="text-align: left;">
     <img src="./assets/image86.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


- To find descriptions that **end with** a specific word, use: `*word`  
  → Example: `*test` will match "test issue", "test Git commit", etc.
      <div style="text-align: left;">
     <img src="./assets/image87.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- To find descriptions that **contain** a word anywhere, use: `*word*` or simply enter the word.  
  → Example: `*test*` or `test`  will match "Rollout Testing", "testing process", "pretest", etc.
        <div style="text-align: left;">
     <img src="./assets/image88.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

This method helps you quickly locate relevant issues without needing to enter the full description text.

## Filter Issue Data through Fat Client
The data filtering process in the Fat Client works the same way as the [Filtering via the General Tab](#1-filtering-via-the-general-tab) in the Portal.

### Filter data using Wildcards

 Unlike the Portal which requires you to enter the full description text for filtering the Fat Client allows more **flexible searching** by supporting partial text and keyword matching.

You can use wildcard characters to refine your search:

- Use `test%` to find descriptions that **start with** the word “test”.

    <div style="text-align: left;">
     <img src="./assets/image76.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- Use `%test` to find descriptions that **end with** the word “test”.

    <div style="text-align: left;">
     <img src="./assets/image77.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
- Use `%test%` to find descriptions that **contain** the word “test” anywhere in the text.

    <div style="text-align: left;">
     <img src="./assets/image78.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- If you enter just `test`, it will only return results where the **entire description** is exactly “test”.

    <div style="text-align: left;">
     <img src="./assets/image79.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

This makes searching in the Fat Client more efficient especially when you're unsure of the full description or only remember part of it.

---

<br><br>