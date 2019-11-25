---
title: Form von WordprocessingML-Dokumenten
ms.date: 07/20/2015
ms.assetid: 2dfb446b-5a07-4c00-9ab3-a74ba734ff3a
ms.openlocfilehash: 64e9ca280c000ba488bfc72248bd83e37474f043
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350609"
---
# <a name="shape-of-wordprocessingml-documents-visual-basic"></a><span data-ttu-id="96bf8-102">Shape of WordprocessingML Documents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96bf8-102">Shape of WordprocessingML Documents (Visual Basic)</span></span>
<span data-ttu-id="96bf8-103">Dieses Thema enthält eine Einführung in die XML-Form von WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="96bf8-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="96bf8-104">Microsoft Office-Formate</span><span class="sxs-lookup"><span data-stu-id="96bf8-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="96bf8-105">Das systemeigene Dateiformat für das 2007 Microsoft Office-System ist Office Open XML (häufig als Open XML bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="96bf8-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="96bf8-106">Open XML ist ein XML-basiertes Format, das von der Ecma als Standard übernommen wurde und für das die ISO-IEC-Standardisierung beantragt wurde.</span><span class="sxs-lookup"><span data-stu-id="96bf8-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="96bf8-107">Die Markupsprache für Textverarbeitungsdateien innerhalb von Open XML heißt WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="96bf8-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="96bf8-108">Dieses Lernprogramm verwendet als Eingabe für die Beispiele WordprocessingML-Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="96bf8-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="96bf8-109">Benutzer von Microsoft Office 2003 müssen Microsoft Office Compatibility Pack für Word, Excel und PowerPoint 2007-Dateiformate installiert haben, um Dokumente im Office Open XML-Format speichern zu können.</span><span class="sxs-lookup"><span data-stu-id="96bf8-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="96bf8-110">Form der WordprocessingML-Dokumente</span><span class="sxs-lookup"><span data-stu-id="96bf8-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="96bf8-111">Als Erstes sollten Sie die Form von WordprocessingML-Dokumenten verstehen.</span><span class="sxs-lookup"><span data-stu-id="96bf8-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="96bf8-112">WordprocessingML-Dokumente enthalten ein Textkörperelement (mit der Bezeichnung `w:body`) mit den Absätzen des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="96bf8-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="96bf8-113">Jeder Absatz enthält mindestens einen Textrun (mit der Bezeichnung `w:r`).</span><span class="sxs-lookup"><span data-stu-id="96bf8-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="96bf8-114">Jeder Textrun enthält mindestens ein Textstück (mit der Bezeichnung `w:t`).</span><span class="sxs-lookup"><span data-stu-id="96bf8-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="96bf8-115">Das folgende Beispiel ist ein sehr einfaches WordprocessingML-Dokument:</span><span class="sxs-lookup"><span data-stu-id="96bf8-115">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="96bf8-116">Dieses Dokument besteht aus zwei Absätzen.</span><span class="sxs-lookup"><span data-stu-id="96bf8-116">This document contains two paragraphs.</span></span> <span data-ttu-id="96bf8-117">Beide Absätze enthalten genau einen Textrun, und jeder Textrun enthält genau ein Textstück.</span><span class="sxs-lookup"><span data-stu-id="96bf8-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="96bf8-118">Die einfachste Möglichkeit, sich den Inhalt eines WordprocessingML-Dokuments in XML-Form anzusehen, besteht darin, ein WordprocessingML-Dokument in Microsoft Word zu erstellen, das Dokument zu speichern und dann das folgende Programm zum Ausgeben des XML-Codes auf der Konsole auszuführen:</span><span class="sxs-lookup"><span data-stu-id="96bf8-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="96bf8-119">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="96bf8-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="96bf8-120">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="96bf8-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Sub Main()  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
  
        Using wdPackage As Package = _  
          Package.Open("SampleDoc.docx", _  
                       FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage _  
                .GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri( _  
                            New Uri("/", UriKind.Relative), _  
                            docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Get the officeDocument part from the package.  
                ' Load the XML in the part into an XDocument instance.  
                Dim xDoc As XDocument = _  
                    XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
                Console.WriteLine(xDoc.Root)  
            End If  
        End Using  
    End Sub  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="96bf8-121">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="96bf8-121">External Resources</span></span>  
 <span data-ttu-id="96bf8-122">[Einführung in die Microsoft Office (2007) Open XML-Dateiformate](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))</span><span class="sxs-lookup"><span data-stu-id="96bf8-122">[Introducing the Office (2007) Open XML File Formats](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))</span></span>  
  
 <span data-ttu-id="96bf8-123">[Übersicht über WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))</span><span class="sxs-lookup"><span data-stu-id="96bf8-123">[Overview of WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))</span></span>  
  
 [<span data-ttu-id="96bf8-124">Office 2003: Downloadseite für die XML-Referenzschemas</span><span class="sxs-lookup"><span data-stu-id="96bf8-124">Office 2003: XML Reference Schemas Download page</span></span>](https://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a><span data-ttu-id="96bf8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96bf8-125">See also</span></span>

- [<span data-ttu-id="96bf8-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96bf8-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
