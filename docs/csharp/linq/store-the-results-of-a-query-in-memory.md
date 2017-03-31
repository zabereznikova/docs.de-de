---
title: Speichern der Ergebnisse einer Abfrage im Speicher
description: So speichern Sie Ergebnisse.
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 644db94bc739d0ae465e28315f0ec43ef6ac241e
ms.lasthandoff: 03/13/2017

---
# <a name="store-the-results-of-a-query-in-memory"></a>Speichern der Ergebnisse einer Abfrage im Speicher

Eine Abfrage besteht im Grunde aus einer Reihe von Anweisungen für das Abrufen und Organisieren von Daten. Abfragen werden verzögert ausgeführt, da jedes nachfolgende Element im Ergebnis angefordert wird. Wenn Sie `foreach` zum Durchlaufen der Ergebnisse verwenden, werden Elemente so zurückgegeben, wie auf sie zugegriffen wurde. Rufen Sie einfach eine der folgenden Methoden für die Abfragevariable auf, um eine Abfrage auszuwerten und ihre Ergebnisse ohne das Ausführen einer `foreach`-Schleife zu speichern:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Es wird empfohlen, dass Sie die zurückgegebenen Auflistungsobjekte beim Speichern der Abfrageergebnisse einer neuen Variable zuweisen, wie im folgenden Beispiel gezeigt wird:  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)
