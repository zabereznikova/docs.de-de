---
title: Erstellen innerer Joins (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie innere Joins mit LINQ in C# ausführen.
ms.date: 12/01/2016
ms.assetid: 45bceed6-f549-4114-a9b1-b44feb497742
ms.openlocfilehash: a3e8e9bd97ec630797bc48a3302b27ed45d9103e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659838"
---
# <a name="perform-inner-joins"></a>Ausführen von inneren Verknüpfungen

Bei relationalen Datenbanken erzeugt eine *innere Verknüpfung* einen Ergebnissatz, in dem jedes Element der ersten Aufzählung einmal für jedes übereinstimmende Element in der zweiten Auflistung erscheint. Wenn ein Element in der ersten Auflistung keine übereinstimmenden Elemente besitzt, erscheint es nicht im Ergebnissatz. Die Methode <xref:System.Linq.Enumerable.Join%2A>, die durch die `join`-Klausel in C# aufgerufen wird, implementiert eine innere Verknüpfung.

In diesem Artikel erfahren Sie, wie Sie vier Varianten eines inneren Joins ausführen:

- Eine einfache innere Verknüpfung, die Elemente aus zwei Datenquellen anhand eines einfachen Schlüssels verknüpft.

- Eine innere Verknüpfung, die Elemente aus zwei Datenquellen anhand eines *zusammengesetzten* Schlüssels verknüpft. Mit einem zusammengesetzten Schlüssel, der aus mehr als einem Wert besteht, können Sie Elemente anhand mehr als einer Eigenschaft verknüpfen.

- Eine *Mehrfachverknüpfung*, in der aufeinanderfolgende Verknüpfungsvorgänge aneinander gehängt werden.

- Eine innere Verknüpfung, die mithilfe einer Gruppenverknüpfung implementiert wird.

## <a name="example---simple-key-join"></a>Beispiel: einfacher Schlüsseljoin

Im folgenden Beispiel werden zwei Auflistungen erstellt, die Objekte von zwei benutzerdefinierten Typen (`Person` und `Pet`) enthalten. Die Abfrage verwendet die `join`-Klausel in C#, um `Person`-Objekte mit `Pet`-Objekten übereinzustimmen, dessen `Owner` diese `Person` ist. Die `select`-Klausel in C# definiert, wie die resultierenden Objekte aussehen werden. In diesem Beispiel sind die resultierenden Objekte anonyme Typen, die aus dem Vornamen des Besitzers und dem Haustiernamen bestehen.

[!code-csharp[CsLINQProgJoining#1](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_1.cs)]

Beachten Sie, dass das `Person`-Objekt, dessen `LastName` „Huff“ ist, nicht im Ergebnissatz erscheint, weil es kein `Pet`-Objekt gibt, bei dem `Pet.Owner` gleich `Person` ist.

## <a name="example---composite-key-join"></a>Beispiel: Join mit zusammengesetztem Schlüssel

Anstatt Elemente anhand nur einer Eigenschaft zu verknüpfen, können Sie einen zusammengesetzten Schlüssel verwenden, um Elemente anhand mehreren Eigenschaften zu vergleichen. Geben Sie dazu die Schlüsselauswahlfunktion für jede Auflistung an, um einen anonymen Typ zurückgegeben, der aus den zu vergleichenden Eigenschaften besteht. Wenn Sie die Eigenschaften beschriften, müssen sie über die gleiche Bezeichnung in jedem anonymen Typ des Schlüssels verfügen. Die Eigenschaften müssen auch in der gleichen Reihenfolge angezeigt werden.

Im folgenden Beispiel wird eine Liste von `Employee`-Objekten und eine Liste von `Student`-Objekten verwendet, um zu bestimmen, welche Angestellten auch Studenten sind. Diese beiden Typen haben eine `FirstName`- und `LastName`-Eigenschaft vom Typ <xref:System.String>. Die Funktion, die die Verknüpfungsschlüssel aus jedem Element der Liste erstellt, gibt einen anonymen Typ zurück, der aus den Eigenschaften `FirstName` und `LastName` von jedem Element besteht. Der Verknüpfungsvorgang vergleicht diese zusammengesetzten Schlüssel auf Gleichheit und gibt Objektpaare aus jeder Liste zurück, in der der Vor- und Nachname übereinstimmen.

[!code-csharp[CsLINQProgJoining#2](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_2.cs)]

## <a name="example---multiple-join"></a>Beispiel: Mehrfachjoin

Eine beliebige Anzahl von Verknüpfungsvorgängen kann aneinander gehängt werden, um eine Mehrfachverknüpfung auszuführen. Jede `join`-Klausel in C# verknüpft eine angegebene Datenquelle mit den Ergebnissen der vorherigen Verknüpfung.

Im folgenden Beispiel werden drei Auflistungen erstellt: eine Liste von `Person`-Objekten, eine Liste von `Cat`-Objekten und eine Liste von `Dog`-Objekten.

Die erste `join`-Klausel in C# stimmt Personen und Katzen überein, anhand eines `Person`-Objekts, das mit `Cat.Owner` übereinstimmt. Es gibt eine Sequenz von anonymen Typen zurück, die das `Person`-Objekt und `Cat.Name` enthält.

Die zweite `join`-Klausel in C# verknüpft die von der ersten Verknüpfung zurückgegebenen anonymen Typen mit `Dog`-Objekten in der bereitgestellten Liste von Hunden anhand eines zusammengesetzten Schlüssels, der aus der `Owner`-Eigenschaft des `Person`-Typs und dem ersten Buchstaben des Tiernamens besteht. Sie gibt eine Sequenz von anonymen Typen zurück, die die Eigenschaft `Cat.Name` und `Dog.Name` von jedem übereinstimmen Paar enthält. Da es sich um eine innere Verknüpfung handelt, werden nur die Elemente aus der ersten Datenquelle zurückgegeben, die eine Übereinstimmung in der zweiten Datenquelle haben.

[!code-csharp[CsLINQProgJoining#3](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_3.cs)]

## <a name="example---inner-join-by-using-grouped-join"></a>Beispiel: innerer Join mithilfe eines gruppierten Joins

In den folgenden Beispielen wird Ihnen gezeigt, wie eine innere Verknüpfung mithilfe einer Gruppenverknüpfung implementiert wird.

Die Liste von `Person`-Objekten in `query1` ist über eine Gruppenverknüpfung mit der Liste von `Pet`-Objekten verknüpft, basierend auf der `Person`, die mit der Eigenschaft `Pet.Owner` übereinstimmt. Die Gruppeverknüpfung erstellt eine Auflistung von Zwischengruppen, bei der jede Gruppe aus einem `Person`-Objekt und einer Sequenz von übereinstimmenden `Pet`-Objekten besteht.

Durch das Hinzufügen einer zweiten `from`-Klausel zur Abfrage, wird diese Sequenz von Sequenzen in eine längere Sequenz vereint (oder vereinfacht). Der Typ der Elemente der endgültigen Sequenz wird von der `select`-Klausel festgelegt. In diesem Beispiel ist dieser Typ ein anonymer Typ, der aus der Eigenschaft `Person.FirstName` und `Pet.Name` für jedes übereinstimmende Paar besteht.

Das Ergebnis von `query1` entspricht dem Ergebnissatz, der mithilfe der `join`-Klausel abgerufen werden würde, ohne dass die `into`-Klausel eine innere Verknüpfung ausführt. Die `query2`-Variable veranschaulicht diese entsprechende Abfrage.

[!code-csharp[CsLINQProgJoining#4](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_4.cs)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [Ausführen von Gruppenverknüpfungen](perform-grouped-joins.md)
- [Ausführen linker äußerer Verknüpfungen](perform-left-outer-joins.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
