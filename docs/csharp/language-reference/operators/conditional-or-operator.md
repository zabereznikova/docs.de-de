---
title: Operator || (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 58e5fd72a3748e7af0894093fc461c4efb543608
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925539"
---
# <a name="-operator-c-reference"></a>Operator || (C#-Referenz)
Der bedingte Operator OR (`||`) führt ein logisches „Oder“ seiner `bool`-Operanden aus. Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet. Wenn der erste Operand als `false` ausgewertet wird, wird durch den zweiten Operanden bestimmt, ob der ODER-Ausdruck als Ganzes als `true` oder `false` ausgewertet wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Vorgang  
  
```csharp  
x || y  
```  
  
 entspricht dem Vorgang  
  
```csharp  
x | y  
```  
  
 mit folgender Ausnahme: Wenn `x` `true` ist, wird `y` nicht ausgewertet, da der ODER-Vorgang unabhängig des Werts von `y` `true` ist. Dieses Konzept wird als „Kurzschlussauswertung“ bezeichnet.  
  
 Der bedingte ODER-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [TRUE](../../../csharp/language-reference/keywords/true.md) und [FALSE](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen wertet der Ausdruck, der `||` verwendet, nur den ersten Operanden aus. Der Ausdruck, der `|` verwendet, wertet beide Operanden aus. Im zweiten Beispiel tritt eine Laufzeitausnahme auf, wenn beide Operanden ausgewertet werden.  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
