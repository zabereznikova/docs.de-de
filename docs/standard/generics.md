---
title: Generische Typen (Generics) – Übersicht
description: Erfahren Sie, wie Generics als Codevorlagen fungieren, mit denen Sie typsichere Datenstrukturen definieren können, ohne sich auf einen Datentyp festlegen zu müssen.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 5f6e84e23b5bcdcb3dcd742823d83728fb43d195
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557943"
---
# <a name="generic-types-overview"></a>Generische Typen – Übersicht

Entwickler verwenden Generics sehr häufig in .NET, entweder implizit oder explizit. Wenn Sie LINQ in .NET verwenden: Ist Ihnen schon aufgefallen, dass Sie mit <xref:System.Collections.Generic.IEnumerable%601> arbeiten? Oder haben Sie in einem Onlinebeispiel eines „generischen Repositorys“ zur Kommunikation mit Datenbanken über Entity Framework festgestellt, dass die meisten Methoden `IQueryable<T>` zurückgeben? Möglicherweise haben Sie sich gefragt, wofür das **T** in diesen Beispielen steht und warum es dort ist.

Generics wurden in .NET Framework 2.0 eingeführt und sind im Grunde eine „Codevorlage“, mit der Entwickler [typsichere](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) Datenstrukturen definieren können, ohne sich tatsächlich auf einen Datentyp festlegen zu müssen. <xref:System.Collections.Generic.List%601> ist beispielsweise eine [generische Auflistung](xref:System.Collections.Generic), die deklariert und mit beliebigen Typen wie `List<int>`, `List<string>` oder `List<Person>` verwendet werden kann.

Um zu verstehen, warum Generics nützlich sind, sehen wir uns eine bestimmte Klasse an, und zwar vor und nach dem Hinzufügen von Generics: <xref:System.Collections.ArrayList>. In .NET Framework 1.0 wiesen die -`ArrayList` den Typ <xref:System.Object> auf. Jedes der Sammlung hinzugefügte Element wurde im Hintergrund in ein `Object`-Element konvertiert. Das Gleiche passierte beim Lesen von Elementen aus der Liste. Dieser Vorgang wird als [Boxing und Unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md) bezeichnet und wirkt sich auf die Leistung aus. Abgesehen von der Leistung gibt es jedoch keine Möglichkeit, zur Kompilierzeit den Typ der Daten in der Liste zu bestimmen. Dies beeinträchtigt die Stabilität des Codes. Generics lösen dieses Problem, indem sie den Datentyp definieren, der in jeder Instanz der Liste enthalten sind. Beispielsweise können Sie zu `List<int>` nur Ganzzahlen hinzufügen, zu `List<Person>` nur Personen.

Generics sind auch zur Laufzeit verfügbar. Die Runtime weiß, welche Art Datenstruktur Sie verwenden, und kann die Daten effizienter im Arbeitsspeicher speichern.

Das folgende Beispiel ist ein kleines Programm, das veranschaulicht, wie effizient es ist, wenn die Art der Datenstruktur zur Laufzeit bekannt ist:

```csharp
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

Dieses Programm erzeugt eine Ausgabe ähnlich der folgenden:

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

Als Erstes können Sie feststellen, dass das Sortieren der generischen Liste erheblich schneller erfolgt als bei der nicht generischen Liste. Sie werden vermutlich auch bemerken, dass der Typ für die generische Liste eindeutig ([System.Int32]), der Typ für die nicht generische Liste dagegen generalisiert ist. Da der Runtime bekannt ist, dass die generische `List<int>` den Typ <xref:System.Int32> aufweist, kann sie die Listenelemente in einem zugrunde liegenden Ganzzahlarray im Arbeitsspeicher speichern. Die nicht generische `ArrayList` muss hingegen jedes Listenelement in ein Objekt umwandeln. Wie dieses Beispiel zeigt, beanspruchen die zusätzlichen Umwandlungen Zeit und verlangsamen den Sortiervorgang für die Liste.

Ein weiterer Vorteil: Wenn die Runtime den Typ der Generika kennt, wird das Debuggen vereinfacht. Wenn Sie Generika in C# debuggen, wissen Sie, welchen Typ jedes Element in Ihrer Datenstruktur aufweist. Ohne Generics wüssten Sie dies nicht.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch – Generics](../csharp/programming-guide/generics/index.md)
