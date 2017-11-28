---
title: 'Gewusst wie: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ddb4ecbbf456179e91aa0003c2dc5653f153411f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Gewusst wie: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)
Das folgende Beispiel veranschaulicht das Erstellen von Multicastdelegaten. Eine nützliche Eigenschaft von [delegate](../../../csharp/language-reference/keywords/delegate.md)-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können. Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten. Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf. Es können nur Delegaten desselben Typs kombiniert werden.  
  
 Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.MulticastDelegate>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)
