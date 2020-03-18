---
title: Sortieren der Ergebnisse einer Join-Klausel (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie die Ergebnisse einer Join-Klausel in C# sortieren.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659864"
---
# <a name="order-the-results-of-a-join-clause"></a>Sortieren der Ergebnisse einer Join-Klausel

Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren. Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird. Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen. Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.

## <a name="example"></a>Beispiel

Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet. Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>Weitere Informationen

- [Language-Integrated Query (LINQ)](index.md)
- [orderby-Klausel](../language-reference/keywords/orderby-clause.md)
- [join-Klausel](../language-reference/keywords/join-clause.md)
