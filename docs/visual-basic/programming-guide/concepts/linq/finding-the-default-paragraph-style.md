---
title: Suchen der standardmäßigen Absatzformatvorlage
ms.date: 07/20/2015
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
ms.openlocfilehash: c3c92c7ae6f80082265d8516e62118595a341790
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353453"
---
# <a name="finding-the-default-paragraph-style-visual-basic"></a>Finding the Default Paragraph Style (Visual Basic)
Die erste Aufgabe im Tutorial „Bearbeiten des Inhalts eines WordprocessingML-Dokuments“ besteht darin, die Standardabsatzformatvorlage im Dokument zu ermitteln.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel öffnet ein Office Open XML-WordprocessingML-Dokument, bestimmt den Dokument- und den Formatvorlagenteil des Pakets und führt dann eine Abfrage aus, um den Namen der Standardformatvorlage zu ermitteln. For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).  
  
 Die Abfrage sucht nach einem Knoten mit dem Namen `w:style`, der ein `w:type`-Attribut mit dem Wert "paragraph" und ein `w:default`-Attribut mit dem Wert "1" besitzt. Da es nur einen XML-Knoten mit diesen Attributen gibt, verwendet die Abfrage den <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType>-Operator, um eine Auflistung in ein Singleton umzuwandeln. Dann ruft die Abfrage den Wert des Attributs mit dem Namen `w:styleId` ab.  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.  
  
### <a name="code"></a>Code  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Kommentare  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
The default style is: Normal  
```  
  
## <a name="next-steps"></a>Nächste Schritte  
 Im nächsten Beispiel erstellen Sie eine ähnliche Abfrage. Diese Abfrage sucht nach allen Absätzen eines Dokuments und deren Formatvorlagen:  
  
- [Retrieving the Paragraphs and Their Styles (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a>Siehe auch

- [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
