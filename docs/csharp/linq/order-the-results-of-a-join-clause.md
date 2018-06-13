---
title: Sortieren der Ergebnisse einer Join-Klausel
description: So sortieren Sie die Ergebnisse einer Join-Klausel.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f426152e614ed9a9c4aa41d7ba7cb8ddf1cd3063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269699"
---
# <a name="order-the-results-of-a-join-clause"></a>Sortieren der Ergebnisse einer Join-Klausel
Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren. Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird. Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen. Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.  
  
## <a name="example"></a>Beispiel  
 Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet. Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)  
 [orderby-Klausel](../language-reference/keywords/orderby-clause.md)  
 [join-Klausel](../language-reference/keywords/join-clause.md) 
