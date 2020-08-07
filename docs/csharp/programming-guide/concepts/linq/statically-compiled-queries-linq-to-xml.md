---
title: Statisch kompilierte Abfragen (LINQ to XML) (C#)
description: Erfahren Sie mehr über statisch kompilierte Abfragen in LINQ to XML in C# und darüber, wie diese sich von XPath-Abfragen unterscheiden, die zur Laufzeit interpretiert werden müssen.
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: cd2e6a6507311d5fc17215a22c70bd0449292b6f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302307"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a>Statisch kompilierte Abfragen (LINQ to XML) (C#)
Einer der wichtigsten Leistungsvorteile von LINQ to XML (im Unterschied zu <xref:System.Xml.XmlDocument>) besteht darin, dass Abfragen in LINQ to XML statisch kompiliert werden. XPath-Abfragen müssen dagegen zur Laufzeit interpretiert werden. Diese Funktion ist in LINQ to XML integriert, sodass Sie keine zusätzlichen Schritte ausführen müssen, um diesen Vorteil zu nutzen. Es ist jedoch hilfreich, den Unterschied zu verstehen, wenn Sie eine Auswahl zwischen den beiden Technologien treffen. In diesem Thema wird der Unterschied erklärt.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>Statisch kompilierte Abfragen und XPath  
 Im folgenden Beispiel wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.  
  
 Im Folgenden finden Sie den entsprechenden XPath-Ausdruck: `//Address[@Type='Shipping']`
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Der Abfrageausdruck in diesem Beispiel wird vom Compiler in eine methodenbasierte Abfragesyntax umgeschrieben. Das folgende in methodenbasierter Abfragesyntax geschriebene Beispiel führt zum selben Ergebnis wie das vorherige Beispiel:  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Die <xref:System.Linq.Enumerable.Where%2A>-Methode ist eine Erweiterungsmethode. Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md). Da <xref:System.Linq.Enumerable.Where%2A> eine Erweiterungsmethode ist, wird die obige Abfrage kompiliert, als wäre sie wie folgt geschrieben:  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Dieses Beispiel führt zu genau den gleichen Ergebnissen wie die beiden vorherigen Beispiele. Dies veranschaulicht die Tatsache, dass Abfragen tatsächlich zu statisch verknüpften Methodenaufrufen kompiliert werden. Hierdurch wird, gemeinsam mit der verzögerten Ausführungssemantik von Iteratoren, die Leistung verbessert. Weitere Informationen zu der verzögerten Ausführungssemantik von Iteratoren finden Sie unter [Verzögerte Ausführung und Auswertung in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
> [!NOTE]
> Diese Beispiele sind für den Code repräsentativ, der möglicherweise vom Compiler geschrieben wird. Die tatsächliche Implementierung kann in Details von diesen Beispielen abweichen, die Leistung wird jedoch weitgehend mit der dieser Beispiele übereinstimmen.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>Ausführen von XPath-Ausdrücken mit XmlDocument  
 Im folgenden Beispiel erhalten Sie mit <xref:System.Xml.XmlDocument> dieselben Ergebnisse wie in den vorherigen Beispielen:  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 Diese Abfrage gibt dieselbe Ausgabe wie die Beispiele mit LINQ to XML zurück. Der einzige Unterschied ist, dass LINQ to XML das gedruckte XML im Gegensatz zu <xref:System.Xml.XmlDocument> einrückt.  
  
 Der <xref:System.Xml.XmlDocument>-Ansatz bietet in der Regel nicht die Leistung von LINQ to XML, da die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode bei jedem Aufruf intern die folgenden Schritte ausführen muss:  
  
- Analysieren der Zeichenfolge, die den XPath-Ausdruck enthält, und Zerlegen der Zeichenfolge in Token.  
  
- Überprüfen der Token, um sicherzustellen, dass der XPath-Ausdruck gültig ist.  
  
- Übersetzen des Ausdrucks in eine interne Ausdrucksstruktur.  
  
- Durchlaufen der Knoten und entsprechendes Auswählen der Knoten für das Resultset auf Grundlage der Ausdrucksauswertung.  
  
 Dies sind bedeutend mehr Arbeitsschritte als bei einer entsprechenden LINQ to XML-Abfrage. Die genauen Leistungsunterschiede variieren je nach Abfragetyp, in der Regel müssen LINQ to XML-Abfragen jedoch weniger Arbeitsschritte ausführen und bieten daher eine bessere Leistung als das Auswerten von XPath-Ausdrücken mit <xref:System.Xml.XmlDocument>.  
