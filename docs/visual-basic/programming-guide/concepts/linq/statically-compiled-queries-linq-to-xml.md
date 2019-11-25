---
title: Statisch kompilierte Abfragen (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: e9f56366f1566f831f1e0ea5bd5a06775d698c3d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350581"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Statically Compiled Queries (LINQ to XML) (Visual Basic)

Einer der wichtigsten Leistungsvorteile von LINQ to XML (im Unterschied zu <xref:System.Xml.XmlDocument>) besteht darin, dass Abfragen in LINQ to XML statisch kompiliert werden. XPath-Abfragen müssen dagegen zur Laufzeit interpretiert werden. Diese Funktion ist in LINQ to XML integriert, sodass Sie keine zusätzlichen Schritte ausführen müssen, um diesen Vorteil zu nutzen. Es ist jedoch hilfreich, den Unterschied zu verstehen, wenn Sie eine Auswahl zwischen den beiden Technologien treffen. In diesem Thema wird der Unterschied erklärt.

## <a name="statically-compiled-queries-vs-xpath"></a>Statisch kompilierte Abfragen im Vergleich zu XPath

Im folgenden Beispiel wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.

Hier folgt der entsprechende XPath-Ausdruck:

```vb
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

Die <xref:System.Linq.Enumerable.Where%2A>-Methode ist eine Erweiterungsmethode. Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Da <xref:System.Linq.Enumerable.Where%2A> eine Erweiterungsmethode ist, wird die obige Abfrage kompiliert, als wäre sie wie folgt geschrieben:

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Dieses Beispiel führt zu genau den gleichen Ergebnissen wie die beiden vorherigen Beispiele. Dies veranschaulicht die Tatsache, dass Abfragen tatsächlich zu statisch verknüpften Methodenaufrufen kompiliert werden. Hierdurch wird, gemeinsam mit der verzögerten Ausführungssemantik von Iteratoren, die Leistung verbessert. For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

> [!NOTE]
> Diese Beispiele sind für den Code repräsentativ, der möglicherweise vom Compiler geschrieben wird. Die tatsächliche Implementierung kann in Details von diesen Beispielen abweichen, die Leistung wird jedoch weitgehend mit der dieser Beispiele übereinstimmen.

## <a name="executing-xpath-expressions-with-xmldocument"></a>Ausführen von XPath-Ausdrücken mit XmlDocument

Im folgenden Beispiel erhalten Sie mit <xref:System.Xml.XmlDocument> dieselben Ergebnisse wie in den vorherigen Beispielen:

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

Diese Abfrage gibt dieselbe Ausgabe wie die Beispiele mit LINQ to XML zurück. Der einzige Unterschied ist, dass LINQ to XML das gedruckte XML im Gegensatz zu <xref:System.Xml.XmlDocument> einrückt.

Der <xref:System.Xml.XmlDocument>-Ansatz bietet in der Regel nicht die Leistung von LINQ to XML, da die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode bei jedem Aufruf intern die folgenden Schritte ausführen muss:

- Analysieren der Zeichenfolge, die den XPath-Ausdruck enthält, und Zerlegen der Zeichenfolge in Token.

- Überprüfen der Token, um sicherzustellen, dass der XPath-Ausdruck gültig ist.

- Übersetzen des Ausdrucks in eine interne Ausdrucksstruktur.

- Durchlaufen der Knoten und entsprechendes Auswählen der Knoten für das Resultset auf Grundlage der Ausdrucksauswertung.

Dies sind bedeutend mehr Arbeitsschritte als bei einer entsprechenden LINQ to XML-Abfrage. Die genauen Leistungsunterschiede variieren je nach Abfragetyp, in der Regel müssen LINQ to XML-Abfragen jedoch weniger Arbeitsschritte ausführen und bieten daher eine bessere Leistung als das Auswerten von XPath-Ausdrücken mit <xref:System.Xml.XmlDocument>.

## <a name="see-also"></a>Siehe auch

- [Performance (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
