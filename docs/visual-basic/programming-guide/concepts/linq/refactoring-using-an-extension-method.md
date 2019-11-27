---
title: Umgestalten mit einer Erweiterungsmethode
ms.date: 07/20/2015
ms.assetid: d87ae99a-cfa9-4a31-a5e4-9d6437be6810
ms.openlocfilehash: 1045a649907f877bddd0ec2d8c0e5dfa2a5d0830
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346507"
---
# <a name="refactoring-using-an-extension-method-visual-basic"></a>Refactoring mit einer Erweiterungsmethode (Visual Basic)
Dieses Beispiel baut auf dem vorherigen Beispiel auf und [Ruft den Text der Absätze (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)ab, indem die Verkettung von Zeichen folgen mit einer reinen Funktion, die als Erweiterungsmethode implementiert ist, umgestaltet wird.  
  
 Im vorherigen Beispiel wurde zum Verketten mehrerer Zeichenfolgen zu einer Zeichenfolge der <xref:System.Linq.Enumerable.Aggregate%2A>-Standardabfrageoperator verwendet. Bequemer ist es aber, dafür eine Erweiterungsmethode zu schreiben, weil die Abfrage dadurch kleiner und einfacher wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absätze, die Formatvorlagen der Absätze und den Text der einzelnen Absätze abruft. Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.  
  
 Das Beispiel enthält mehrere Überladungen der `StringConcatenate`-Methode.  
  
 Anweisungen zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Erstellen des Office Open XML-Quelldokuments (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly. Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.  
  
```vb  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each s As String In source  
        sb.Append(s)  
    Next  
    Return sb.ToString()  
End Function  
  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
ByVal func As Func(Of T, String)) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each item As T In source  
        sb.Append(func(item))  
    Next  
    Return sb.ToString()  
End Function  
  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
ByVal separator As String) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each s As T In source  
        sb.Append(s).Append(separator)  
    Next  
    Return sb.ToString()  
End Function  
  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
ByVal func As Func(Of T, String), ByVal separator As String) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each item As T In source  
        sb.Append(func(item)).Append(separator)  
    Next  
    Return sb.ToString()  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Es gibt vier Überladungen der `StringConcatenate`-Methode. Eine Überladung nimmt einfach eine Auflistung von Zeichenfolgen und gibt eine einzelne Zeichenfolge zurück. Eine andere Überladung kann eine Auflistung eines beliebigen Typs und einen Delegat nehmen, der von einem Singleton der Auflistung in eine Zeichenfolge projiziert. Es gibt zwei weitere Überladungen, die es Ihnen ermöglichen, eine Trennzeichenfolge anzugeben.  
  
 Der folgende Code verwendet alle vier Überladungen:  
  
```vb  
Dim numbers As String() = {"one", "two", "three"}  
  
Console.WriteLine("{0}", numbers.StringConcatenate())  
Console.WriteLine("{0}", numbers.StringConcatenate(":"))  
  
Dim intNumbers As Integer() = {1, 2, 3}  
Console.WriteLine("{0}", intNumbers.StringConcatenate(Function(i) i.ToString()))  
Console.WriteLine("{0}", intNumbers.StringConcatenate(Function(i) i.ToString(), ":"))  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a>Beispiel  
 Jetzt kann das Beispiel so geändert werden, dass es die neue Erweiterungsmethode nutzt:  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As String In source  
            sb.Append(s)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item))  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As T In source  
            sb.Append(s).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String), ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item)).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    ' Following function is required because VB does not support short circuit evaluation  
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
  
        ' Retrieve the text of each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t>.StringConcatenate(Function(e) CStr(e)) _  
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
  
 Beachten Sie, dass dieses Refactoring eine Variante des Refactorings in eine reine Funktion ist. Das Umgestalten in reine Funktionen wird im nächsten Thema ausführlicher erläutert.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Im nächsten Beispiel wird gezeigt, wie dieser Code durch Verwendung von reinen Funktionen umgestaltet werden kann:  
  
- [Refactoring mit reiner Funktion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)  
  
## <a name="see-also"></a>Siehe auch

- [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [Refactoring in reine Funktionen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
