---
title: as (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 6ea5346119259d70ac1a42f3f72a8b2746b8f536
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="as-c-reference"></a>as (C#-Referenz)
Sie können den `as`-Operator verwenden, um bestimmte Arten von Konvertierungen zwischen kompatiblen Verweistypen oder [auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/index.md) durchzuführen. Der folgende Code zeigt ein Beispiel.  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Der `as`-Operator kann mit einem Umwandlungsvorgang verglichen werden. Wenn die Konvertierung jedoch nicht möglich ist, gibt `as` `null` zurück, statt eine Ausnahme auszulösen. Betrachten Sie das folgende Beispiel:  
  
```  
expression as type  
```  
  
 Der Code ist äquivalent zu folgendem Ausdruck, jedoch wird die `expression`-Variable nur einmal ausgewertet.  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 Beachten Sie, dass der `as`-Operator nur Verweis- und Boxingkonvertierungen sowie Konvertierungen mit Nullwert durchführt. Der `as`-Operator kann keine anderen Konvertierungen wie z.B. benutzerdefinierte Konvertierungen durchführen, die stattdessen mithilfe der Cast-Ausdrücke ausgeführt werden sollten.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [?:-Operator](../../../csharp/language-reference/operators/conditional-operator.md)  
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)
