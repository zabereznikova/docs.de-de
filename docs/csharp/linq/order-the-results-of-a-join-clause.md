---
title: Sortieren der Ergebnisse einer Join-Klausel
description: So sortieren Sie die Ergebnisse einer Join-Klausel.
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0252dd62e5638ffd1ab4eeebcfc2382a65997e30
ms.lasthandoff: 03/13/2017

---
# <a name="order-the-results-of-a-join-clause"></a>Sortieren der Ergebnisse einer Join-Klausel
Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren. Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird. Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen. Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.  
  
## <a name="example"></a>Beispiel  
 Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet. Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.  
  
 [!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)   
 [orderby-Klausel](../language-reference/keywords/orderby-clause.md)   
 [join-Klausel](../language-reference/keywords/join-clause.md) 
