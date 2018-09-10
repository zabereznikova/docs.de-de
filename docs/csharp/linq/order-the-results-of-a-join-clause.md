---
title: Sortieren der Ergebnisse einer Join-Klausel (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie die Ergebnisse einer Join-Klausel in C# sortieren.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: 13cd6cb202cf67def17310db6d98e368ce837646
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516985"
---
# <a name="order-the-results-of-a-join-clause"></a>Sortieren der Ergebnisse einer Join-Klausel

Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren. Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird. Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen. Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.

## <a name="example"></a>Beispiel

Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet. Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ)](index.md)  
- [orderby-Klausel](../language-reference/keywords/orderby-clause.md)  
- [join-Klausel](../language-reference/keywords/join-clause.md)  