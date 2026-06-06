# Name Tags — Mail Merge in LibreOffice Writer

This guide explains how to create personalized name tags for VBS, camp, or other events using a spreadsheet of names and LibreOffice Writer's mail merge feature.

By the end of this guide you will have a document ready to print — one name tag per person — without typing each name individually.

---

## What You Will Need

- **LibreOffice** (Writer and Calc) installed on your computer
- A list of participant names (you will create this as a spreadsheet)
- Name tag label sheets — this guide uses **Avery 5395** (2¾" × 4¼", 2 per sheet), but any compatible label sheet works

---

## Step 1 — Prepare Your Name List in LibreOffice Calc

1. Open **LibreOffice Calc** (the spreadsheet program).
2. In **Row 1**, type these column headers exactly as shown:

   | A | B | C |
   | --- | --- | --- |
   | FirstName | LastName | Group |

3. Starting in **Row 2**, enter one person per row:

   | A | B | C |
   | --- | --- | --- |
   | Emma | Johnson | Blue Team |
   | Liam | Garcia | Red Team |

   The **Group** column is optional. Use it for a class name, team color, grade, or any label you want printed on the tag. Leave the column blank if you don't need it.

4. Save the file. Give it a clear name such as `vbs-participants-2025.ods` and save it somewhere you can find it (Desktop or Documents).

   > **Important:** Close the file after saving. LibreOffice Writer cannot use it as a data source while it is open in Calc.

---

## Step 2 — Set Up the Name Tag Template in LibreOffice Writer

### Open the Labels Dialog

1. Open **LibreOffice Writer**.
2. From the menu bar, choose **File → New → Labels**.

   The **Labels** dialog will open.

### Choose Your Label Format

1. Click the **Labels** tab (it should already be selected).
2. In the **Brand** dropdown, choose **Avery Letter Size**.
3. In the **Type** dropdown, choose **5395**.

   > If you are using a different brand or size, find the matching entry in the dropdowns. The dimensions shown on the right side of the dialog should match your label sheet packaging.

4. Leave the **Inscription** box blank for now — you will insert merge fields in Step 3.
5. Click **New Document**. LibreOffice will generate a blank label sheet and open it as a new Writer document.

---

## Step 3 — Connect Your Spreadsheet and Insert Merge Fields

With the blank label sheet open, you will now connect your spreadsheet and tell LibreOffice what to print on each label.

1. From the menu bar, choose **Tools → Mail Merge Wizard**.

   The **Mail Merge Wizard** will open.

### Wizard Step 1 — Starting Document

- Select **Use the current document** and click **Next**.

### Wizard Step 2 — Document Type

- Select **Labels** and click **Next**.

### Wizard Step 3 — Address Block (skip this)

- Click **Next** without making changes. You will insert fields manually.

### Wizard Step 4 — Salutation (skip this)

- Click **Next** without making changes.

### Wizard Step 5 — Adjust Layout (skip this)

- Click **Next** without making changes.

### Wizard Step 6 — Edit Document

- Click **Edit Document**. This will close the wizard temporarily and return you to the label sheet.
- You will see a grid of empty label boxes. Click inside the **first label** (top-left box).
- From the menu bar, choose **Insert → Field → More Fields**.
- Click the **Database** tab.
- Click the **Browse** button and navigate to your `.ods` spreadsheet. Select it and click **Open**.
- In the list that appears, expand your file name, then expand **Sheet1**.
- Double-click **FirstName** to insert it. You will see `<FirstName>` appear in the label.
- Press the **Space bar**, then double-click **LastName** to insert it.
- Press **Enter** to move to a new line.
- If you want the group label, double-click **Group**.
- Close the **Fields** dialog.
- Your first label should now look like this:

  ```
  <FirstName> <LastName>
  <Group>
  ```

- From the menu bar, choose **Format → Synchronize Labels** (or click the **Synchronize Labels** button in the toolbar). This copies your field layout to all the other labels on the sheet.
- Click **Return to Mail Merge Wizard** in the toolbar.

### Wizard Step 7 — Personalize Documents

- Click **Next**.

### Wizard Step 8 — Save, Print, or Send

- Choose **Print Document** to print directly, or choose **Save Document** to save a merged document with all names filled in.
- Click **Finish**.

---

## Step 4 — Preview and Print

### If You Chose Print

1. A dialog will ask which records to print. Choose **All** to print every name on your list.
2. Load your label sheets into the printer and click **OK**.

### If You Saved the Merged Document

1. Open the saved file. Each page contains label-sized boxes with the actual names filled in (not field codes).
2. Review the document to make sure names look correct.
3. Load your label sheets into the printer, then choose **File → Print** and print all pages.

---

## Tips and Troubleshooting

| Problem | Solution |
| --- | --- |
| Fields show `<FirstName>` instead of actual names | The spreadsheet is not connected. Repeat Step 3 and confirm the file path. |
| Labels are misaligned on the sheet | Confirm you selected the correct Avery number. Check printer settings — make sure scaling is set to **100% (actual size)**, not "fit to page." |
| Some names are missing | Check the spreadsheet for blank rows. A blank row will produce a blank name tag. |
| The Group column is blank on the tags | Confirm the column header in the spreadsheet is spelled exactly **Group** (capital G, no spaces). |
| Only one name prints | You may need to click **Synchronize Labels** after inserting your fields (see Step 3). |

---

## Starting Fresh Next Time

Once your template is saved (the `.odt` Writer file), you can reuse it for future events:

1. Open the saved `.odt` template.
2. From the menu bar, choose **Edit → Exchange Database** and point it to the new event's spreadsheet.
3. Print as before.

You do not need to rebuild the label layout from scratch each time.
