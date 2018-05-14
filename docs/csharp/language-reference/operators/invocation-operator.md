---
title: Operator () (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 2ded01ef3192e0f34d586cd63d93b894b5347e7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operator () (C#-Referenz)
Zusätzlich zur Angabe der Reihenfolge von Vorgängen in einem Ausdruck werden Klammern verwendet, um folgende Aufgaben auszuführen:  
  
1.  Das Angeben von Umwandlungen oder Typkonvertierungen.  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Aufrufen von Methoden oder Delegaten.  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Eine Umwandlung ruft implizit den Konvertierungsoperator von einem Typ in einen anderen auf; die Umwandlung schlägt fehl, wenn der Konvertierungsoperator nicht definiert ist. Weitere Informationen zu Konvertierungsoperatoren erhalten Sie unter [explizit](../../../csharp/language-reference/keywords/explicit.md) und [implizit](../../../csharp/language-reference/keywords/implicit.md).  
  
 Operator `()` kann nicht überladen werden.  
  
 Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Ein CAST-Ausdruck kann zu mehrdeutiger Syntax führen. Der Ausdruck `(x)–y` könnte z.B. entweder als CAST-Ausdruck (eine Umwandlung von –y in Typ x) oder als additiver Ausdruck kombiniert mit einem Ausdruck in Klammern interpretiert werden, der den Wert x–y berechnet.  
  
 Weitere Informationen zu Methodenaufrufen finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
