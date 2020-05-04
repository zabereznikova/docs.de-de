---
title: Ausführen von gruppierten Joins (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie gruppierte Joins mit LINQ in C# ausführen.
ms.date: 04/22/2020
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 740a861da7dfb9653a874d5baf67eeb2030555b4
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135749"
---
# <a name="perform-grouped-joins"></a>Ausführen von Gruppenverknüpfungen

Die Gruppenverknüpfung ist nützlich für das Erstellen hierarchischer Datenstrukturen. Sie verbindet jedes Element aus der ersten Auflistung mit einem Satz von entsprechenden Elementen aus der zweiten Auflistung.

Eine Klasse oder relationale Datenbanktabelle namens `Student` kann z.B. zwei Felder enthalten: `Id` und `Name`. Eine zweite Klasse oder relationale Datenbanktabelle namens `Course` kann zwei Felder enthalten: `StudentId` und `CourseTitle`. Eine Gruppenverknüpfung dieser beiden Datenquellen, die auf der übereinstimmenden `Student.Id` und `Course.StudentId` basiert, würde jeden `Student` mit einer Auflistung von `Course`-Objekten gruppieren (die vielleicht leer sind).

> [!NOTE]
> Jedes Element der ersten Auflistung erscheint im Ergebnissatz einer Gruppenverknüpfung, unabhängig davon, ob entsprechende Elemente in der zweiten Auflistung gefunden werden. Sollten keine entsprechenden Elemente gefunden werden, ist die Sequenz der entsprechenden Elemente für das Element leer. Die Ergebnisauswahl hat daher Zugriff auf jedes Element der ersten Auflistung. Dies unterscheidet sich von der Ergebnisauswahl in einer Verknüpfung, bei der keine Gruppen verknüpft werden. Diese kann nicht auf Elemente aus der ersten Auflistung zugreifen, die keine Übereinstimmung in der zweiten Auflistung haben.

> [!WARNING]
> <xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType> hat keine direkte Entsprechung unter den Begriffen herkömmlicher relationaler Datenbanken. Diese Methode implementiert jedoch eine Obermenge innerer Joins und linker äußerer Joins. Beide dieser Vorgänge können im Hinblick auf einen gruppierten Join geschrieben werden. Weitere Informationen finden Sie unter [Verknüpfungsvorgänge (C#)](../programming-guide/concepts/linq/join-operations.md) und unter [Entity Framework Core > GroupJoin](https://docs.microsoft.com/ef/core/querying/complex-query-operators#groupjoin).

Im ersten Beispiel in diesem Artikel wird das Ausführen eines gruppierten Joins gezeigt. Im zweiten Beispiel wird gezeigt, wie eine Gruppenverknüpfung zum Erstellen von XML-Elementen verwendet wird.

## <a name="example---group-join"></a>Beispiel: Gruppierter Join

Das folgende Beispiel führt eine Gruppenverknüpfung von Objekten des Typs `Person` und `Pet` aus, die auf der `Person` basiert und mit der `Pet.Owner`-Eigenschaft übereinstimmt. Bei einer Verknüpfung, bei der keine Gruppen verknüpft werden, wird für jede Übereinstimmung ein Elementpaar erzeugt. Im Gegensatz dazu erzeugt eine Gruppenverknüpfung nur ein resultierendes Objekt für jedes Element der ersten Auflistung, was in diesem Beispiel ein `Person`-Objekt ist. Die entsprechenden Elemente aus der zweiten Auflistung, die in diesem Beispiel `Pet`-Objekte sind, werden in einer Auflistung gruppiert. Die Ergebnisauswahlfunktion erstellt schließlich einen anonymen Typ für jede Übereinstimmung, die aus `Person.FirstName` und einer Auflistung von `Pet`-Objekten besteht.

[!code-csharp[CsLINQProgJoining#5](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]

## <a name="example---group-join-to-create-xml"></a>Beispiel: Gruppierter Join zum Erstellen einer XML

Gruppenverknüpfungen lassen sich ideal für das Erstellen von XML mithilfe von LINQ to XML nutzen. Das folgende Beispiel ähnelt dem vorherigen, nur dass die Ergebnisauswahlfunktion anstatt eines anonymen Typs XML-Elemente erstellt, die die verknüpften Objekte darstellen.

[!code-csharp[CsLINQProgJoining#6](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [Ausführen innerer Verknüpfungen](perform-inner-joins.md)
- [Ausführen linker äußerer Verknüpfungen](perform-left-outer-joins.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
