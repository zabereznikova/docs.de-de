---
title: Umgestalten mit einer Erweiterungsmethode
ms.date: 07/20/2015
ms.assetid: d87ae99a-cfa9-4a31-a5e4-9d6437be6810
ms.openlocfilehash: c66fb90f9949ee3e47105498b211c857d5d63804
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348019"
---
# <a name="refactoring-using-an-extension-method-visual-basic"></a><span data-ttu-id="5e2e6-102">Refactoring mit einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e2e6-102">Refactoring Using an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="5e2e6-103">Dieses Beispiel baut auf dem vorherigen Beispiel auf und [Ruft den Text der Absätze (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)ab, indem die Verkettung von Zeichen folgen mit einer reinen Funktion, die als Erweiterungsmethode implementiert ist, umgestaltet wird.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-103">This example builds on the previous example, [Retrieving the Text of the Paragraphs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="5e2e6-104">Im vorherigen Beispiel wurde zum Verketten mehrerer Zeichenfolgen zu einer Zeichenfolge der <xref:System.Linq.Enumerable.Aggregate%2A>-Standardabfrageoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-104">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="5e2e6-105">Bequemer ist es aber, dafür eine Erweiterungsmethode zu schreiben, weil die Abfrage dadurch kleiner und einfacher wird.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-105">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e2e6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2e6-106">Example</span></span>  
 <span data-ttu-id="5e2e6-107">Dieses Beispiel verarbeitet ein WordprocessingML-Dokument, indem es die Absätze, die Formatvorlagen der Absätze und den Text der einzelnen Absätze abruft.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-107">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="5e2e6-108">Das Beispiel baut auf den vorherigen Beispielen dieses Lernprogramms auf.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-108">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="5e2e6-109">Das Beispiel enthält mehrere Überladungen der `StringConcatenate`-Methode.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-109">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="5e2e6-110">Anweisungen zum Erstellen des Quelldokuments für dieses Beispiel finden Sie unter [Erstellen des Office Open XML-Quelldokuments (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="5e2e6-110">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="5e2e6-111">Dieses Beispiel verwendet Klassen aus der <legacyBold>WindowsBase</legacyBold>-Assembly.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="5e2e6-112">Außerdem werden Typen im <xref:System.IO.Packaging?displayProperty=nameWithType>-Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="5e2e6-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2e6-113">Example</span></span>  
 <span data-ttu-id="5e2e6-114">Es gibt vier Überladungen der `StringConcatenate`-Methode.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-114">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="5e2e6-115">Eine Überladung nimmt einfach eine Auflistung von Zeichenfolgen und gibt eine einzelne Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-115">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="5e2e6-116">Eine andere Überladung kann eine Auflistung eines beliebigen Typs und einen Delegat nehmen, der von einem Singleton der Auflistung in eine Zeichenfolge projiziert.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-116">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="5e2e6-117">Es gibt zwei weitere Überladungen, die es Ihnen ermöglichen, eine Trennzeichenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-117">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="5e2e6-118">Der folgende Code verwendet alle vier Überladungen:</span><span class="sxs-lookup"><span data-stu-id="5e2e6-118">The following code uses all four overloads.</span></span>  
  
```vb  
Dim numbers As String() = {"one", "two", "three"}  
  
Console.WriteLine("{0}", numbers.StringConcatenate())  
Console.WriteLine("{0}", numbers.StringConcatenate(":"))  
  
Dim intNumbers As Integer() = {1, 2, 3}  
Console.WriteLine("{0}", intNumbers.StringConcatenate(Function(i) i.ToString()))  
Console.WriteLine("{0}", intNumbers.StringConcatenate(Function(i) i.ToString(), ":"))  
```  
  
 <span data-ttu-id="5e2e6-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5e2e6-119">This example produces the following output:</span></span>  
  
```console  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="5e2e6-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2e6-120">Example</span></span>  
 <span data-ttu-id="5e2e6-121">Jetzt kann das Beispiel so geändert werden, dass es die neue Erweiterungsmethode nutzt:</span><span class="sxs-lookup"><span data-stu-id="5e2e6-121">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
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
  
 <span data-ttu-id="5e2e6-122">In diesem Beispiel wird die folgende Ausgabe erzeugt, wenn Sie auf das Dokument angewendet wird, [das unter Erstellen des Open XML-Quelldokuments (Visual Basic)](creating-the-source-office-open-xml-document.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](creating-the-source-office-open-xml-document.md).</span></span>
  
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
  
 <span data-ttu-id="5e2e6-123">Beachten Sie, dass dieses Refactoring eine Variante des Refactorings in eine reine Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-123">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="5e2e6-124">Das Umgestalten in reine Funktionen wird im nächsten Thema ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="5e2e6-124">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5e2e6-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5e2e6-125">Next Steps</span></span>  
 <span data-ttu-id="5e2e6-126">Im nächsten Beispiel wird gezeigt, wie dieser Code durch Verwendung von reinen Funktionen umgestaltet werden kann:</span><span class="sxs-lookup"><span data-stu-id="5e2e6-126">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
- [<span data-ttu-id="5e2e6-127">Refactoring mit reiner Funktion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e2e6-127">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)  
  
## <a name="see-also"></a><span data-ttu-id="5e2e6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e2e6-128">See also</span></span>

- [<span data-ttu-id="5e2e6-129">Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e2e6-129">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [<span data-ttu-id="5e2e6-130">Refactoring in reine Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e2e6-130">Refactoring Into Pure Functions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
