---
title: 'Gewusst wie: Streamen von XML-Fragmenten aus einem XmlReader'
ms.date: 07/20/2015
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
ms.openlocfilehash: 42d3edb390035d20f506388974000aa204312109
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636795"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="36b2c-102">Gewusst wie: Streamen von XML-Fragmenten aus einem XmlReader-Objekt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36b2c-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="36b2c-103">Wenn Sie große XML-Dateien verarbeiten müssen, kann u. U. nicht die gesamte XML-Struktur in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="36b2c-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="36b2c-104">In diesem Thema wird gezeigt, wie mit einem <xref:System.Xml.XmlReader> Fragmente gestreamt werden können.</span><span class="sxs-lookup"><span data-stu-id="36b2c-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="36b2c-105">Eine der effektivsten Möglichkeiten, einen <xref:System.Xml.XmlReader> zum Lesen von <xref:System.Xml.Linq.XElement>-Objekten zu verwenden, besteht darin, eine eigene benutzerdefinierte Achsenmethode zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="36b2c-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="36b2c-106">Achsenmethoden geben in der Regel eine Auflistung, z. B. die <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> zurück, wie dies im Beispiel in diesem Thema dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="36b2c-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="36b2c-107">Nachdem Sie in der benutzerdefinierten Achsenmethode durch Aufrufen der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode das XML-Fragment erstellt haben, geben Sie die Auflistung mit `yield return` zurück.</span><span class="sxs-lookup"><span data-stu-id="36b2c-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="36b2c-108">Auf diese Weise versehen Sie Ihre benutzerdefinierte Achsenmethode mit der Semantik für eine verzögerte Ausführung.</span><span class="sxs-lookup"><span data-stu-id="36b2c-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="36b2c-109">Wenn Sie eine XML-Struktur auf der Grundlage eines <xref:System.Xml.XmlReader>-Objekts erstellen, muss der <xref:System.Xml.XmlReader> auf einem Element positioniert sein.</span><span class="sxs-lookup"><span data-stu-id="36b2c-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="36b2c-110">Die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode gibt erst dann einen Wert zurück, wenn sie das Endtag des Elements gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="36b2c-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="36b2c-111">Wenn Sie eine Teilstruktur erstellen möchten, können Sie einen <xref:System.Xml.XmlReader> instanziieren, den Reader auf dem Knoten positionieren, der in eine <xref:System.Xml.Linq.XElement>-Struktur umgewandelt werden soll, und dann das <xref:System.Xml.Linq.XElement>-Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="36b2c-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="36b2c-112">Das Thema Gewusst [wie: Streamen von XML-Fragmenten mit Zugriff auf Header Informationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) enthält Informationen und ein Beispiel für das Streamen eines komplexeren Dokuments.</span><span class="sxs-lookup"><span data-stu-id="36b2c-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="36b2c-113">Das Thema Gewusst [wie: Durchführen einer streamingtransformation großer XML-Dokumente (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) enthält ein Beispiel für die Verwendung von LINQ to XML, um extrem große XML-Dokumente zu transformieren und gleichzeitig einen geringen Speicherbedarf zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="36b2c-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36b2c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36b2c-114">Example</span></span>  
 <span data-ttu-id="36b2c-115">Dieses Beispiel erstellt eine benutzerdefinierte Achsenmethode.</span><span class="sxs-lookup"><span data-stu-id="36b2c-115">This example creates a custom axis method.</span></span> <span data-ttu-id="36b2c-116">Sie können Sie mithilfe einer LINQ-Abfrage Abfragen.</span><span class="sxs-lookup"><span data-stu-id="36b2c-116">You can query it by using a LINQ query.</span></span> <span data-ttu-id="36b2c-117">Die benutzerdefinierte Achsenmethode `StreamRootChildDoc` eignet sich vor allem zum Lesen eines Dokuments, das ein sich wiederholendes `Child`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="36b2c-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim markup = "<Root>" &  
                     "  <Child Key=""01"">" &  
                     "    <GrandChild>aaa</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""02"">" &  
                     "    <GrandChild>bbb</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""03"">" &  
                     "    <GrandChild>ccc</GrandChild>" &  
                     "  </Child>" &  
                     "</Root>"  
  
        Dim grandChildData =  
             From el In New StreamRootChildDoc(New IO.StringReader(markup))  
             Where CInt(el.@Key) > 1  
             Select el.<GrandChild>.Value  
  
        For Each s In grandChildData  
            Console.WriteLine(s)  
        Next  
    End Sub  
End Module  
  
Public Class StreamRootChildDoc  
    Implements IEnumerable(Of XElement)  
  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamChildEnumerator(_stringReader)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamChildEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _reader As Xml.XmlReader  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        While _reader.Read()  
            Select Case _reader.NodeType  
                Case Xml.XmlNodeType.Element  
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)  
                    If el IsNot Nothing Then  
                        _current = el  
                        Return True  
                    End If  
            End Select  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="36b2c-118">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="36b2c-118">This example produces the following output:</span></span>  
  
```console  
bbb  
ccc  
```  
  
 <span data-ttu-id="36b2c-119">In diesem Beispiel ist das Quelldokument sehr klein.</span><span class="sxs-lookup"><span data-stu-id="36b2c-119">In this example, the source document is very small.</span></span> <span data-ttu-id="36b2c-120">Dieses Beispiel würde aber auch dann wenig Speicher beanspruchen, wenn das Quelldokument Millionen `Child`-Elemente enthielte.</span><span class="sxs-lookup"><span data-stu-id="36b2c-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b2c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36b2c-121">See also</span></span>

- [<span data-ttu-id="36b2c-122">Exemplarische Vorgehensweise: Implementieren von IEnumerable (of T) in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="36b2c-122">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)
- [<span data-ttu-id="36b2c-123">XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36b2c-123">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
