---
title: Vergleich zwischen dem Abfragen eines &quot;XDocument&quot; und dem Abfragen ein &quot;XElement&quot; (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 29044cd118bfd8ecc12bddca722ee3656d455e0f
ms.lasthandoff: 03/13/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a>Vergleich zwischen dem Abfragen eines "XDocument" und dem Abfragen ein "XElement" (Visual Basic)
Wenn Sie ein Dokument über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, werden Sie feststellen, dass Sie etwas anders als beim Laden über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> Abfragen schreiben müssen,</xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> laden  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Vergleich zwischen "XDocument.Load" und "XElement.Load"  
 Beim Laden eines XML-Dokuments in ein <xref:System.Xml.Linq.XElement>über <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, die <xref:System.Xml.Linq.XElement>am Stamm der XML-Struktur das Stammelement des geladenen Dokuments enthält.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement> Allerdings laden Wenn Sie dasselbe XML-Dokument in eine <xref:System.Xml.Linq.XDocument>über <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>den Stamm der Struktur ist ein <xref:System.Xml.Linq.XDocument>Knoten, und das Stammelement des geladenen Dokuments ist der einen zulässigen untergeordneten <xref:System.Xml.Linq.XElement>Knoten des <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> Die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achsen agieren relativ zum Stammknoten.  
  
 Dieses erstes Beispiel lädt eine XML-Struktur mithilfe von <xref:System.Xml.Linq.XElement.Load%2A>.</xref:System.Xml.Linq.XElement.Load%2A> Anschließend fragt es die untergeordneten Elemente des Stamms der Struktur ab:  
  
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
  
 Im folgende Beispiel wird der gleiche wie der oben mit der Ausnahme, dass die XML-Struktur in eine <xref:System.Xml.Linq.XDocument>anstelle einer <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> geladen wird  
  
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
  
 Ein Ansatz für den Umgang mit diesem Verhalten ist die Verwendung der <xref:System.Xml.Linq.XDocument.Root%2A>Eigenschaft vor dem Zugriff auf die Achsenmethoden wie folgt:</xref:System.Xml.Linq.XDocument.Root%2A>  
  
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
  
 Diese Abfrage führt jetzt in der gleichen Weise wie die Abfrage für die Struktur als Stamm <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> Das Beispiel führt zur folgenden Ausgabe:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Standardabfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
