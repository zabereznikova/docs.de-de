---
title: Leistung verketteter Abfragen (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: 7deff9205e6535877efabd85257baa5b3906f41a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253124"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a>Leistung verketteter Abfragen (LINQ to XML) (C#)

Einer der wichtigsten Vorteile von LINQ (und LINQ to XML) besteht darin, dass verkettete Abfragen wie eine einzelne große, kompliziertere Abfrage ausgeführt werden können.

Eine verkettete Abfrage ist eine Abfrage, die als Quelle eine andere Abfrage verwendet. Beispielsweise ist im folgenden einfachen Code `query2` die Quelle von `query1`:

```csharp
XElement root = new XElement("Root",
    new XElement("Child", 1),
    new XElement("Child", 2),
    new XElement("Child", 3),
    new XElement("Child", 4)
);

var query1 = from x in root.Elements("Child")
             where (int)x >= 3
             select x;

var query2 = from e in query1
             where (int)e % 2 == 0
             select e;

foreach (var i in query2)
    Console.WriteLine("{0}", (int)i);
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```output
4
```

Diese verkettete Abfrage bietet dasselbe Leistungsprofil wie das Durchlaufen einer verknüpften Liste.

- Die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse bietet im Wesentlichen die gleiche Leistung wie das Durchlaufen einer verknüpften Liste. <xref:System.Xml.Linq.XContainer.Elements%2A> wird als Iterator mit verzögerter Ausführung implementiert. Dies bedeutet, dass neben dem Durchlaufen der verknüpften Liste einige zusätzliche Arbeitsschritte ausgeführt werden, z. B. die Zuweisung des Iteratorobjekts und das Nachverfolgen des Ausführungsstatus. Diese Arbeitsschritte können in zwei Kategorien eingeteilt werden: einerseits die Schritte, die beim Einrichten des Iterators durchgeführt werden, und andererseits die Schritte, die in jeder Iteration durchgeführt werden. Zum Einrichten sind nur wenige, festgelegte Arbeitsschritte erforderlich, und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, sind proportional zur Anzahl der Elemente in der Quellauflistung.

- In `query1` wird von der Abfrage durch die `where`-Klausel die <xref:System.Linq.Enumerable.Where%2A>-Methode aufgerufen. Diese Methode ist auch als Iterator implementiert. Die Einrichtung besteht neben den normalen Einrichtungsschritten für einen Iterator aus dem Instanziieren des Delegaten, der auf den Lambdaausdruck verweist. Der Delegat wird bei jeder Iteration aufgerufen, um das Prädikat auszuführen. Diese Einrichtungsschritte und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, ähneln den Arbeitsschritten, die beim Durchlaufen einer Iteration der Achse durchgeführt werden.

- In `query1` wird von der Abfrage durch die <xref:System.Linq.Enumerable.Select%2A>select{3}-Klausel die {4}-Methode aufgerufen. Diese Methode weist dasselbe Leistungsprofil wie die <xref:System.Linq.Enumerable.Where%2A>-Methode auf.

- In `query2` verfügen sowohl die `where`-Klausel als auch die `select`-Klausel über dasselbe Leistungsprofil wie in `query1`.

Die Iteration durch `query2` ist daher direkt proportional zur Anzahl der Elemente in der Quelle der ersten Abfrage, mit anderen Worten, zeitlich linear. Ein entsprechendes Visual Basic-Beispiel hätte dasselbe Leistungsprofil.

Weitere Informationen zu Iteratoren finden Sie unter [yield](../../../language-reference/keywords/yield.md).

Ein ausführlicheres Tutorial zum Verketten von Abfragen finden Sie unter [Tutorial: Verketten von Abfragen](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).
