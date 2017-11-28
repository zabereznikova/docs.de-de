---
title: Form von WordprocessingML-Dokumenten (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8c1ccbfd71baff50a8055cd89ddecf47bd35cac9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="1aae9-102">Form von WordprocessingML-Dokumenten (C#)</span><span class="sxs-lookup"><span data-stu-id="1aae9-102">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="1aae9-103">Dieses Thema enthält eine Einführung in die XML-Form von WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="1aae9-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="1aae9-104">Microsoft Office-Formate</span><span class="sxs-lookup"><span data-stu-id="1aae9-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="1aae9-105">Das systemeigene Dateiformat für das 2007 Microsoft Office-System ist Office Open XML (häufig als Open XML bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="1aae9-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="1aae9-106">Open XML ist ein XML-basiertes Format, das von der Ecma als Standard übernommen wurde und für das die ISO-IEC-Standardisierung beantragt wurde.</span><span class="sxs-lookup"><span data-stu-id="1aae9-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="1aae9-107">Die Markupsprache für Textverarbeitungsdateien innerhalb von Open XML heißt WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="1aae9-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="1aae9-108">Dieses Lernprogramm verwendet als Eingabe für die Beispiele WordprocessingML-Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="1aae9-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="1aae9-109">Benutzer von Microsoft Office 2003 müssen das Compatibility Pack für Microsoft Office 2007-Dateiformate installiert haben, um Dokumente im Office Open XML-Format speichern zu können.</span><span class="sxs-lookup"><span data-stu-id="1aae9-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="1aae9-110">Form der WordprocessingML-Dokumente</span><span class="sxs-lookup"><span data-stu-id="1aae9-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="1aae9-111">Als Erstes sollten Sie die Form von WordprocessingML-Dokumenten verstehen.</span><span class="sxs-lookup"><span data-stu-id="1aae9-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="1aae9-112">WordprocessingML-Dokumente enthalten ein Textkörperelement (mit der Bezeichnung `w:body`) mit den Absätzen des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="1aae9-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="1aae9-113">Jeder Absatz enthält mindestens einen Textrun (mit der Bezeichnung `w:r`).</span><span class="sxs-lookup"><span data-stu-id="1aae9-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="1aae9-114">Jeder Textrun enthält mindestens ein Textstück (mit der Bezeichnung `w:t`).</span><span class="sxs-lookup"><span data-stu-id="1aae9-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="1aae9-115">Das folgende Beispiel ist ein sehr einfaches WordprocessingML-Dokument:</span><span class="sxs-lookup"><span data-stu-id="1aae9-115">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="1aae9-116">Dieses Dokument besteht aus zwei Absätzen.</span><span class="sxs-lookup"><span data-stu-id="1aae9-116">This document contains two paragraphs.</span></span> <span data-ttu-id="1aae9-117">Beide Absätze enthalten genau einen Textrun, und jeder Textrun enthält genau ein Textstück.</span><span class="sxs-lookup"><span data-stu-id="1aae9-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="1aae9-118">Die einfachste Möglichkeit, sich den Inhalt eines WordprocessingML-Dokuments in XML-Form anzusehen, besteht darin, ein WordprocessingML-Dokument in Microsoft Word zu erstellen, das Dokument zu speichern und dann das folgende Programm zum Ausgeben des XML-Codes auf der Konsole auszuführen:</span><span class="sxs-lookup"><span data-stu-id="1aae9-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="1aae9-119">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="1aae9-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="1aae9-120">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="1aae9-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="1aae9-121">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1aae9-121">External Resources</span></span>  
 [<span data-ttu-id="1aae9-122">Einführung in die Microsoft Office (2007) Open XML-Dateiformate</span><span class="sxs-lookup"><span data-stu-id="1aae9-122">Introducing the Office (2007) Open XML File Formats</span></span>](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 [<span data-ttu-id="1aae9-123">Übersicht über WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="1aae9-123">Overview of WordprocessingML</span></span>](http://go.microsoft.com/fwlink/?LinkId=98094)  
  
 [<span data-ttu-id="1aae9-124">Office 2003: Downloadseite für die XML-Referenzschemas</span><span class="sxs-lookup"><span data-stu-id="1aae9-124">Office 2003: XML Reference Schemas Download page</span></span>](http://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a><span data-ttu-id="1aae9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aae9-125">See Also</span></span>  
 [<span data-ttu-id="1aae9-126">Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))</span><span class="sxs-lookup"><span data-stu-id="1aae9-126">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
