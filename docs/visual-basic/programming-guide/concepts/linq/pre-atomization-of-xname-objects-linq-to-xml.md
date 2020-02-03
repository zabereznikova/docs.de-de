---
title: Voratomisierung von XName-Objekten (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740790"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Voratomisierung von XName-Objekten (LINQ to XML) (Visual Basic)

Eine Möglichkeit zum Verbessern der Leistung in LINQ to XML ist, <xref:System.Xml.Linq.XName>-Objekte vorab zu atomisieren. Voratomisierung bedeutet, dass Sie einer <xref:System.Xml.Linq.XName>-Objekt eine Zeichenfolge zuweisen, bevor Sie die XML-Struktur mit den Konstruktoren der Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XAttribute> erstellen. Anschließend wird anstelle der Übergabe einer Zeichenfolge an den Konstruktor, der die implizite Konvertierung von Zeichenfolge in <xref:System.Xml.Linq.XName> verwenden würde, das initialisierte <xref:System.Xml.Linq.XName>-Objekt übergeben.

Dies verbessert die Leistung beim Erstellen von großen XML-Strukturen, in denen bestimmte Namen wiederholt werden. Deklarieren und initialisieren Sie hierzu <xref:System.Xml.Linq.XName>-Objekte, bevor Sie die XML-Struktur erstellen, und verwenden Sie dann die <xref:System.Xml.Linq.XName>-Objekte, anstatt für die Element- und Attributnamen Zeichenfolgen anzugeben. Mit dieser Vorgehensweise können beim Erstellen einer großen Anzahl von Elementen (oder Attributen) wesentliche Leistungsverbesserungen erzielt werden.

Sie sollten Voratomisierung innerhalb Ihres Szenarios testen, um eine Entscheidung über die Anwendbarkeit dieses Verfahrens zu treffen.

## <a name="example"></a>Beispiel

Dies wird im folgenden Beispiel veranschaulicht:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

Hierdurch wird folgende Ausgabe generiert:

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

Im folgenden Beispiel wird dieselbe Vorgehensweise für ein XML-Dokument in einem Namespace erläutert.

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

Hierdurch wird folgende Ausgabe generiert:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

Das folgende Beispiel entspricht eher realen Bedingungen. In diesem Beispiel wird der Inhalt des Elements durch eine Abfrage bereitgestellt:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

Im vorherigen Beispiel wird eine bessere Leistung als im folgenden Beispiel erzielt, in dem Namen nicht voratomisiert werden:

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a>Weitere Informationen

- [Leistung (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
- [Atomisierte XName-und XNamespace-Objekte (LINQ to XML) (Visual Basic)](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
