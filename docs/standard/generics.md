---
title: "Generische Typen (Generika) – Übersicht"
description: "Generische Typen (Generika) – Übersicht"
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 9827f9f37ce198b23bfd4e5fbca41cd86d5885a4
ms.lasthandoff: 03/02/2017

---

# <a name="generic-types-generics-overview"></a>Generische Typen (Generika) – Übersicht

Generika werden andauernd in C# verwendet, entweder implizit oder explizit. Wenn Sie LINQ in C# verwenden, haben Sie schon einmal bemerkt, dass Sie mit IEnumerable<T> arbeiten? Oder haben Sie in einem Onlinebeispiel eines „generischen Repositorys“ zur Kommunikation mit Datenbanken über Entity Framework festgestellt, dass die meisten Methoden IQueryable<T> zurückgeben? Haben Sie sich gefragt, wofür das **T** in diesen Beispielen steht und warum es dort ist?

Generika wurden zum ersten Mal in .NET Framework 2.0 eingeführt und umfassten Änderungen sowohl an der Sprache C# als auch an der Common Language Runtime (CLR). **Generika** sind im Grunde eine „Codevorlage“, mit der Entwickler [typsichere](https://msdn.microsoft.com/library/hbzz1a9a.aspx) Datenstrukturen definieren können, ohne sich tatsächlich auf einen Datentyp festlegen zu müssen. `List<T>` ist beispielsweise eine [generische Auflistung](https://msdn.microsoft.com/library/System.Collections.Generic.aspx), die deklariert und mit beliebigen Typen verwendet werden kann: `List<int>`, `List<string>`, `List<Person>` usw.

Worum liegt also der Sinn? Warum sind Generika nützlich? Um dies zu verstehen, müssen wir uns eine bestimmte Klasse ansehen, und zwar vor und nach dem Hinzufügen von Generika. Wir sehen uns `ArrayList` an. In C# 1.0 wiesen die `ArrayList`-Elemente den Typ `object` auf. Dies bedeutete, dass jedes hinzugefügte Element im Hintergrund in ein `object` konvertiert wurde. Das Gleiche passierte beim Lesen der Elemente aus der Liste (dieser Prozess wird als [Boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) bzw. Unboxing bezeichnet). Boxing und Unboxing wirken sich auf die Leistung aus. Schlimmer noch: Zum Zeitpunkt der Kompilierung lässt sich nicht mitteilen, welchen Typ die Daten in der Liste tatsächlich aufweisen. Dies beeinträchtigt die Stabilität des Codes. Generika lösen dieses Problem, indem sie zusätzliche Informationen zum Datentyp bereitstellen, die in jeder Instanz der Liste enthalten sind. Einfach gesagt: Zu `List<int>` können Sie nur Ganzzahlen hinzufügen, zu `List<Person>` nur Personen usw.

Generika sind auch zur Laufzeit verfügbar und werden **konkretisiert**. Dies bedeutet, dass die Runtime weiß, welche Art Datenstruktur Sie verwenden, und die Daten effizienter im Arbeitsspeicher speichern kann.

Das folgende Programm zeigt, wie effizient es ist, wenn die Art der Datenstruktur zur Laufzeit bekannt ist:

```cs
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }

```

Das Programm erzeugt die folgende Ausgabe:

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms

```

Als erstes bemerken Sie, dass das Sortieren der generischen Liste erheblich schneller ist als bei der nicht generischen Liste. Sie stellen vermutlich auch fest, dass der Typ für die generische Liste eindeutig ([System.Int32]), der Typ für die nicht generische Liste dagegen generalisiert ist. Da der Runtime bekannt ist, dass die generische `List<int>` den Typ „int“ aufweist, kann sie die Listenelemente in einem zugrunde liegenden ganzzahligen Array im Arbeitsspeicher speichern. Die nicht generische `ArrayList` dagegen muss jedes Listenelement in ein Objekt umwandeln, das in einem Objektarray im Arbeitsspeicher gespeichert wird. Wie in diesem Beispiel gezeigt, beanspruchen die Umwandlungen Zeit und verlangsamen den Sortiervorgang für die Liste.

Ein weiterer nützlicher Vorteil: Wenn die Runtime den Typ der Generika kennt, wird das Debuggen vereinfacht. Wenn Sie Generika in C# debuggen, wissen Sie, welchen Typ jedes Element in Ihrer Datenstruktur aufweist. Ohne Generika wüssten Sie dies nicht.

## <a name="further-reading-and-resources"></a>Weitere Informationen und Ressourcen

*   [Einführung in Generika in C#](https://msdn.microsoft.com/library/ms379564.aspx)
*   [C#-Programmierhandbuch – Generika](https://msdn.microsoft.com/library/512aeb7t.aspx)

