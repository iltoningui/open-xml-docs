---

api_name:
- Microsoft.Office.DocumentFormat.OpenXML.Packaging
api_type:
- schema
ms.assetid: 4fbda0e3-5676-4a8f-ba62-3fba59fa418b
title: What's new in the Open XML SDK 2.5 for Office
ms.suite: office

ms.author: o365devx
author: o365devx
ms.topic: conceptual
ms.date: 11/01/2017
ms.localizationpriority: high
---

# What's new in the Open XML SDK 2.5 for Office

This topic describes the new and improved features included in the Open
XML SDK 2.5 for Office in addition to known issues and limitations.
 
The Open XML SDK 2.5 is a collection of classes that let you create and
manipulate Open XML documents - documents that adhere to the [Office Open XML File Formats Standard](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=51463).
Because the SDK provides an application program interface that lets you
manipulate Open XML documents directly, you can do so without the need
for the Office client products themselves in both client and server
operating environments. The SDK is designed to let you build high
performance client-side or server-side solutions that perform complex
operations using only a small amount of program code.

This release of the SDK greatly extends support for the file formats
while adding new features.


--------------------------------------------------------------------------------
## System requirements 
The Open XML SDK 2.5 has the following system requirements:

**Supported operating systems:** Windows 8 Preview, Windows 7, Windows
Server 2003 Service Pack 2, Windows Server 2008 R2, Windows Server 2008
Service Pack 2, Windows Vista Service Pack 2, Windows XP Service Pack 3

**System prerequisites:** .NET Framework version 4.0, Up to 300 MB of
available disk space


--------------------------------------------------------------------------------
## New software requirements 
Open XML SDK 2.5 requires .NET Framework 4.0 or the greater version.
Accordingly, the supported operating systems are updated to be the same
as the requirements of the .NET Framework 4.0.


--------------------------------------------------------------------------------
## Support of Office 2013 Preview file format 
In addition to offering compatibility with the Open XML SDK 1.0 classes
and the Open XML SDK 2.0 for Microsoft Office classes, Open XML SDK 2.5
provides new classes that enable you to write and build applications to
manipulate Open XML file extensions of the new Microsoft Office 2013
features (see Table 1). By using the Open XML SDK 2.5 Productivity Tool
for Office, those new extensions can be browsed inside the Open XML SDK
documentation in the left pane.

**Table 1. DocumentFormat.OpenXml.Office15 classes**

| Class | Description |
|---|---|
| **DocumentFormat.OpenXml.Office15.Excel** | Supports new PivotTable features, timeline, and the other new features of Excel |
| **DocumentFormat.OpenXml.Office15.Word** | Supports new Comment features (e.g. Comments pane) and other new features of Word. For example, the **CommentEx** class reads the comments author; The **WebVideoProperty** property is used to insert a video in a Word document |
| **DocumentFormat.OpenXml.Office15.PowerPoint, Theme** | Supports comment hint, theme family, and the other new features of PowerPoint |
| **DocumentFormat.OpenXml.Office15.Drawing** | Supports new Charts, PivotCharts, and other new Drawing and Chart features |
| **DocumentFormat.OpenXml.Office15.WebExtension, WebExtentionPane** | Supports app for Office and Task Pane app for Office features. The classes are viable for inserting or modifying app for Office into Word and Excel document files |

