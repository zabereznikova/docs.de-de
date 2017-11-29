---
title: as (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4f2964f32a4139ffeb6d51b761f1176a57c5be6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
