# Name Tags — Mail Merge in LibreOffice Writer

The goal of this procedure is to produce a document containing multiple name tags — one per person — ready to send to the printer and then cut apart. Names are printed directly on the tags; no handwriting required.

This guide uses LibreOffice Writer on a standard US Letter page (8.5" × 11"). The same process can be adapted to other page sizes.

---

## Prerequisites

Before you begin, make sure the following are in place:

- **LibreOffice Writer** — for designing and producing the name tag document
- **LibreOffice Calc** — for editing your data file
- **LibreOffice Base** — must be installed; it works behind the scenes to connect your data to the Writer document. The merge will not work without it.
- **Your data file** — a CSV or ODS spreadsheet with participant names and any other fields you want on the tag. This file must be complete and **closed** before you begin.

---

## Step 1 — Prepare Your Data File

Your data can come from any source: a form export (ShelbyNext, Google Forms, etc.), a manually built list, or a combination. The final file needs to be a CSV or ODS spreadsheet with column headers in Row 1.

### Recommended field names

Use short, single-word headers with no spaces:

| Field | Use |
| --- | --- |
| `FirstName` | First name |
| `LastName` | Last name |
| `Group` | Class, team, grade, or other grouping |
| `Age` | Age |
| `Grade` | Grade level |
| `Phone` | Phone number |
| `Gender` | Gender |

Include only the fields you actually need on the tag. A simple name tag might only need `FirstName` and `LastName`.

### Before you move on

- Edit and clean your data file in LibreOffice Calc.
- **Finalize the file completely before registering it.** If you edit the file after registering it as a data source, LibreOffice will not automatically pick up your changes — you will need to re-register it (see gotcha below).
- Save the file and **close it** before opening Writer.
- Note the file location — you will need to browse for it.

!!! warning "Duplicate data source entries"
    If you re-register the same file more than once (for example, after editing it), LibreOffice will create a new data source entry each time and append a number to the name — `vbs_data`, then `vbs_data1`, then `vbs_data2`, and so on. This is normal; just make sure you select the correct (most recent) entry when prompted.

---

## Step 2 — Open Your Writer Document

Open LibreOffice Writer. You can start with a blank document or an existing one. You will design the name tag layout later — for now, just have the document open.

---

## Step 3 — Launch the Mail Merge Wizard and Register Your Data Source

From the menu bar, choose **Tools → Mail Merge Wizard**. The Mail Merge Wizard dialog will open. The left side of the dialog lists the steps: Select Starting Document, Select Document Type, Insert Address Block, Create Salutation, and Adjust Layout.

### Step 1 of the wizard — Select Starting Document

On the right side, select **Use the current document**.

Before clicking Next, you must register your data file. Below the radio buttons, click the **Exchange Databases…** button. This opens the Exchange Databases dialog.

#### Registering your data file

The Exchange Databases dialog has two panes: **Databases in Use** (left) and **Available Databases** (right).

1. Click the **Browse** button below the Available Databases pane.
2. A file finder dialog will open. Navigate to your CSV or ODS file, select it, and click **Open**.
3. The file will appear in the Available Databases pane as a LibreOffice Base file (LibreOffice creates this Base file as an intermediary — it is what actually connects to your Writer document).
4. Click the **expansion arrow** next to the file name to expand it. You will see the data table inside.
5. Click on the table to select it. The **Define** button at the bottom of the dialog will become active once a valid table is selected.
6. Click **Define**. The dialog closes and you are returned to the Mail Merge Wizard.

!!! warning "Editing your data file after registering"
    LibreOffice Base acts as an intermediary between your original data file and Writer. If you edit your original CSV or ODS after registering, the Base file will not automatically reflect those changes. You must re-register the file to pick up any edits.

### Step 2 of the wizard — Select Document Type

Select **Letter** and click **Next**.

### Step 3 of the wizard — Insert Address Block

No action needed here (this step is designed for formal letters). Confirm that the data source name shown looks correct, then click **Next**.

### Step 4 of the wizard — Create Salutation

No action needed. Do not check the salutation checkbox.

!!! important "Click Finish, not Next"
    The **Next** button on this step is greyed out unless you check the salutation box. Since you do not need a salutation, click **Finish** instead of Next. Steps 5 and beyond in the wizard do not apply to this task.

Clicking Finish closes the wizard and returns you to your document. The **Mail Merge toolbar** will appear.

---

## Step 4 — Design Your Name Tag Layout

### Adjust page margins

From the menu bar, choose **Format → Page Style** (or press **Alt+Shift+P**). Set your margins to zero or near-zero on all sides. You will control name tag padding through the table settings in the next step, so minimal page margins give you the most usable space.

### Mock up your label first

Before inserting any merge fields, type sample text in the first cell to mock up the layout. Use real-looking names and text so you can judge how the content actually fits. This is important because merge field placeholders (`<FirstName>`) are long and will appear to overflow the cell — they will not reflect actual name lengths.