For code samples demonstrating how to use these new classes, please
refer to new articles posted to [Open XML Format SDK Forum](https://social.msdn.microsoft.com/Forums/oxmlsdk/threads) in
the Microsoft Developer Network.


--------------------------------------------------------------------------------
## Reads ISO Strict document files 
The Open XML SDK 2.5 can read ISO/IEC 29500 Strict Format files. Its
document contents are recognized as an Open XML Transitional Format file
when the document is opened. When the file is saved, the document is
saved as an Open XML Transitional Format file.

The Open XML SDK 2.5 converts ISO Strict files to Transitional Formatted
files when any changes are made to the document or when the document is
saved. Unless the document is saved or modified, the document is left as
an ISO Strict Format file.


--------------------------------------------------------------------------------
## Updated API information 
Because the file format extension of Office 2013 extends members of the
**\<extLst\>** element which did not have any
member elements, Open XML SDK 2.0 classes associated with the empty
**\<extLst\>** (e.g. **DocumentFormat.OpenXml.Spreadsheet.PivotFilter:ExtensionList**)
are updated to the new variants of **ExtensionList** classes of Open XML SDK 2.5 (e.g.
**DocumentFormat.OpenXml.Spreadsheet.PivotFilter:PivotFilterExtensionList**).
The following empty **ExtensionList** in each
class are replaced with a new **ExtensionList**
class including new **Off Open XML** child
element members.

**ExtensionList:**

-   **DocumentFormat.OpenXml.Drawing.ConnectionShapeLocks**

-   **DocumentFormat.OpenXml.Drawing.Theme**

-   **DocumentFormat.OpenXml.Drawing.ChartDrawing.NonVisualGroupShapeDrawingProperties**

-   **DocumentFormat.OpenXml.Drawing.Charts.MultiLevelStringReference**

-   **DocumentFormat.OpenXml.Drawing.Charts.NumberReference**

-   **DocumentFormat.OpenXml.Drawing.Charts.StringReference**

-   **DocumentFormat.OpenXml.Drawing.Charts.SurfaceChartSeries**

-   **DocumentFormat.OpenXml.Drawing.Diagrams.DataModelRoot**

-   **DocumentFormat.OpenXml.Drawing.Spreadsheet.NonVisualDrawingProperties**

-   **DocumentFormat.OpenXml.Drawing.Spreadsheet.NonVisualGroupShapeDrawingProperties**

-   **DocumentFormat.OpenXml.Office.Drawing.NonVisualGroupDrawingShapeProperties**

-   **DocumentFormat.OpenXml.Office2010.Excel.SlicerCacheDefinition**

-   **DocumentFormat.OpenXml.Office2010.Word.DrawingGroup.NonVisualGroupDrawingShapeProperties**

-   **DocumentFormat.OpenXml.Presentation.CommentAuthor**

-   **DocumentFormat.OpenXml.Presentation.NonVisualGroupShapeDrawingProperties**

-   **DocumentFormat.OpenXml.Spreadsheet.PivotFilter**

-   **DocumentFormat.OpenXml.Spreadsheet.QueryTable**

**ExtensionListWithModification:**

-   **DocumentFormat.OpenXml.Presentation.Comment**

-   **DocumentFormat.OpenXml.Presentation.HandoutMaster**

-   **DocumentFormat.OpenXml.Presentation.NotesMaster**

-   **DocumentFormat.OpenXml.Presentation.SlideLayout**

-   **DocumentFormat.OpenXml.Presentation.SlideMaster**


--------------------------------------------------------------------------------
## Deprecated API information 
The following section discusses deprecated API members:

### Smart tags

Because *smart tags* were deprecated in Office 2010, the Open XML SDK
2.5 doesn't support smart tag related Open XML elements. The Open XML
SDK 2.5 still can process smart tag elements as *unknown* elements,
however the Open XML SDK 2.5 Productivity Tool for Office validates
those elements (see the following list) in Office document files as
*invalid tags*.

DocumentFormat.OpenXml.Spreadsheet:

-   **SmartTagDisplayValues**

-   **SmartTagProperties**

-   **SmartTags**

-   **SmartTagType**

-   **SmartTagTypes**

DocumentFormat.OpenXml.Wordprocessing:

-   **SaveSmartTagAsXml**

-   **SmartTagAttribut**

-   **SmartTagProperties**

-   **SmartTagRun**

-   **SmartTagType**

### Office 2010 Beta only tags

The Open XML SDK 2.0 classes for Office 2010 *beta only* Open XML tags
are deprecated. For example, the beta only non-visual properties of
**DocumentFormat.OpenXml.Office2010.Drawing.ChartDrawing**,
**DocumentFormat.OpenXml.Office2010.Word**, and
**DocumentFormat.OpenXml.Office2010.Drawing**
have been removed from the Open XML SDK 2.5.
