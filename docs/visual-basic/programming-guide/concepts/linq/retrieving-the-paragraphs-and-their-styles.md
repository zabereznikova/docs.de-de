---
title: "Abrufen der Absätze und deren Stile (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bb6d68296a720a796a319502c4cb2f0319727459
ms.lasthandoff: 03/13/2017


---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a>Abrufen der Absätze und deren Stile (Visual Basic)
In diesem Beispiel schreiben wir eine Abfrage, die die Absatzknoten aus einem WordprocessingML-Dokument abruft. Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage.  
  
 Diese Abfrage baut auf der Abfrage im vorherigen Beispiel [Suchen der standardmäßigen Absatzformatvorlage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), der den Standardstil aus der Liste der Formatvorlagen abgerufen. Diese Information wird benötigt, damit die Abfrage die Formatvorlagen der Absätze abrufen kann, für die keine Formatvorlage explizit festgelegt ist. Absatzformatvorlagen werden über das `w:pPr`-Element festgelegt. Wenn ein Absatz dieses Element nicht enthält, wird er mit der Standardformatvorlage formatiert.  
  
 In diesem Thema wird die Bedeutung einiger Teile der Abfrage erläutert, bevor die Abfrage im Kontext eines vollständigen, funktionstüchtigen Beispiels gezeigt wird.  
  
## <a name="example"></a>Beispiel  
 Die Abfrage verwendet zum Abrufen aller in einem Dokument vorhandenen Absätze und der zugehörigen Formatvorlagen die folgende Quelle:  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 Dieser Ausdruck ähnelt der Quelle der Abfrage im vorherigen Beispiel [Suchen der Standard-Absatzformatvorlage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md). Der Hauptunterschied besteht darin, dass er verwendet die <xref:System.Xml.Linq.XContainer.Descendants%2A>Achse statt der <xref:System.Xml.Linq.XContainer.Elements%2A>Achse.</xref:System.Xml.Linq.XContainer.Elements%2A> </xref:System.Xml.Linq.XContainer.Descendants%2A> Die Abfrage verwendet die <xref:System.Xml.Linq.XContainer.Descendants%2A>Achse weil in Dokumenten mit Abschnitten die Absätze nicht die direkten untergeordneten Elemente des Body-Elements sein, sondern die Absätze befinden sich zwei Ebenen weiter unten in der Hierarchie.</xref:System.Xml.Linq.XContainer.Descendants%2A> Mithilfe der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse funktioniert der Code, ob das Dokument Abschnitte verwendet.</xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
## <a name="example"></a>Beispiel  
 Die Abfrage verwendet eine `Let`-Klausel, um das Element zu bestimmen, das den Formatvorlagenknoten enthält. Wenn es kein Element gibt, wird `styleNode` auf `Nothing` gesetzt.  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 Die `Let` -Klausel verwendet zuerst die <xref:System.Xml.Linq.XContainer.Elements%2A>Achse, um nach allen Elementen, die mit dem Namen suchen `pPr`, verwendet dann die <xref:System.Xml.Linq.Extensions.Elements%2A>Erweiterungsmethode finden Sie alle untergeordneten Elemente mit dem Namen `pStyle`, und die <xref:System.Linq.Enumerable.FirstOrDefault%2A>Standardabfrageoperator, um die Auflistung in ein Singleton umzuwandeln.</xref:System.Linq.Enumerable.FirstOrDefault%2A> </xref:System.Xml.Linq.Extensions.Elements%2A> </xref:System.Xml.Linq.XContainer.Elements%2A> Wenn die Auflistung leer ist, wird `styleNode` auf `Nothing` gesetzt. Dies ist eine sinnvolle Vorgehensweise, um nach dem `pStyle`-Nachfolgerknoten zu suchen. Beachten Sie dabei: Wenn der untergeordnete `pPr`-Knoten nicht existiert, löst der Code keine Ausnahme aus, sondern `styleNode` wird auf `Nothing` gesetzt, was dem erwünschten Verhalten dieser `Let`-Klausel entspricht.  
  
 Die Abfrage projiziert eine Auflistung eines anonymen Typs mit zwei Membern, `StyleName` und `ParagraphNode`.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absatzknoten aus einem WordprocessingML-Dokument abruft. Außerdem ermittelt es für jeden Absatz die verwendete Formatvorlage. Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf. Die neue Abfrage wird im Code unten durch entsprechende Kommentare gekennzeichnet.  
  
 Sie finden die Anleitung zum Erstellen des Quelldokuments für dieses Beispiel in [Erstellen von Office Open XML-Quelldokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Er verwendet die Typen in der <xref:System.IO.Packaging?displayProperty=fullName>Namespace.</xref:System.IO.Packaging?displayProperty=fullName>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe, wenn für das Dokument, das in beschriebene [Erstellen von Office Open XML-Quelldokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
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
 Im nächsten Thema [Abrufen des Texts der Absätze (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), erstellen Sie eine Abfrage zum Abrufen des Texts der Absätze.  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
