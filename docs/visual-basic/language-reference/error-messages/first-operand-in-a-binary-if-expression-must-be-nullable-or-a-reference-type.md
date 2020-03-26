---
title: Der erste Operand in einem binären If-Ausdruck muss ein Typ, der NULL-Werte zulässt, oder ein Referenztyp sein
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249525"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Der erste Operand in einem binären If-Ausdruck muss ein Typ, der NULL-Werte zulässt, oder ein Referenztyp sein
Ein `If` Ausdruck kann entweder zwei oder drei Argumente annehmen. Wenn Sie nur zwei Argumente senden, muss das erste Argument ein Verweistyp oder ein NULL-Werttyp sein. Wenn das erste Argument zu `Nothing`etwas anderem als ausgewertet wird, wird sein Wert zurückgegeben. Wenn das erste Argument `Nothing`zu ausgewertet wird, wird das zweite Argument ausgewertet und zurückgegeben.  
  
 Der folgende Code enthält `If` z. B. zwei Ausdrücke, einen mit drei Argumenten und einen mit zwei Argumenten. Die Ausdrücke berechnen und geben denselben Wert zurück.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Die folgenden Ausdrücke verursachen diesen Fehler:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Fehler-ID:** 33107  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie den Code nicht so ändern können, dass das erste Argument ein NULL-Werttyp oder Verweistyp ist, sollten Sie in einen Ausdruck mit drei Argumenten `If` oder in eine `If...Then...Else` Anweisung konvertieren.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Siehe auch

- [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
