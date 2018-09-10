---
title: 'Operator ?: (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 150149453a67d8e5319461266865cb25be180347
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506431"
---
# <a name="-operator-c-reference"></a>Operator ?: (C#-Referenz)
Der bedingte Operator (`?:`), gemeinhin als ternärer bedingter Operator bekannt, gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück. Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a>Hinweise  
 `condition` muss mit `true` oder `false` ausgewertet werden. Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet. Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet. Nur einer der beiden Ausdrücke wird ausgewertet.  
  
 Entweder muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.  
  
 Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`-Konstruktion benötigen. Im folgenden Code wird z. B. zuerst eine `if`-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 Der bedingte Operator ist rechtsassoziativ. Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.  
  
 Der bedingte Operator kann nicht überladen werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [?.- und ?[]-Operatoren](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [?? Operator](../../../csharp/language-reference/operators/null-coalescing-operator.md)
