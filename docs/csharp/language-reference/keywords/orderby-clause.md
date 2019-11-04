---
title: orderby-Klausel – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 09a745fe3da3a5acb71972b9cf56391774c7016a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422644"
---
# <a name="orderby-clause-c-reference"></a>orderby-Klausel (C#-Referenz)

In einem Abfrageausdruck bewirkt die `orderby`-Klausel, dass die zurückgegebene Sequenz oder Untersequenz (Gruppe) entweder in aufsteigender oder absteigender Reihenfolge sortiert wird. Es können mehrere Schlüssel angegeben werden, um eine oder mehrere sekundäre Sortiervorgänge auszuführen. Die Sortierung erfolgt mit dem Standardvergleich für den Typ des Elements. Standardmäßig wird eine aufsteigende Sortierreihenfolge verwendet. Sie können auch einen benutzerdefinierten Vergleich angeben. Der ist jedoch nur mit der methodenbasierten Syntax verfügbar. Weitere Informationen finden Sie unter [Sortieren von Daten](../../programming-guide/concepts/linq/sorting-data.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel sortiert die erste Abfrage die Wörter in alphabetischer Reihenfolge, beginnend mit A, und die zweite Abfrage die gleichen Wörter in absteigender Reihenfolge. (Das Schlüsselwort `ascending` ist der Standardwert für das Sortieren und kann ausgelassen werden.)

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine primäre Sortierung der Nachnamen von Studenten und dann eine sekundäre Sortierung auf ihre Vornamen ausgeführt.

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a>Anmerkungen

Zur Kompilierzeit wird die `orderby`-Klausel in einen Aufruf der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode übersetzt. Mehrere Schlüssel in der `orderby`-Klausel werden in <xref:System.Linq.Enumerable.ThenBy%2A>-Methodenaufrufe übersetzt.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Abfrageschlüsselwörter (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [group-Klausel](group-clause.md)
- [Erste Schritte mit LINQ in C#](/dotnet/csharp/programming-guide/concepts/linq/)
