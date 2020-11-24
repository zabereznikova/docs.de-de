---
title: Verwenden von foreach zum Entfernen von Elementen aus einer BlockingCollection-Klasse
ms.date: 05/04/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: 9346ead4bf0aef91a224e0ab11ffd30a7c205294
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830999"
---
# <a name="use-foreach-to-remove-items-in-a-blockingcollection"></a>Verwenden von foreach zum Entfernen von Elementen aus einer BlockingCollection-Klasse

Zusätzlich zum Entnehmen von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601>-Klasse mithilfe der Methoden <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> können Sie auch einen [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Verweis ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) mit der <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType>-Methode verwenden, um Elemente zu entfernen, bis der Hinzufügevorgang abgeschlossen und die Auflistung leer ist. Dies wird als *mutierende Enumeration* oder *verbrauchende Enumeration* bezeichnet, da dieser Enumerator, im Gegensatz zu einer typischen `foreach`- (`For Each`-)Schleife, die Quellsammlung durch Entfernen von Elementen verändert.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Entfernen aller Elemente in einer <xref:System.Collections.Concurrent.BlockingCollection%601> mithilfe einer `foreach`-Schleife (`For Each`).

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

Dieses Beispiel verwendet eine `foreach`-Schleife mit der <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType>-Methode im verbrauchenden Thread, wodurch jedes Element beim Aufzählen aus der Auflistung entfernt wird. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> begrenzt die maximale Anzahl von Elementen, die sich zu einem bestimmten Zeitpunkt in der Sammlung befinden können. Durch Aufzählen der Auflistung auf diese Weise wird der Consumerthread blockiert, wenn keine Elemente verfügbar sind oder die Auflistung leer ist. In diesem Beispiel ist eine Blockierung kein Problem, da der Producerthread Elemente schneller hinzufügt als sie verbraucht werden können.

Die <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType>-Methode gibt `IEnumerable<T>` zurück, weshalb die Reihenfolge nicht garantiert werden kann. Intern wird jedoch eine <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>-Klasse als zugrunde liegender Sammlungstyp verwendet, die Objekte nach der FIFO-Reihenfolge (First-in-First-Out) aus der Warteschlange entfernt. Wenn gleichzeitige Aufrufe der <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType>-Methode durchgeführt werden, konkurrieren diese. Ein Element, das in einer Enumeration aus der Warteschlange entfernt wurde, kann nicht in der anderen Enumeration beobachtet werden.

Um die Auflistung aufzuzählen, ohne sie zu verändern, verwenden Sie einfach `foreach` (`For Each`) ohne die <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>-Methode. Es ist jedoch wichtig zu wissen, dass diese Art der Enumeration eine Momentaufnahme der Auflistung zu einem genauen Zeitpunkt darstellt. Wenn weitere Threads gleichzeitig Elemente hinzufügen oder entfernen, während die Schleife ausgeführt wird, stellt die Schleife möglicherweise nicht den tatsächlichen Zustand der Auflistung dar.

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Parallele Programmierung](../../parallel-programming/index.md)
