---
title: "First operand in a binary &#39;If&#39; expression must be nullable or a reference type | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33107"
  - "vbc33107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33107"
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# First operand in a binary &#39;If&#39; expression must be nullable or a reference type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein `If`\-Ausdruck kann entweder zwei oder drei Argumente verarbeiten.  Wenn Sie nur zwei Argumente verwenden, muss das erste Argument ein Referenztyp oder ein Typ sein, der NULL\-Werte zulässt.  Wenn die Auswertung des ersten Arguments etwas anderes als `Nothing` ergibt, wird der Wert zurückgegeben.  Wenn die Auswertung des ersten Arguments `Nothing` ergibt, wird das zweite Argument ausgewertet und zurückgegeben.  
  
 Der folgende Code enthält beispielsweise zwei `If`\-Ausdrücke, einen mit drei und einen mit zwei Argumenten.  Von beiden Ausdrücken wird der gleiche Wert berechnet und zurückgegeben.  
  
```vb#  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Dieser Fehler wird durch die folgenden Ausdrücke verursacht:  
  
```vb#  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Fehler\-ID:** BC33107  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie den Code nicht so ändern können, dass das erste Argument ein Referenztyp oder ein Typ ist, der NULL\-Werte zulässt, ziehen Sie die Umwandlung in einen `If`\-Ausdruck mit drei Argumenten oder in eine `If...Then...Else`\-Anweisung in Betracht.  
  
    ```vb#  
    Console.WriteLine(If(choice1 < choice2, 1, 2))  
    Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
    ```  
  
## Siehe auch  
 [If Operator](../../../visual-basic/language-reference/operators/if-operator.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)