---
title: "Gewusst wie: Durchführen einer Streamingtransformation großer XML-Dokumente (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 3d954cc9-4b3c-4b47-8132-ff7541cff53b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 730039a85c8c72b9379617cb4b3c019028c3a1e9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-visual-basic"></a><span data-ttu-id="1010d-102">Gewusst wie: Durchführen einer Streamingtransformation großer XML-Dokumente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1010d-102">How to: Perform Streaming Transform of Large XML Documents (Visual Basic)</span></span>
<span data-ttu-id="1010d-103">Es kann vorkommen, dass Sie große XML-Dateien transformieren und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist.</span><span class="sxs-lookup"><span data-stu-id="1010d-103">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="1010d-104">Wenn Sie versuchen, eine XML-Struktur mit einer sehr großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv.</span><span class="sxs-lookup"><span data-stu-id="1010d-104">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="1010d-105">Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="1010d-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="1010d-106">Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten.</span><span class="sxs-lookup"><span data-stu-id="1010d-106">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="1010d-107">Einige Standardabfrageoperatoren, wie z. B. <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, Sortieren sie und geben schließlich das erste Element in der Sequenz.</xref:System.Linq.Enumerable.OrderBy%2A></span><span class="sxs-lookup"><span data-stu-id="1010d-107">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="1010d-108">Beachten Sie, dass Sie bei der Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, keine minimale Speicherbeanspruchung für Ihre Anwendung aufrechterhalten können.</span><span class="sxs-lookup"><span data-stu-id="1010d-108">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
 <span data-ttu-id="1010d-109">Auch wenn Sie das beschriebene Verfahren verwenden [How to: Stream XML-Fragmenten mit Zugriff auf Headerinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md), wenn Sie versuchen, eine XML-Struktur zusammensetzen, das die transformierten Dokuments Speicher wird zu groß sein.</span><span class="sxs-lookup"><span data-stu-id="1010d-109">Even if you use the technique described in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>  
  
 <span data-ttu-id="1010d-110">Es gibt im Wesentlichen zwei Lösungsansätze:</span><span class="sxs-lookup"><span data-stu-id="1010d-110">There are two main approaches.</span></span> <span data-ttu-id="1010d-111">Ein Ansatz besteht darin, die verzögerte Verarbeitung Merkmale <xref:System.Xml.Linq.XStreamingElement>.</xref:System.Xml.Linq.XStreamingElement> verwenden</span><span class="sxs-lookup"><span data-stu-id="1010d-111">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="1010d-112">Ein anderer Ansatz ist die Erstellung einer <xref:System.Xml.XmlWriter>, und verwenden Sie die Funktionen der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Elemente geschrieben werden, um eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="1010d-112">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="1010d-113">In diesem Thema werden beide Ansätze besprochen.</span><span class="sxs-lookup"><span data-stu-id="1010d-113">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1010d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1010d-114">Example</span></span>  
 <span data-ttu-id="1010d-115">Das folgende Beispiel baut auf dem Beispiel in [How to: Stream XML-Fragmenten mit Zugriff auf Headerinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="1010d-115">The following example builds on the example in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="1010d-116">In diesem Beispiel wird die verzögerte Ausführung von <xref:System.Xml.Linq.XStreamingElement>um die Ausgabe zu streamen.</xref:System.Xml.Linq.XStreamingElement></span><span class="sxs-lookup"><span data-stu-id="1010d-116">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="1010d-117">Damit kann auch ein sehr großes Dokument transformiert werden, ohne dass die Speicherbeanspruchung zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="1010d-117">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="1010d-118">Beachten Sie, dass die benutzerdefinierte Achse (`StreamCustomerItem`) so geschrieben ist, dass sie über ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen verfügt. Diese Elemente werden wie im folgenden Source.xml-Dokument angeordnet.</span><span class="sxs-lookup"><span data-stu-id="1010d-118">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="1010d-119">Eine robustere Implementierung würde jedoch darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.</span><span class="sxs-lookup"><span data-stu-id="1010d-119">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="1010d-120">Das Quelldokument (<legacyBold>Source.xml</legacyBold>) sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1010d-120">The following is the source document, Source.xml:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>   
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root = New XStreamingElement("Root",  
            From el In New StreamCustomerItem("Source.xml")  
            Select <Item>  
                       <Customer><%= el.Parent.<Name>.Value %></Customer>  
                       <%= el.<Key> %>  
                   </Item>  
            )  
        root.Save("Test.xml")  
        Console.WriteLine(My.Computer.FileSystem.ReadAllText("Test.xml"))  
    End Sub  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
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
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
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
  
 <span data-ttu-id="1010d-121">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1010d-121">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="1010d-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1010d-122">Example</span></span>  
 <span data-ttu-id="1010d-123">Das folgende Beispiel baut ebenfalls auf dem Beispiel in [How to: Stream XML-Fragmenten mit Zugriff auf Headerinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="1010d-123">The following example also builds on the example in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="1010d-124">In diesem Beispiel wird die Fähigkeit von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Elemente in einer <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> schreiben</span><span class="sxs-lookup"><span data-stu-id="1010d-124">This example uses the capability of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="1010d-125">Damit kann auch ein sehr großes Dokument transformiert werden, ohne dass die Speicherbeanspruchung zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="1010d-125">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="1010d-126">Beachten Sie, dass die benutzerdefinierte Achse (`StreamCustomerItem`) so geschrieben ist, dass sie über ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen verfügt. Diese Elemente werden wie im folgenden Source.xml-Dokument angeordnet.</span><span class="sxs-lookup"><span data-stu-id="1010d-126">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="1010d-127">Eine robustere Implementierung würde jedoch entweder das Quelldokument mit einer XSD prüfen oder darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.</span><span class="sxs-lookup"><span data-stu-id="1010d-127">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="1010d-128">In diesem Beispiel wird das gleiche Quelldokument (<legacyBold>Source.xml</legacyBold>) wie im Beispiel oben verwendet.</span><span class="sxs-lookup"><span data-stu-id="1010d-128">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="1010d-129">Es erzeugt auch genau die gleiche Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1010d-129">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="1010d-130">Verwenden <xref:System.Xml.Linq.XStreamingElement>für das Ausgabe-XML-Code zu schreiben, eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> bevorzugte ist streaming</xref:System.Xml.Linq.XStreamingElement></span><span class="sxs-lookup"><span data-stu-id="1010d-130">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim srcTree =  
            From el In New StreamCustomerItem("Source.xml")  
            Select <Item>  
                       <Customer><%= el.Parent.<Name>.Value %></Customer>  
                       <%= el.<Key> %>  
                   </Item>  
  
        Dim xws = New Xml.XmlWriterSettings()  
        xws.OmitXmlDeclaration = True  
        xws.Indent = True  
        Using xw = Xml.XmlWriter.Create("Output.xml", xws)  
            xw.WriteStartElement("Root")  
            For Each el In srcTree  
                el.WriteTo(xw)  
            Next  
            xw.WriteEndElement()  
        End Using  
  
        Dim s = My.Computer.FileSystem.ReadAllText("Output.xml")  
        Console.WriteLine(s)  
    End Sub  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
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
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
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
  
 <span data-ttu-id="1010d-131">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1010d-131">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1010d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1010d-132">See Also</span></span>  
 [<span data-ttu-id="1010d-133">Erweiterte LINQ to XML-Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1010d-133">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
