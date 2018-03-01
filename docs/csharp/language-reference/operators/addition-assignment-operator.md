---
title: "Operator += (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: de83f48fc644d8b232d9ef9e1698272f20a27d65
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-operator-c-reference"></a>Operator += (C#-Referenz)
Der Additionszuweisungsoperator.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `+=`, z.B.  
  
```  
x += y  
```  
  
 für die folgende Syntax:  
  
```  
x = x + y  
```  
  
 außer dass `x` nur einmal überprüft wird. Die Bedeutung des [+-Operators](../../../csharp/language-reference/operators/addition-operator.md) hängt von den Typen von `x` und `y` ab (Addition für numerische Operanden, Verkettung für Zeichenfolgenoperanden usw.).  
  
 Der Operator `+=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [+-Operator](../../../csharp/language-reference/operators/addition-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 Der `+=`-Operator wird auch verwendet, um eine Methode zu bestimmen, die als Antwort auf ein Ereignis aufgerufen wird. Solche Methoden werden als Ereignishandler bezeichnet. Die Verwendung des `+=`-Operators in diesem Kontext wird als *Abonnieren eines Ereignisses* bezeichnet. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
