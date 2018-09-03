---
title: Operator / (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: bddf6d234f3536ad64f0cd876cc7ade4494916d9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43394852"
---
# <a name="-operator-c-reference"></a>Operator / (C#-Referenz)
Der Divisionsoperator (`/`) dividiert seinen ersten Operanden durch den zweiten Operanden. Alle numerischen Typen besitzen vordefinierte Divisionsoperatoren.
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `/` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Eine Überladung des `/`-Operator überlädt implizit den [/= Operator](division-assignment-operator.md).  
  
 Wenn Sie zwei ganze Zahlen teilen, ist das Ergebnis immer eine ganze Zahl. Z.B. das Ergebnis von 7 / 3 ist 2. Dies ist nicht zu verwechseln mit der ganzzahligen Division, weil der Operator `/` nach 0 rundet: Das Ergebnis von -7 / 3 ist -2.  
  
 Verwenden Sie die Typen `float`, `double` oder `decimal`, um als Quotienten eine rationale Zahl zu erhalten. Es gibt viele Möglichkeiten für die Konvertierung zwischen [integrierten numerischen Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md).  
  
 Bestimmen Sie den Rest mithilfe des [Restoperators](../../../csharp/language-reference/operators/remainder-operator.md) `%`.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
