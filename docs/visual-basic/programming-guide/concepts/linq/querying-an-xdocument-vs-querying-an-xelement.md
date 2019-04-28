---
title: Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen ein "XElement" (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
ms.openlocfilehash: 500b1e58663ef6aca052850ad7994687e2cc36f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766492"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a>Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen ein "XElement" (Visual Basic)
Das Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> geladen werden, unterscheidet sich geringfügig vom Schreiben von Abfragen für Dokumente, die über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> geladen werden.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Vergleich zwischen "XDocument.Load" und "XElement.Load"  
 Beim Laden eines XML-Dokuments in ein <xref:System.Xml.Linq.XElement> über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> enthält das <xref:System.Xml.Linq.XElement> am Stamm der XML-Struktur das Stammelement des geladenen Dokuments. Wenn Sie jedoch dasselbe XML-Dokument über <xref:System.Xml.Linq.XDocument> in ein <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> laden, ist der Stamm der Struktur ein <xref:System.Xml.Linq.XDocument>-Knoten, und das Stammelement des geladenen Dokuments ist der einzige zulässige untergeordnete <xref:System.Xml.Linq.XElement>-Knoten des <xref:System.Xml.Linq.XDocument>. Die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen agieren relativ zum Stammknoten.  
  
 Dieses erstes Beispiel lädt eine XML-Struktur mit <xref:System.Xml.Linq.XElement.Load%2A>. Anschließend fragt es die untergeordneten Elemente des Stamms der Struktur ab:  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Wie zu erwarten, erzeugt dieses Beispiel die folgende Ausgabe:  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 Das folgende Beispiel entspricht dem vorhergehenden Beispiel, wobei hier die XML-Struktur nicht in ein <xref:System.Xml.Linq.XDocument>, sondern in ein <xref:System.Xml.Linq.XElement> geladen wird:  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 Dieselbe Abfrage hat also diesmal nicht die drei untergeordneten Knoten, sondern den einen `Root`-Knoten zurückgegeben.  
  
 Ein Ansatz für den Umgang mit diesem Verhalten besteht darin, vor dem Zugreifen auf die Achsenmethoden die <xref:System.Xml.Linq.XDocument.Root%2A>-Eigenschaft zu verwenden, wie im folgenden Beispiel gezeigt:  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Diese Abfrage ist jetzt genauso schnell wie die Abfrage für die Struktur mit dem <xref:System.Xml.Linq.XElement> als Stammelement. Das Beispiel führt zur folgenden Ausgabe:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Standardabfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
