---
title: '&amp;-Operator (C#-Referenz)'
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 59813b4bc5781776c9f9741c3e49e660c684bff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267879"
---
# <a name="amp-operator-c-reference"></a>&amp;-Operator (C#-Referenz)
Der `&`-Operator kann entweder als unärer oder als binärer Operator funktionieren.  
  
## <a name="remarks"></a>Hinweise  
 Der unäre `&`-Operator gibt die Adresse des Operanden zurück (erfordert [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext).  
  
 Binäre `&`-Operatoren sind für integrale Typen und `bool` vordefiniert. Für integrale Typen berechnet & die bitweise logische AND-Operation der Operanden. Für `bool`-Operanden berechnet & die logische AND-Operation seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn beide Operanden `true` sind.  
  
 Im Gegensatz zum [bedingten AND-Operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&` wertet der binäre `&`-Operator beide Operatoren unabhängig vom Wert des ersten Operators aus. Zum Beispiel:  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 Benutzerdefinierte Typen können den binären `&`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)). Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig. Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
