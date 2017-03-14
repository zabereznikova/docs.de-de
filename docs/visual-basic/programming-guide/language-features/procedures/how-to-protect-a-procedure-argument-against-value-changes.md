---
title: "How to: Protect a Procedure Argument Against Value Changes (Visual Basic) | Microsoft Docs"
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
  - "procedures, calling"
  - "arguments [Visual Basic], ByRef"
  - "arguments [Visual Basic], changing value"
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Protect a Procedure Argument Against Value Changes (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wenn eine Prozedur einen Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) deklariert, übergibt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] einen direkten Verweis auf das Programmierelement, das dem Argument im Aufrufcode zugrunde liegt, an denProzedurcode.  Damit kann die Prozedur den Wert ändern, der dem Argument im Aufrufcode zugrunde liegt.  In bestimmten Fällen sollte der Aufrufcode eine solche Änderung verhindern.  
  
 Sie können ein Argument stets vor einer Änderung schützen, indem Sie den entsprechenden Parameter in der Prozedur als [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) deklarieren.  Wenn Sie ein Argument nur in bestimmten Fällen ändern können möchten, deklarieren Sie es als `ByRef`, und lassen Sie den Übergabemechanismus in jedem Aufruf vom Aufrufcode festlegen.  Dabei wird das entsprechende Argument in runde Klammern eingeschlossen, um es als Wert zu übergeben, bzw. es wird nicht in Klammern eingeschlossen, um es als Verweis zu übergeben.  Weitere Informationen finden Sie unter [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md).  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Prozeduren gezeigt, die eine Arrayvariable übernehmen und auf deren Elemente anwenden.  Mit der `increase`\-Prozedur wird einfach 1 zu jedem Element addiert.  Mit der `replace`\-Prozedur wird dem Parameter `a()` ein neues Array zugewiesen und zu jedem Element 1 addiert.  Die Neuzuweisung wirkt sich jedoch nicht auf die zugrunde liegende Arrayvariable im Aufrufcode aus.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 Beim ersten `MsgBox`\-Aufruf wird Folgendes angezeigt: "After increase\(n\): 11, 21, 31, 41".  Da das Array `n` ein Verweistyp ist, kann `replace` dessen Member ändern, obwohl der Übergabemechanismus `ByVal` ist.  
  
 Beim zweiten `MsgBox`\-Aufruf wird Folgendes angezeigt: "After replace\(n\): 11, 21, 31, 41".  Da `n` mit `ByVal` übergeben wird, kann `replace` die Variable `n` im Aufrufcode durch Zuweisen eines neuen Arrays nicht ändern.  Wenn `replace` die neue Arrayinstanz `k` erstellt und diese der lokalen Variablen `a`zuweist, geht der im Aufrufcode übergebene Verweis auf `n` verloren.  Wenn die Member von `a`geändert werden, wirkt sich dies nur auf das lokale Array `k` aus.  Deshalb inkrementiert `replace` die Werte von Array `n` im Aufrufcode nicht.  
  
## Kompilieren des Codes  
 Standardmäßig werden Argumente in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] als Wert übergeben.  Beim Programmieren empfiehlt es sich jedoch, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Schlüsselwort oder das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Schlüsselwort in jeden deklarierten Parameter aufzunehmen.  Dadurch wird der Code besser lesbar.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)