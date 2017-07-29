---
title: Operator / (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operator / (C#-Referenz)
Der Divisionsoperator (`/`) dividiert seinen ersten Operanden durch den zweiten Operanden. Alle numerischen Typen besitzen vordefinierte Divisionsoperatoren.  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `/` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Eine Überladung des `/`-Operator überlädt implizit den [/= Operator](division-assignment-operator.md).  
  
 Wenn Sie zwei ganze Zahlen teilen, ist das Ergebnis immer eine ganze Zahl. Z.B. das Ergebnis von 7 / 3 ist 2. Bestimmen Sie den Rest von 7 / 3, mithilfe des Restoperator ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Um einen Quotienten als rationale Zahl oder Bruch zu erhalten, geben Sie dem Dividend oder Divisor Typ `float` oder `double`. Sie können den Typ implizit zuweisen, wenn Sie den Dividenden oder Divisor als Dezimalzahl ausdrücken, indem Sie eine Ziffer rechts neben dem Dezimaltrennzeichen einfügen, wie im folgenden Beispiel gezeigt.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)

