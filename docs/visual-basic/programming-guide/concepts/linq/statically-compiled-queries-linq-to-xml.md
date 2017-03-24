---
title: Statisch kompilierte Abfragen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ea8e71acf861b93a21296c74254b3ca4d977d0a
ms.lasthandoff: 03/13/2017


---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Statisch kompilierte Abfragen (LINQ to XML) (Visual Basic)
Eine der wichtigsten Leistungsvorteile von LINQ to XML, im Gegensatz zur <xref:System.Xml.XmlDocument>, sind Abfragen in LINQ to XML statisch kompiliert wird, während die XPath-Abfragen zur Laufzeit interpretiert werden müssen.</xref:System.Xml.XmlDocument> Diese Funktion ist in LINQ to XML integriert, sodass Sie keine zusätzlichen Schritte ausführen müssen, um diesen Vorteil zu nutzen. Es ist jedoch hilfreich, den Unterschied zu verstehen, wenn Sie eine Auswahl zwischen den beiden Technologien treffen. In diesem Thema wird der Unterschied erklärt.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>Statisch kompilierte Abfragen und XPath  
 Im folgenden Beispiel wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.  
  
 Hier folgt der entsprechende XPath-Ausdruck:  
  
```  
//Address[@Type='Shipping']  
```  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = From el In po.Descendants("Address")  
            Where el.@Type = "Shipping"  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
  
```  
  
 Der Abfrageausdruck in diesem Beispiel wird vom Compiler in eine methodenbasierte Abfragesyntax umgeschrieben. Das folgende in methodenbasierter Abfragesyntax geschriebene Beispiel führt zum selben Ergebnis wie das vorherige Beispiel:  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next   
```  
  
 Die <xref:System.Linq.Enumerable.Where%2A>Methode ist eine Erweiterungsmethode.</xref:System.Linq.Enumerable.Where%2A> Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Da <xref:System.Linq.Enumerable.Where%2A>ist eine Erweiterungsmethode, die obige Abfrage kompiliert, als wäre es wie folgt geschrieben:</xref:System.Linq.Enumerable.Where%2A>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Dieses Beispiel führt zu genau den gleichen Ergebnissen wie die beiden vorherigen Beispiele. Dies veranschaulicht die Tatsache, dass Abfragen tatsächlich zu statisch verknüpften Methodenaufrufen kompiliert werden. Hierdurch wird, gemeinsam mit der verzögerten Ausführungssemantik von Iteratoren, die Leistung verbessert. Weitere Informationen zu der verzögerten Ausführungssemantik von Iteratoren, finden Sie unter [verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
> [!NOTE]
>  Diese Beispiele sind für den Code repräsentativ, der möglicherweise vom Compiler geschrieben wird. Die tatsächliche Implementierung kann in Details von diesen Beispielen abweichen, die Leistung wird jedoch weitgehend mit der dieser Beispiele übereinstimmen.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>Ausführen von XPath-Ausdrücken mit XmlDocument  
 Im folgenden Beispiel wird <xref:System.Xml.XmlDocument>um dieselben Ergebnisse wie in den vorherigen Beispielen:</xref:System.Xml.XmlDocument>  
  
```vb  
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")  
Dim doc As New Xml.XmlDocument()  
doc.Load(reader)  
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")  
For Each n As Xml.XmlNode In nl  
    Console.WriteLine(n.OuterXml)  
Next  
reader.Close()  
  
```  
  
 Diese Abfrage gibt dieselbe Ausgabe wie die Beispiele mit LINQ to XML zurück. der einzige Unterschied ist, dass LINQ to XML das gedruckte XML zieht, während <xref:System.Xml.XmlDocument>nicht.</xref:System.Xml.XmlDocument>  
  
 Allerdings die <xref:System.Xml.XmlDocument>Ansatz in der Regel ist nicht so gut wie LINQ to XML, da die <xref:System.Xml.XmlNode.SelectNodes%2A>Methode führen die folgenden intern jedes Mal, wenn sie aufgerufen wird:</xref:System.Xml.XmlNode.SelectNodes%2A> </xref:System.Xml.XmlDocument>  
  
-   Analysieren der Zeichenfolge, die den XPath-Ausdruck enthält, und Zerlegen der Zeichenfolge in Token.  
  
-   Überprüfen der Token, um sicherzustellen, dass der XPath-Ausdruck gültig ist.  
  
-   Übersetzen des Ausdrucks in eine interne Ausdrucksstruktur.  
  
-   Durchlaufen der Knoten und entsprechendes Auswählen der Knoten für das Resultset auf Grundlage der Ausdrucksauswertung.  
  
 Dies sind bedeutend mehr Arbeitsschritte als bei einer entsprechenden LINQ to XML-Abfrage. Die genauen Leistungsunterschiede variiert für verschiedene Arten von Abfragen, aber im Allgemeinen LINQ to XML-Abfragen jedoch weniger Arbeitsschritte und daher besser als das Auswerten von XPath-Ausdrücken mit <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> ausführen.  
  
## <a name="see-also"></a>Siehe auch  
 [Leistung (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
