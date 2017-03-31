---
title: Operator () (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 159a663ca151a276b3b56f13cf8e997069210d67
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>Operator () (C#-Referenz)
Zusätzlich zur Angabe der Reihenfolge von Vorgängen in einem Ausdruck werden Klammern verwendet, um folgende Aufgaben auszuführen:  
  
1.  Das Angeben von Umwandlungen oder Typkonvertierungen.  
  
     [!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Aufrufen von Methoden oder Delegaten.  
  
     [!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Eine Umwandlung ruft implizit den Konvertierungsoperator von einem Typ in einen anderen auf; die Umwandlung schlägt fehl, wenn der Konvertierungsoperator nicht definiert ist. Weitere Informationen zu Konvertierungsoperatoren erhalten Sie unter [explizit](../../../csharp/language-reference/keywords/explicit.md) und [implizit](../../../csharp/language-reference/keywords/implicit.md).  
  
 Operator `()` kann nicht überladen werden.  
  
 Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Ein CAST-Ausdruck kann zu mehrdeutiger Syntax führen. Der Ausdruck `(x)–y` könnte z.B. entweder als CAST-Ausdruck (eine Umwandlung von –y in Typ x) oder als additiver Ausdruck kombiniert mit einem Ausdruck in Klammern interpretiert werden, der den Wert x–y berechnet.  
  
 Weitere Informationen zu Methodenaufrufen finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
