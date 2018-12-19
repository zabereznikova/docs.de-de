---
title: 'Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d835f9b22fef550d6e73cbd620a283bd71e393ec
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237791"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)
Das folgende Beispiel veranschaulicht das Erstellen von Multicastdelegaten. Eine nützliche Eigenschaft von [delegate](../../../csharp/language-reference/keywords/delegate.md)-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können. Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten. Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf. Es können nur Delegaten desselben Typs kombiniert werden.  
  
 Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.MulticastDelegate>  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Ereignisse](../../../csharp/programming-guide/events/index.md)
