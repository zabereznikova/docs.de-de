---
title: Abrufen des Texts der Absätze
ms.date: 07/20/2015
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
ms.openlocfilehash: 24167ade2d0326ef9382536f79f9e45eb22c89c5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413387"
---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a>Abrufen des Texts der Absätze (Visual Basic)
Dieses Beispiel baut auf dem vorherigen Beispiel auf [und ruft die Absätze und deren Stile (Visual Basic)](retrieving-the-paragraphs-and-their-styles.md)ab. Dieses neue Beispiel ruft den Text jedes einzelnen Absatzes als Zeichenfolge ab  
  
 Zum Abrufen des Texts fügt dieses Beispiel eine zusätzliche Abfrage hinzu, die die Auflistung der anonymen Typen durchläuft und eine neue Auflistung eines anonymen Typs unter Hinzufügung eines neuen Members, `Text`, projiziert Mithilfe des <xref:System.Linq.Enumerable.Aggregate%2A>-Standardabfrageoperators werden mehrere Zeichenfolgen zu einer Zeichenfolge verkettet.  
  
 Dieses Verfahren (erst eine Auflistung eines anonymen Typs projizieren und dann diese Auflistung zum Projizieren einer neuen Auflistung eines anonymen Typs verwenden) ist eine häufig verwendete und sinnvolle Vorgehensweise. Diese Abfrage hätte auch ohne Projizieren in den ersten anonymen Typ geschrieben werden können. Aufgrund der verzögerten Auswertung wird aber nicht allzu viel zusätzliche Rechenleistung beansprucht. Die Ausdrucksweise erstellt zwar mehr kurzlebige Objekte auf dem Heap, dies führt aber nur zu unerheblichen Leistungseinbußen.  
  
 Natürlich wäre es auch möglich, eine einzelne Abfrage zu schreiben, die die Funktionalität zum Abrufen der Absätze, der Formatvorlagen der einzelnen Absätze und des Texts in den Absätzen enthält. Häufig ist es aber sinnvoll, eine kompliziertere Abfrage in mehrere Abfragen aufzuteilen, weil der resultierende Code dann modularer und einfacher zu verwalten ist. Wenn Sie einen Teil der Abfrage wiederverwenden müssen und die Abfragen auf diese Weise geschrieben sind, können Sie den entsprechenden Abfrageteil auch einfacher umgestalten.  
  
 Diese Abfragen, die miteinander verkettet sind, verwenden das Verarbeitungsmodell, das im Thema [Tutorial: verzögerte Ausführung (Visual Basic)](tutorial-deferred-execution.md)ausführlich untersucht wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es den Elementknoten, die Namen der Formatvorlagen und den Text der einzelnen Absätze bestimmt. Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf. Die neue Abfrage wird im Code unten durch entsprechende Kommentare gekennzeichnet.  
  
 Anweisungen zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Erstellen des Quell-Office Open-XML-Dokuments (Visual Basic)](creating-the-source-office-open-xml-document.md).  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    ' Following function is required because Visual Basic does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = _  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
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
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Following is the new query that retrieves the text of  
        ' each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t> _  
                    .Aggregate(New StringBuilder(), _  
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _  
                               Function(s As StringBuilder) s.ToString) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 In diesem Beispiel wird die folgende Ausgabe erzeugt, wenn Sie auf das Dokument angewendet wird, [das unter Erstellen des Open XML-Quelldokuments (Visual Basic)](creating-the-source-office-open-xml-document.md)beschrieben wird.  
  
```console  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >Imports System<  
StyleName:Code ><  
StyleName:Code >Class Program<  
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >   End Sub<  
StyleName:Code >End Class<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a>Nächste Schritte  
 Im nächsten Beispiel wird gezeigt, wie Sie zum Verketten mehrerer Zeichenfolgen zu einer einzelnen Zeichenfolge statt <xref:System.Linq.Enumerable.Aggregate%2A> eine Erweiterungsmethode verwenden können:  
  
- [Refactoring mit einer Erweiterungsmethode (Visual Basic)](refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [Verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
