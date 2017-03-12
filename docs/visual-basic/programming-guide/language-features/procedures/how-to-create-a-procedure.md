---
title: "How to: Create a Procedure (Visual Basic) | Microsoft Docs"
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
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "Visual Basic code, reusing"
  - "procedure declarations"
  - "procedures, about procedures"
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# How to: Create a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Eine Prozedur wird von einer einleitenden Deklarationsanweisung \(`Sub` oder `Function`\) und einer abschließenden Deklarationsanweisung \(`End Sub` oder `End Function`\) eingeschlossen.  Der gesamte Code der Prozedur befindet sich zwischen diesen Anweisungen.  
  
 Eine Prozedur kann keine andere Prozedur enthalten, deshalb müssen sich ihre einleitenden und abschließenden Anweisungen außerhalb jeder anderen Prozedur befinden.  
  
 Wenn Ihr Code die gleiche Aufgaben an verschiedenen Stellen ausführt, können Sie die Aufgabe einmal als Prozedur schreiben und sie anschließend von verschiedenen Codeabschnitten aus aufrufen.  
  
### So erstellen Sie eine Prozedur, die keinen Wert zurückgibt  
  
1.  Verwenden Sie außerhalb anderer Prozeduren eine `Sub`\-Anweisung, auf die eine `End Sub`\-Anweisung folgt.  
  
2.  Geben Sie in der `Sub`\-Anweisung nach dem `Sub`\-Schlüsselwort den Namen der Prozedur und danach die Parameterliste in runden Klammern ein.  
  
3.  Setzen Sie die Codeanweisungen der Prozedur zwischen die `Sub`\-Anweisung und die `End Sub`\-Anweisung.  
  
### So erstellen Sie eine Prozedur, die einen Wert zurückgibt  
  
1.  Verwenden Sie außerhalb anderer Prozeduren eine `Function`\-Anweisung, auf die eine `End Function`\-Anweisung folgt.  
  
2.  Geben Sie in der `Function`\-Anweisung nach dem `Function`\-Schlüsselwort den Namen der Prozedur, die Parameterliste in Klammern und anschließend eine `As`\-Klausel ein, mit der der Datentyp des Rückgabewerts festgelegt wird.  
  
3.  Setzen Sie die Codeanweisungen der Prozedur zwischen die Anweisungen `Function` und `End Function`.  
  
4.  Verwenden Sie eine `Return`\-Anweisung, um den Wert an den Aufrufcode zurückzugeben.  
  
### So verbinden Sie die neue Prozedur mit den alten wiederkehrenden Codeblöcken  
  
1.  Definieren Sie die neue Prozedur an einer Stelle, an der der alte Code darauf zugreifen kann.  
  
2.  Ersetzen Sie im alten wiederkehrenden Codeblock die Anweisungen zur Durchführung der wiederkehrenden Aufgabe durch eine Anweisung, die die `Sub`\-Prozedur oder die `Function`\-Prozedur aufruft.  
  
3.  Wenn es sich bei der Prozedur um eine `Function`\-Prozedur handelt, die einen Wert zurückgibt, müssen Sie sicherstellen, dass die aufrufende Anweisung eine Aktion mit dem zurückgegebenen Wert ausführt, dass der Wert z. B. in einer Variablen gespeichert wird. Andernfalls geht der Wert verloren.  
  
## Beispiel  
 Mit der folgenden `Function`\-Prozedur wird die längste Seite \(die Hypotenuse\) eines rechtwinkligen Dreiecks anhand der Werte der beiden anderen Seiten berechnet.  
  
 [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-create-a-procedure_1.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Objektorientiertes Programmieren](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)