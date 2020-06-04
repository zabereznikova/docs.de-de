---
title: Leistung verketteter Abfragen (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
ms.openlocfilehash: 6b87f2744f663ebd45dceb036dcaac71b80765fc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396388"
---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a>Leistung verketteter Abfragen (LINQ to XML) (Visual Basic)

Einer der wichtigsten Vorteile von LINQ (und LINQ to XML) besteht darin, dass verkettete Abfragen wie eine einzelne große, kompliziertere Abfrage ausgeführt werden können.

Eine verkettete Abfrage ist eine Abfrage, die als Quelle eine andere Abfrage verwendet. Beispielsweise ist im folgenden einfachen Code `query2` die Quelle von `query1`:

```vb
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))

Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x

Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e

For Each i As var In query2
    Console.WriteLine("{0}", CInt(i))
Next
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```console
4
```

Diese verkettete Abfrage bietet dasselbe Leistungsprofil wie das Durchlaufen einer verknüpften Liste.

- Die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse bietet im Wesentlichen die gleiche Leistung wie das Durchlaufen einer verknüpften Liste. <xref:System.Xml.Linq.XContainer.Elements%2A> wird als Iterator mit verzögerter Ausführung implementiert. Dies bedeutet, dass neben dem Durchlaufen der verknüpften Liste einige zusätzliche Arbeitsschritte ausgeführt werden, z. B. die Zuweisung des Iteratorobjekts und das Nachverfolgen des Ausführungsstatus. Diese Arbeitsschritte können in zwei Kategorien eingeteilt werden: einerseits die Schritte, die beim Einrichten des Iterators durchgeführt werden, und andererseits die Schritte, die in jeder Iteration durchgeführt werden. Zum Einrichten sind nur wenige, festgelegte Arbeitsschritte erforderlich, und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, sind proportional zur Anzahl der Elemente in der Quellauflistung.

- In `query1` wird von der Abfrage durch die `Where`-Klausel die <xref:System.Linq.Enumerable.Where%2A>-Methode aufgerufen. Diese Methode ist auch als Iterator implementiert. Die Einrichtung besteht neben den normalen Einrichtungsschritten für einen Iterator aus dem Instanziieren des Delegaten, der auf den Lambdaausdruck verweist. Der Delegat wird bei jeder Iteration aufgerufen, um das Prädikat auszuführen. Diese Einrichtungsschritte und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, ähneln den Arbeitsschritten, die beim Durchlaufen einer Iteration der Achse durchgeführt werden.

- In `query1` wird von der Abfrage durch die <xref:System.Linq.Enumerable.Select%2A>select<xref:System.Linq.Enumerable.Select%2A>-Klausel die {3}-Methode aufgerufen. Diese Methode weist dasselbe Leistungsprofil wie die <xref:System.Linq.Enumerable.Where%2A>-Methode auf.

- In `query2` verfügen sowohl die `Where`-Klausel als auch die `Select`-Klausel über dasselbe Leistungsprofil wie in `query1`.

 Die Iteration durch `query2` ist daher direkt proportional zur Anzahl der Elemente in der Quelle der ersten Abfrage, mit anderen Worten, zeitlich linear.

## <a name="see-also"></a>Weitere Informationen

- [Leistung (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
