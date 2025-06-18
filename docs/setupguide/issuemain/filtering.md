# Data Filtration 

This section covers the available methods for filtering issue data in Smart DevOps helping you quickly find the information you need.

## Filtering Issue Data via Portal
The Portal offers two ways to filter issue data. Each method is described below.

### 1. Filtering via the General Tab

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

    Enter the *complete* description text to retrieve matching issues. Partial keywords will not return results.

    <div style="text-align: left;">
     <img src="./assets/image73.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- **Status** 

     Select the desired status from the dropdown (*Active (A)*, *Inactive (I)*, or *Complete (C)*), then click **Find** to filter accordingly.
        
    <div style="text-align: left;">
     <img src="./assets/image74.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

### 2.  Filter via Grid Search Box
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

- Select the desired column from the list. The system will then filter the **rows in the grid** where that keyword appears in the selected **column only**.

## Filtering Issue Data via Fat Client
The data filtering process in the Fat Client works the same way as the [Filtering via the General Tab](#1-filtering-via-the-general-tab) in the Portal.

The key difference lies in how the **Description** field is handled.

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