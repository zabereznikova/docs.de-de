---
title: Operator -= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 443f0d717288a491838d23eaa63218150bd346d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-c-reference"></a>Operator -= (C#-Referenz)
Der Subtraktionszuweisungsoperator.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `-=`, z.B.  
  
```  
x -= y  
```  
  
 für die folgende Syntax:  
  
```  
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
