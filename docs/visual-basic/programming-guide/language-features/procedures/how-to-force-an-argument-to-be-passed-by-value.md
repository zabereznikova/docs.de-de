---
title: "How to: Force an Argument to Be Passed by Value (Visual Basic) | Microsoft Docs"
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
  - "procedures, arguments"
  - "procedures, parameters"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], ByVal"
  - "arguments [Visual Basic], passing by value"
  - "procedure parameters"
  - "procedures, calling"
  - "arguments [Visual Basic], in parentheses"
  - "procedure arguments, in parentheses"
  - "arguments [Visual Basic], changing value"
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Force an Argument to Be Passed by Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Der Übergabemechanismus richtet sich nach der Prozedurdeklaration.  Wenn ein Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) deklariert wird, geht [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] davon aus, dass das entsprechende Argument als Verweis zu übergeben ist.  Auf diese Weise kann die Prozedur den Wert des Programmierelements ändern, der dem Argument im Aufrufcode zugrunde liegt.  Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie den `ByRef`\-Übergabemechanismus im Prozeduraufruf überschreiben, indem Sie den Argumentnamen in Klammern einschließen.  Diese Klammern kommen zu den Klammern hinzu, von denen die Argumentliste im Aufruf eingeschlossen ist.  
  
 Der Aufrufcode kann einen [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Mechanismus nicht überschreiben.  
  
### So erzwingen Sie die Übergabe eines Arguments als Wert  
  
-   Wenn der entsprechende Parameter in der Prozedur als `ByVal` deklariert wird, müssen Sie keine zusätzlichen Schritte ausführen.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] geht bereits davon aus, dass das Argument als Wert übergeben wird.  
  
-   Wenn der entsprechende Parameter in der Prozedur als `ByRef` deklariert wird, schließen Sie das Argument im Prozeduraufruf in Klammern ein.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `ByRef`\-Parameterdeklaration überschrieben.  Beachten Sie im Aufruf, mit dem `ByVal` erzwungen wird, die beiden Klammerebenen.  
  
 [!code-vb[VbVbcnProcedures#39](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-force-an-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-force-an-argument_2.vb)]  
  
 Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist, kann die `setNewString`\-Prozedur diesen Wert im Aufrufcode nicht ändern, und im `MsgBox` wird "Cannot be replaced if passed ByVal" angezeigt.  Wenn `str` nicht von zusätzlichen Klammern eingeschlossen ist, kann die Prozedur den Wert ändern. `MsgBox` zeigt daraufhin "This is a new value for the inString argument." an.  
  
## Kompilieren des Codes  
 Die Variablenübergabe durch Verweis muss mit dem `ByRef`\-Schlüsselwort angegeben werden.  
  
 Standardmäßig werden Argumente in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] als Wert übergeben.  Beim Programmieren empfiehlt es sich jedoch, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Schlüsselwort oder das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Schlüsselwort in jeden deklarierten Parameter aufzunehmen.  Dadurch wird der Code besser lesbar.  
  
## Robuste Programmierung  
 Wenn eine Prozedur eine [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Parameterdeklaration verwendet, kann die richtige Ausführung des Codes davon abhängen, ob das zugrunde liegende Element im Aufrufcode geändert werden kann.  Wenn der Aufrufcode diesen Aufrufmechanismus überschreibt, indem das Argument in Klammern eingeschlossen wird, oder wenn der Code ein unveränderliches Argument übergibt, kann die Prozedur das zugrunde liegende Element nicht ändern.  Dies kann im Aufrufcode unerwartete Ergebnisse zur Folge haben.  
  
## .NET Framework-Sicherheit  
 Wenn Sie den Wert, der einem Argument im Aufrufcode zugrunde liegt, von einer Prozedur ändern lassen, stellt dies stets ein gewisses Risiko dar.  Stellen Sie sicher, dass Sie mit der Änderung des Werts einverstanden sind, und überprüfen Sie die Gültigkeit des Werts, bevor Sie ihn verwenden.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)