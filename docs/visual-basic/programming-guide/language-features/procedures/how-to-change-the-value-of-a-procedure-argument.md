---
title: "How to: Change the Value of a Procedure Argument (Visual Basic) | Microsoft Docs"
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
  - "arguments [Visual Basic], passing by reference"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], ByVal"
  - "arguments [Visual Basic], passing by value"
  - "procedure parameters"
  - "arguments [Visual Basic], ByRef"
  - "arguments [Visual Basic], changing value"
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Change the Value of a Procedure Argument (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Im Aufruf einer Prozedur entspricht jedes Argument, das angegeben wird, einem der in der Prozedur definierten Parameter.  In einigen Fällen kann der Prozedurcode den Wert ändern, der einem Argument im Aufrufcode zugrunde liegt.  In anderen Fällen kann die Prozedur nur ihre lokale Kopie eines Arguments ändern.  
  
 Wenn Sie die Prozedur aufrufen, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] von jedem Argument, das mit [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) übergeben wird, eine lokale Kopie.  Für jedes mit [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) übergebene Argument übergibt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] der Prozedur einen direkten Verweis auf das Programmierelement, das dem Argument im Aufrufcode zugrunde liegt.  
  
 Falls es sich bei dem zugrunde liegenden Element im Aufrufcode um ein änderbares Element handelt und das Argument mit `ByRef` übergeben wird, kann der Prozedurcode über den direkten Verweis den Wert des Elements im Aufrufcode ändern.  
  
## Ändern des zugrunde liegenden Werts  
  
#### So ändern Sie den zugrunde liegenden Wert eines Prozedurarguments im Aufrufcode  
  
1.  Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter an, der dem Argument entspricht.  
  
2.  Übergeben Sie im Aufrufcode ein änderbares Programmierelement als Argument.  
  
3.  Schließen Sie im Aufrufcode das Argument in der Argumentliste nicht in Klammern ein.  
  
4.  Verwenden Sie im Prozedurcode den Parameternamen, um dem zugrunde liegenden Element im Aufrufcode einen Wert zuzuweisen.  
  
 Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
## Ändern von lokalen Kopien  
 Wenn es sich beim zugrunde liegenden Element im Aufrufcode um ein nicht änderbares Element handelt, oder wenn das Argument mit `ByVal` übergeben wird, kann die Prozedur dessen Wert im Aufrufcode nicht ändern.  Die Prozedur kann jedoch die lokale Kopie eines solchen Arguments ändern.  
  
#### So ändern Sie die Kopie eines Prozedurarguments im Prozedurcode  
  
1.  Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter an, der dem Argument entspricht.  
  
     \- oder \-  
  
     Schließen Sie im Aufrufcode das Argument in der Argumentliste in Klammern ein.  Dadurch wird [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] gezwungen, das Argument als Wert zu übergeben, auch wenn für den entsprechenden Parameter `ByRef` angegeben wird.  
  
2.  Verwenden Sie im Prozedurcode den Parameternamen, um der lokalen Kopie des Arguments einen Wert zuzuweisen.  Der zugrunde liegende Wert im Aufrufcode wird nicht geändert.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Prozeduren gezeigt, die eine Arrayvariable übernehmen und auf deren Elemente anwenden.  Mit der `increase`\-Prozedur wird einfach 1 zu jedem Element addiert.  Mit der `replace`\-Prozedur wird dem Parameter `a()` ein neues Array zugewiesen und zu jedem Element 1 addiert.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-change-the-value-_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-change-the-value-_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-change-the-value-_3.vb)]  
  
 Beim ersten `MsgBox`\-Aufruf wird Folgendes angezeigt: "After increase\(n\): 11, 21, 31, 41".  Da das Array `n` ein Verweistyp ist, kann `replace` dessen Member ändern, obwohl der Übergabemechanismus `ByVal` ist.  
  
 Der zweite `MsgBox`\-Aufruf zeigt "After replace\(n\): 101, 201, 301" an.  Da `n` mit `ByRef` übergeben wird, kann `replace` die Variable `n` im Aufrufcode ändern und ihr ein neues Array zuweisen.  Weil `n` ein Verweistyp ist, kann `replace` auch seine Member ändern.  
  
 Sie können verhindern, dass die Prozedur die Variable im Aufrufcode ändert.  Weitere Informationen finden Sie unter [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## Kompilieren des Codes  
 Die Variablenübergabe durch Verweis muss mit dem `ByRef`\-Schlüsselwort angegeben werden.  
  
 Standardmäßig werden Argumente in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] als Wert übergeben.  Beim Programmieren empfiehlt es sich jedoch, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Schlüsselwort oder das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Schlüsselwort in jeden deklarierten Parameter aufzunehmen.  Dadurch wird der Code besser lesbar.  
  
## .NET Framework-Sicherheit  
 Wenn Sie den Wert, der einem Argument im Aufrufcode zugrunde liegt, von einer Prozedur ändern lassen, stellt dies stets ein gewisses Risiko dar.  Stellen Sie sicher, dass Sie mit der Änderung des Werts einverstanden sind, und überprüfen Sie die Gültigkeit des Werts, bevor Sie ihn verwenden.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)