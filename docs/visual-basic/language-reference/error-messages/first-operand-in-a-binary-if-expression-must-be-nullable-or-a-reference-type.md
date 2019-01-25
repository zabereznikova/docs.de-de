---
title: Der erste Operand in eine Binärdatei &#39;Wenn&#39; Ausdruck muss NULL-Werte zulässt, oder geben Sie ein Verweis
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 85094ba6d6a44bf2e6cc4fba7946598c286a08a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668271"
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a>Der erste Operand in eine Binärdatei &#39;Wenn&#39; Ausdruck muss NULL-Werte zulässt, oder geben Sie ein Verweis
Ein `If` Ausdruck kann entweder zwei oder drei Argumente annehmen. Wenn Sie nur zwei Argumente senden, muss das erste Argument ein Verweistyp oder einem nullable-Typ sein. Ergibt das erste Argument auf einen anderen als `Nothing`, dessen Wert zurückgegeben. Wenn das erste Argument ergibt `Nothing`, das zweite Argument wird ausgewertet und zurückgegeben.  
  
 Der folgende Code enthält z. B. zwei `If` Ausdrücke, eine mit drei Argumenten und einen mit zwei Argumenten. Die Ausdrücke berechnen und den gleichen Wert zurück.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Dieser Fehler wird durch die folgenden Ausdrücke verursacht:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Fehler-ID:** BC33107  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie den Code, damit das erste Argument ein nullable-Typ oder ein Typ ist nicht mehr ändern können, sollten Sie die Konvertierung in ein drei-Argument `If` Ausdruck oder eine `If...Then...Else` Anweisung.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Siehe auch
- [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
