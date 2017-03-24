---
title: "Suchen der standardmäßigen Absatzformatvorlage (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 041e99f4fd70008208a8f661f6763159ac7f4479
ms.lasthandoff: 03/13/2017


---
# <a name="finding-the-default-paragraph-style-visual-basic"></a>Suchen der standardmäßigen Absatzformatvorlage (Visual Basic)
Die erste Aufgabe beim Bearbeiten von Informationen in einem WordprocessingML-Dokument-Lernprogramm ist zu den Standardstil der Absätze im Dokument zu finden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel öffnet ein Office Open XML-WordprocessingML-Dokument, bestimmt den Dokument- und den Formatvorlagenteil des Pakets und führt dann eine Abfrage aus, um den Namen der Standardformatvorlage zu ermitteln. Informationen zu Office Open XML-Dokument-Pakete und deren Bestandteilen der finden Sie unter [Details von Office Open XML-WordprocessingML-Dokumenten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).  
  
 Die Abfrage sucht nach einem Knoten mit dem Namen `w:style`, der ein `w:type`-Attribut mit dem Wert "paragraph" und ein `w:default`-Attribut mit dem Wert "1" besitzt. Da es nur einen XML-Knoten mit diesen Attributen gibt, verwendet die Abfrage die <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName>Operator, um eine Auflistung in ein Singleton umzuwandeln.</xref:System.Linq.Enumerable.First%2A?displayProperty=fullName> Dann ruft die Abfrage den Wert des Attributs mit dem Namen `w:styleId` ab.  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Er verwendet die Typen in der <xref:System.IO.Packaging?displayProperty=fullName>Namespace.</xref:System.IO.Packaging?displayProperty=fullName>  
  
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
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a>Nächste Schritte  
 Im nächsten Beispiel erstellen Sie eine ähnliche Abfrage, die sucht nach allen Absätzen eines Dokuments und deren Formatvorlagen:  
  
-   [Abrufen der Absätze und deren Stile (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
