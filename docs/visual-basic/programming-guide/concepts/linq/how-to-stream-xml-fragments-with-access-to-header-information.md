---
title: 'Gewusst wie: Streamen von XML-Fragmenten in Headerinformationen'
ms.date: 07/20/2015
ms.assetid: effd10df-87c4-4d7a-8a9a-1434d829dca5
ms.openlocfilehash: 489e128e86a47e0e7f76c14a6cf1baf80fb0c406
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332452"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-visual-basic"></a>Gewusst wie: Streamen von XML-Fragmenten mit Zugriff auf Header Informationen (Visual Basic)
Es kann vorkommen, dass Sie willkürlich große XML-Dateien lesen und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist. Wenn Sie versuchen, eine XML-Struktur mit einer großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv. Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.  
  
 Zu diesem Zweck können Sie die Anwendung mit <xref:System.Xml.XmlReader> schreiben. Es empfiehlt sich aber häufig, zum Abfragen der XML-Struktur [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] zu verwenden. Bei Verwendung von {1} können Sie eine eigene benutzerdefinierte Achsenmethode schreiben. Weitere Informationen finden Sie unter Gewusst [wie: Schreiben einer LINQ to XML Achsen Methode (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).  
  
 Zum Schreiben einer eigenen Achsenmethode müssen Sie zunächst eine kleine Methode schreiben, die mit dem <xref:System.Xml.XmlReader> Knoten so lange liest, bis sie zu einem der Knoten gelangt, die Sie interessieren. Die Methode ruft dann die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode auf, die aus dem <xref:System.Xml.XmlReader> liest und ein XML-Fragment instanziiert. Sie können dann LINQ-Abfragen für die benutzerdefinierte Achsenmethode schreiben.  
  
 Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten. Einige Standardabfrageoperatoren, wie <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, sortieren sie und geben dann das erste Element in der Sequenz zurück. Beachten Sie, dass Sie bei der Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, keine minimale Speicherbeanspruchung aufrechterhalten können.  
  
## <a name="example"></a>Beispiel  
 Manchmal wird das Problem noch ein wenig interessanter. Im folgenden XML-Dokument muss der Benutzer Ihrer benutzerdefinierten Achsenmethode auch die Namen der Kunden kennen, zu denen die einzelnen Elemente gehören.  
  
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
  
 Dieses Beispiel sucht auch nach diesen Headerinformationen, speichert sie und konstruiert dann eine kleine XML-Struktur, die sowohl die Headerinformationen als auch die Detailinformationen enthält, die von Ihnen aufgezählt werden. Die Achsenmethode gibt daraufhin diese neue, kleine XML-Struktur zurück. Die Abfrage verfügt damit sowohl über Zugriff auf die Headerinformationen als auch über Zugriff auf die Detailinformationen.  
  
 Dieser Ansatz führt zu einer geringen Speicherbeanspruchung. Da jedes XML-Detailfragment zurückgegeben wird, bleiben keine Verweise auf vorherige Fragmente erhalten. Es steht damit für die Garbage Collection (automatische Speicherbereinigung) zur Verfügung. Beachten Sie, dass bei diesem Verfahren viele kurzlebige Objekte auf dem Heap erstellt werden.  
  
 Im folgenden Beispiel wird die Vorgehensweise bei der Implementierung und Verwendung einer benutzerdefinierten Achsenmethode gezeigt, die XML-Fragmente aus der durch den URI angegebenen Datei streamt. Diese benutzerdefinierte Achse ist so geschrieben, dass sie ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen erwartet. Diese Elemente werden wie im Dokument `Source.xml` oben angeordnet. Dabei handelt es sich um eine eher einfache Implementierung. Eine robustere Implementierung würde darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim xmlTree = <Root>  
                          <%=  
                              From el In New StreamCustomerItem("Source.xml")  
                              Let itemKey = CInt(el.<Key>.Value)  
                              Where itemKey >= 3 AndAlso itemKey <= 7  
                              Select <Item>  
                                         <Customer><%= el.Parent.<Name>.Value %></Customer>  
                                         <%= el.<Key> %>  
                                     </Item>  
                          %>  
                      </Root>  
  
        Console.WriteLine(xmlTree)  
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
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
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
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterte LINQ to XML Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