Use LibreOffice's built-in heading styles to create a natural size hierarchy:

- **Heading 1** — primary line (e.g., first name or full name)
- **Heading 2** — secondary line (e.g., group or class)
- **Heading 3** — additional lines as needed

Using styles means you can adjust font sizes globally with a single style edit rather than reformatting each cell individually.

Work with the mock-up until the layout looks right. Then replace the sample text with merge fields (or insert the fields and apply the same styles to them).

### Insert a table

From the menu bar, choose **Table → Insert Table**. For a portrait letter page, a good starting point is **2 columns × 3 rows**, giving you 6 name tags per sheet.

### Set table properties

From the menu bar, choose **Table → Properties**. Work through the tabs as follows:

**Text Flow tab**

- Uncheck **Allow table to split across pages and columns**. This keeps each name tag intact on its page.

**Borders tab**

- Set **Padding** to at least **0.25"** on all sides. This creates the inner margin for name tag content.
- Leave **Line Arrangement** set to **No Borders** (default). You will cut apart the tags, so printed borders are generally not needed. Add borders here if your design calls for them.

**Background tab**

- No changes needed unless you want a background color or image on the tags.

Click **OK** to close Table Properties.

### Set row height

1. Select the entire table: **Table → Select → Table**.
2. Set the row height: **Table → Size → Row Height**.
3. Enter a value in the Height field.

For a 3-row table on an 11" page, the mathematical maximum is about 3.67" per row — but entering that value will push the table off the page and cause problems (see gotcha below). Use **3.5" or less**.

!!! warning "Row height and blank pages"
    If your row height pushes the table even slightly past the bottom of the page, LibreOffice will add a blank overflow page. In the final merged document, that blank page will appear between every page of name tags — a significant problem. Stay at 3.5" or less for a 3-row portrait layout.

---

## Step 5 — Insert Merge Fields

Click inside the **first cell** of the table. From the menu bar, choose **Insert → Field → More Fields** (or press **Ctrl+F2**).

The Fields dialog will open with six tabs. Choose the **Database** tab.

- On the left pane (**Type**), select **Mail Merge Fields**.
- On the right pane (**Database Selection**), your table should already be selected from Step 3.
- Under the table name, you will see your field names.
- Select a field name and click **Insert** (or double-click the field name). The field will appear in the cell as `<FieldName>`.
- Insert all the fields you want, pressing Enter between lines and Space between fields on the same line.
- Apply heading styles to the fields to match your mock-up.
- Close the Fields dialog when done.

### Next Record field

For the merge to advance to the next person in each subsequent cell, you must insert a **Next Record** field at the beginning of every cell after the first.

To insert it: **Insert → Field → More Fields → Database tab** → select **Next record** from the Type list → click **Insert**.

!!! note "Next Record in the first cell"
    You may also insert the Next Record field in the first cell without skipping the first record, but verify your output carefully to confirm all names are present.

### Copy to remaining cells

Once the first cell is formatted and complete:

1. Select the entire first cell.
2. Copy it (**Ctrl+C**).
3. Click into the next cell and paste (**Ctrl+V**).
4. Repeat for all remaining cells.
5. If you did not include the Next Record field in the first cell, add it to the beginning of each subsequent cell now.

---

## Step 6 — Save the Merged Document

When your layout is complete, use the **Mail Merge toolbar** to produce the final document.

!!! tip "Mail Merge toolbar"
    The toolbar includes navigation buttons (First, Previous, Current, Next, Last entry), an Exclude Recipient checkbox, and output buttons. The **Current Mail Merge Entry** field should show **-1** before running the merge. If it shows 1, the first record may be skipped.

Click **Save Merged Documents** on the toolbar. The Save As Options dialog will open:

1. Select **Save as a single large document** (default).
2. Optionally, specify a record range if you only need to print a subset of the name tags.
3. Click **Save Documents**.

A small progress dialog will appear as LibreOffice works through the records. When it finishes, a file dialog will open — choose a location and file name and click **Save**.

---

## Step 7 — Review and Print

Open the saved merged document and review it before printing:

- Confirm that names are filling in correctly and nothing is truncated.
- Check that the number of pages looks right for your record count.
- Look for any unexpected blank pages (a sign of a row height problem — see Step 4 gotcha).

When everything looks correct, load your paper into the printer and choose **File → Print**.

---

## Reusing the Template

Save your Writer document (the one with merge fields, not the merged output) as a template for future events. To reuse it:

1. Open the saved Writer template.
2. Launch the Mail Merge Wizard (**Tools → Mail Merge Wizard**).
3. On Step 1, click **Exchange Databases…** and register the new event's data file.
4. Proceed through the wizard and save the merged document as before.

You do not need to rebuild the table layout from scratch each time.
