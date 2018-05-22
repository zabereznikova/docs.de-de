---
title: Operator -= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 2f37bfa303fb523840b15e896ee3b4a967eb5b2b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="--operator-c-reference"></a>Operator -= (C#-Referenz)
Der Subtraktionszuweisungsoperator.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `-=`, z.B.  
  
```csharp  
x -= y  
```  
  
 für die folgende Syntax:  
  
```csharp  
x = x - y  
```  
  
 außer dass `x` nur einmal überprüft wird. Die Bedeutung des [Operators -](../../../csharp/language-reference/operators/subtraction-operator.md) hängt von den Typen `x` und `y` (Subtraktion für nummerische Operanden, Delegatentfernung für Delegatoperatoren usw.) ab.  
  
 Der Operator `-=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[- Operator](../../../csharp/language-reference/operators/subtraction-operator.md) überladen (siehe [Operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 Der Operator -= wird auch in C# verwendet, um ein Ereignisabonnement zu kündigen. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
