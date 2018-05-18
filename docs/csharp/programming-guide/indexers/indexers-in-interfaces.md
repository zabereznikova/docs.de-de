---
title: Indexer in Schnittstellen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: cb039755b7440cbfd1f782cc118d11a03b47da04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="indexers-in-interfaces-c-programming-guide"></a>Indexer in Schnittstellen (C#-Programmierhandbuch)
Indexer können für eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden. Accessoren für Schnittstellenindexer unterscheiden sich von den Accessoren für [Klassen](../../../csharp/language-reference/keywords/class.md)-Indexer in den folgenden Punkten:  
  
-   Schnittstellenaccessoren verwenden keine Modifizierer.  
  
-   Ein Schnittstellenaccessor enthält keinen Text.  
  
 Der Zweck eines Accessors besteht darin anzugeben, ob der Indexer gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.  
  
 Das folgende Beispiel zeigt den Accessor für einen Schnittstellenindexer:  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 Die Signatur eines Indexers muss sich von den Signaturen aller anderen in derselben Schnittstelle deklarierten Indexer unterscheiden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Schnittstellenindexer implementiert werden.  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 Im vorherigen Beispiel könnte der Schnittstellenmember durch Verwendung des vollqualifizierten Namens des Schnittstellenmembers explizit implementiert werden. Zum Beispiel:  
  
```  
public string ISomeInterface.this[int index]   
{   
}   
```  
  
 Der vollqualifizierte Name ist jedoch nur erforderlich, um Mehrdeutigkeiten zu vermeiden, wenn mehr als eine Schnittstelle mit derselben Indexersignatur von der Klasse implementiert wird. Wenn z.B. eine `Employee`-Klasse die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen dieselbe Indexersignatur besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich. Das bedeutet, dass die folgende Indexerdeklaration:  
  
```  
public string IEmployee.this[int index]   
{   
}   
```  
  
 den Indexer für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:  
  
```  
public string ICitizen.this[int index]
{   
}   
```  
  
 den Indexer für die Schnittstelle `ICitizen`.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Indexer](../../../csharp/programming-guide/indexers/index.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)
