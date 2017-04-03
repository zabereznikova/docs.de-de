---
title: Form von WordprocessingML-Dokumenten (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 29c8555df695f9e1a93256ea3a25ed22d441fd6d
ms.lasthandoff: 03/13/2017


---
# <a name="shape-of-wordprocessingml-documents-c"></a>Form von WordprocessingML-Dokumenten (C#)
Dieses Thema enthält eine Einführung in die XML-Form von WordprocessingML-Dokumenten.  
  
## <a name="microsoft-office-formats"></a>Microsoft Office-Formate  
 Das systemeigene Dateiformat für das 2007 Microsoft Office-System ist Office Open XML (häufig als Open XML bezeichnet). Open XML ist ein XML-basiertes Format, das von der Ecma als Standard übernommen wurde und für das die ISO-IEC-Standardisierung beantragt wurde. Die Markupsprache für Textverarbeitungsdateien innerhalb von Open XML heißt WordprocessingML. Dieses Lernprogramm verwendet als Eingabe für die Beispiele WordprocessingML-Quelldateien.  
  
 Benutzer von Microsoft Office 2003 müssen das Compatibility Pack für Microsoft Office 2007-Dateiformate installiert haben, um Dokumente im Office Open XML-Format speichern zu können.  
  
## <a name="the-shape-of-wordprocessingml-documents"></a>Form der WordprocessingML-Dokumente  
 Als Erstes sollten Sie die Form von WordprocessingML-Dokumenten verstehen. WordprocessingML-Dokumente enthalten ein Textkörperelement (mit der Bezeichnung `w:body`) mit den Absätzen des Dokuments. Jeder Absatz enthält mindestens einen Textrun (mit der Bezeichnung `w:r`). Jeder Textrun enthält mindestens ein Textstück (mit der Bezeichnung `w:t`).  
  
 Das folgende Beispiel ist ein sehr einfaches WordprocessingML-Dokument:  
  
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
  
 Dieses Dokument besteht aus zwei Absätzen. Beide Absätze enthalten genau einen Textrun, und jeder Textrun enthält genau ein Textstück.  
  
 Die einfachste Möglichkeit, sich den Inhalt eines WordprocessingML-Dokuments in XML-Form anzusehen, besteht darin, ein WordprocessingML-Dokument in Microsoft Word zu erstellen, das Dokument zu speichern und dann das folgende Programm zum Ausgeben des XML-Codes auf der Konsole auszuführen:  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Es werden Typen im Namespace <xref:System.IO.Packaging?displayProperty=fullName> verwendet.  
  
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
  
## <a name="external-resources"></a>Externe Ressourcen  
 [Einführung in die Microsoft Office (2007) Open XML-Dateiformate](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 [Übersicht über WordprocessingML](http://go.microsoft.com/fwlink/?LinkId=98094)  
  
 [Office 2003: Downloadseite für die XML-Referenzschemas](http://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a>Siehe auch  
 [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
