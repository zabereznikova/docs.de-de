---
title: "How to: Create a Lambda Expression (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "lambda expressions [Visual Basic]"
  - "expressions [Visual Basic], lambda"
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# How to: Create a Lambda Expression (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Ein *Lambda\-Ausdruck* ist eine Funktion oder Unterroutine, die keinen Namen aufweist.  Lambda\-Ausdrücke können an allen Stellen verwendet werden, an denen ein Delegattyp gültig ist.  
  
### So erstellen Sie eine einzeilige Funktion mit einem Lambda\-Ausdruck  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, wie im folgenden Beispiel veranschaulicht, das Schlüsselwort `Function` ein:  
  
     `Dim add1 =`   `Function`  
  
2.  Geben Sie direkt nach `Function` in Klammern die Parameter der Funktion ein.  Beachten Sie, dass nach `Function` kein Name festgelegt wird.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Text der Funktion ein.  Der Wert, den der Ausdruck ergibt, wird von der Funktion zurückgegeben.  Sie verwenden keine `As`\-Klausel, um den Rückgabetyp festzulegen.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#1)]  
  
     Sie rufen den Lambda\-Ausdruck auf, indem Sie ein Ganzzahlargument übergeben.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#2)]  
  
4.  Das gleiche Ergebnis wird auch in folgendem Beispiel erreicht:  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#3)]  
  
### So erstellen Sie eine einzeilige Unterroutine mit einem Lambda\-Ausdruck  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, wie im folgenden Beispiel veranschaulicht, das Schlüsselwort `Sub` ein:  
  
     `Dim add1 =`   `Sub`  
  
2.  Geben Sie direkt nach `Sub` in Klammern die Parameter der Unterroutine ein.  Beachten Sie, dass nach `Sub` kein Name festgelegt wird.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Geben Sie nach der Parameterliste eine einzelne Anweisung als Text der Unterroutine ein.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#17)]  
  
     Sie rufen den Lambda\-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#18)]  
  
### So erstellen Sie eine mehrzeilige Funktion mit einem Lambda\-Ausdruck  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, wie im folgenden Beispiel veranschaulicht, das Schlüsselwort `Function` ein:  
  
     `Dim add1 =`   `Function`  
  
2.  Geben Sie direkt nach `Function` in Klammern die Parameter der Funktion ein.  Beachten Sie, dass nach `Function` kein Name festgelegt wird.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Drücken Sie die EINGABETASTE.  Die `End Function`\-Anweisung wird automatisch hinzugefügt.  
  
4.  Fügen Sie im Text der Funktion den folgenden Code hinzu, um einen Ausdruck zu erstellen und den Wert zurückzugeben.  Sie verwenden keine `As`\-Klausel, um den Rückgabetyp festzulegen.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#19)]  
  
     Sie rufen den Lambda\-Ausdruck auf, indem Sie ein Ganzzahlargument übergeben.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#20)]  
  
### So erstellen Sie eine mehrzeilige Unterroutine mit einem Lambda\-Ausdruck  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, wie im folgenden Beispiel veranschaulicht, das Schlüsselwort `Sub` ein:  
  
     `Dim add1 =`   `Sub`  
  
2.  Geben Sie direkt nach `Sub` in Klammern die Parameter der Unterroutine ein.  Beachten Sie, dass nach `Sub` kein Name festgelegt wird.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Drücken Sie die EINGABETASTE.  Die `End Sub`\-Anweisung wird automatisch hinzugefügt.  
  
4.  Fügen Sie im Text der Funktion den folgenden Code hinzu, der beim Aufrufen der Unterroutine ausgeführt werden soll.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#21)]  
  
     Sie rufen den Lambda\-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#22)]  
  
## Beispiel  
 Eine häufige Verwendung von Lambda\-Ausdrücken ist das Definieren einer Funktion, die als Argument für einen Parameter vom Typ `Delegate` übergeben werden kann.  Im folgenden Beispiel wird von der <xref:System.Diagnostics.Process.GetProcesses%2A>\-Methode ein Array der Prozesse zurückgegeben, die auf dem lokalen Computer ausgeführt werden.  Für die <xref:System.Linq.Enumerable.Where%2A>\-Methode der <xref:System.Linq.Enumerable>\-Klasse ist ein `Boolean`\-Delegat als Argument erforderlich.  Zu diesem Zweck wird im Beispiel der Lambda\-Ausdruck verwendet.  Er gibt `True` für alle Prozesse mit nur einem Thread zurück, und diese werden in der `filteredList` ausgewählt.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class4.vb#10)]  
  
 Das vorherige Beispiel ist äquivalent zu folgendem, in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)]\-Syntax geschriebenem Code:  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class5.vb#11)]  
  
## Siehe auch  
 <xref:System.Linq.Enumerable>   
 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)