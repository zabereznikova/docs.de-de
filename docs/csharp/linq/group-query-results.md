---
title: Gruppieren von Abfrageergebnissen (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Ergebnisse mit LINQ in C# gruppieren.
ms.date: 12/01/2016
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: 577a358c31fcf5346e7aab7a2e2b6be10fd1beff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688461"
---
# <a name="group-query-results"></a>Gruppieren von Abfrageergebnissen

Das Gruppieren ist eine der leistungsstärksten Funktionen von LINQ. Die folgenden Beispiele zeigen Ihnen, wie Sie Daten auf verschiedene Arten und Weisen gruppieren:

- Nach einer einzelnen Eigenschaft

- Nach dem ersten Buchstaben einer Zeichenfolgeneigenschaft

- Nach einem berechneten numerischen Bereich

- Nach einem booleschen Prädikat oder einem anderer Ausdruck

- Nach einem Verbundschlüssel

Darüber hinaus projizieren die letzten beiden Abfragen die Ergebnisse in einen neuen anonymen Typ, der nur die Vor- und Nachnamen der Studenten enthält. Weitere Informationen finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).

## <a name="example"></a>Beispiel

Alle Beispiele in diesem Thema verwenden die folgenden Hilfsklassen und Datenquellen.

[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Gruppierung von Quellelementen mithilfe einer einzelnen Eigenschaft des Elements als Gruppenschlüssel. In diesem Fall ist der Schlüssel ein `string`, der Nachname des Studenten. Es ist auch möglich, eine Teilzeichenfolge als Schlüssel zu verwenden. Bei der Gruppierungsoperation wird der als Standard für diesen Typ festgelegte Gleichheitsvergleich verwendet.

Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein. Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupBySingleProperty()`.

[!code-csharp[csProgGuideLINQ#17](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Gruppierung von Quellelemente ohne eine Objekteigenschaft als Gruppenschlüssel zu verwenden. In diesem Beispiel ist der Schlüssel der erste Buchstabe des Nachnamens des Studenten.

Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein. Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupBySubstring()`.

[!code-csharp[csProgGuideLINQ#18](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Gruppierung von Quellelementen mithilfe eines numerischen Bereichs als Gruppenschlüssel. Die Abfrage projiziert dann die Ergebnisse in einen anonymen Typ, der nur den Vor- und Nachnamen und den Prozentbereich enthält, dem der Student angehört. Ein anonymer Typ wird verwendet, da es nicht notwendig ist, das gesamte `Student`-Objekt zu nutzen, um die Ergebnisse anzuzeigen. `GetPercentile` ist eine Hilfsfunktion, die einen Prozentwert berechnet, der auf dem Durchschnittsergebnis des Studenten basiert. Die Methode gibt eine ganze Zahl zwischen 0 und 10 zurück.

[!code-csharp[csProgGuideLINQ#50](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]

Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein. Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByRange()`.

[!code-csharp[csProgGuideLINQ#19](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Gruppierung von Vergleichselementen mithilfe eines booleschen Vergleichsausdrucks. In diesem Beispiel testet der boolesche Ausdruck, ob die durchschnittliche Bewertung der Tests eines Studenten größer als 75 ist. Wie in den vorherigen Beispielen werden die Ergebnisse in einen anonymen Typ projiziert, da nicht das gesamte Quellelement benötigt wird. Beachten Sie, dass die Eigenschaften im anonymen Typ Eigenschaften des `Key`-Members werden und dass über den Namen auf sie zugegriffen werden kann, wenn die Abfrage ausgeführt wird.

Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein. Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByBoolean()`.

[!code-csharp[csProgGuideLINQ#20](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung eines anonymen Typs für die Kapselung eines Schlüssels mit mehreren Werten. In diesem Beispiel ist der erste Schlüsselwert der erste Buchstabe des Nachnamens des Studenten. Der zweite Schlüsselwert ist ein boolescher Wert, der angibt, ob der Student in der ersten Prüfung ein Ergebnis über 85 erzielt hat. Sie können die Gruppen anhand jeder Eigenschaft im Schlüssel sortieren.

Fügen Sie die folgende Methode in die `StudentClass`-Klasse ein. Ändern Sie die aufrufende Anweisung in der Methode `Main` in `sc.GroupByCompositeKey()`.

[!code-csharp[csProgGuideLINQ#21](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.IGrouping%602>
- [Language-Integrated Query (LINQ)](index.md)
- [group-Klausel](../language-reference/keywords/group-clause.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
- [Ausführen einer Unterabfrage für eine Gruppierungsoperation](perform-a-subquery-on-a-grouping-operation.md)
- [Erstellen einer geschachtelten Gruppe](create-a-nested-group.md)
- [Gruppieren von Daten](../programming-guide/concepts/linq/grouping-data.md)
