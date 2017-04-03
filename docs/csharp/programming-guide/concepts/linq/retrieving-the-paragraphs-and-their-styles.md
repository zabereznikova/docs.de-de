---
title: "Abrufen der Absätze und ihrer Stile (C#) | Microsoft-Dokumentation"
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
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fddaa5e25befc40278888c0b401ad39a61e8e9d4
ms.lasthandoff: 03/13/2017


---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a>Abrufen der Absätze und ihrer Stile (C#)
In diesem Beispiel schreiben wir eine Abfrage, die die Absatzknoten aus einem WordprocessingML-Dokument abruft. Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage.  
  
 Diese Abfrage baut auf der Abfrage im vorherigen Beispiel auf, [Finding the Default Paragraph Style (C#) (Suchen der standardmäßigen Absatzformatvorlage (C#))](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), in der die Standardformatvorlage aus der Liste der Formatvorlagen abgerufen wird. Diese Information wird benötigt, damit die Abfrage die Formatvorlagen der Absätze abrufen kann, für die keine Formatvorlage explizit festgelegt ist. Absatzformatvorlagen werden über das `w:pPr`-Element festgelegt. Wenn ein Absatz dieses Element nicht enthält, wird er mit der Standardformatvorlage formatiert.  
  
 In diesem Thema wird die Bedeutung einiger Teile der Abfrage erläutert, bevor die Abfrage im Kontext eines vollständigen, funktionstüchtigen Beispiels gezeigt wird.  
  
## <a name="example"></a>Beispiel  
 Die Abfrage verwendet zum Abrufen aller in einem Dokument vorhandenen Absätze und der zugehörigen Formatvorlagen die folgende Quelle:  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 Dieser Ausdruck ähnelt der Quelle der Abfrage im vorherigen Beispiel, [Finding the Default Paragraph Style (C#), (Suchen der standardmäßigen Absatzformatvorlage (C#))](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md). Der Hauptunterschied besteht darin, dass die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse anstatt der <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse verwendet wird. Die Abfrage verwendet die <xref:System.Xml.Linq.XContainer.Descendants%2A-Achse, weil in Dokumenten mit Abschnitten die Absätze nicht die direkten untergeordneten Elemente des Textkörpers sind. Die Absätze befinden sich zwei Ebenen weiter unten in der Hierarchie. Durch die Verwendung der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse funktioniert der Code unabhängig davon, ob das Dokument Abschnitte verwendet.  
  
## <a name="example"></a>Beispiel  
 Die Abfrage verwendet eine `let`-Klausel, um das Element zu bestimmen, das den Formatvorlagenknoten enthält. Wenn es kein Element gibt, wird `styleNode` auf `null` gesetzt.  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 Die `let`-Klausel verwendet zuerst die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse, um alle Elemente mit dem Namen `pPr` zu suchen, anschließend die Erweiterungsmethode <xref:System.Xml.Linq.Extensions.Elements%2A> zum Suchen aller untergeordneten Elemente mit dem Namen `pStyle` und zuletzt den Standardabfrageoperator <xref:System.Linq.Enumerable.FirstOrDefault%2A> zum Konvertieren der Auflistung in ein Singleton. Wenn die Auflistung leer ist, wird `styleNode` auf `null` gesetzt. Dies ist eine sinnvolle Vorgehensweise, um nach dem `pStyle`-Nachfolgerknoten zu suchen. Beachten Sie dabei: Wenn der untergeordnete `pPr`-Knoten nicht existiert, löst der Code keine Ausnahme aus, sondern `styleNode` wird auf `null` gesetzt, was dem erwünschten Verhalten dieser `let`-Klausel entspricht.  
  
 Die Abfrage projiziert eine Auflistung eines anonymen Typs mit zwei Membern, `StyleName` und `ParagraphNode`.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absatzknoten aus einem WordprocessingML-Dokument abruft. Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage. Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf. Die neue Abfrage wird im Code unten durch entsprechende Kommentare gekennzeichnet.  
  
 Eine Anleitung zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Creating the Source Office Open XML Document (C#) (Erstellen eines Office Open-Quell-XML-Dokuments (C#))](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Es verwendet Typen im Namespace <xref:System.IO.Packaging?displayProperty=fullName>.  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 Dieses Beispiel produziert bei Anwendung auf das in [Erstellen eines Office Open-Quell-XML-Dokuments (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md) beschriebene Dokument die folgende Ausgabe.  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a>Nächste Schritte  
 Im nächsten Thema, [Abrufen des Texts der Absätze (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), erstellen Sie eine Abfrage zum Abrufen des Texts der Absätze.  
  
## <a name="see-also"></a>Siehe auch  
 [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
