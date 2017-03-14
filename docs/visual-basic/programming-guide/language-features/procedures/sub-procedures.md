---
title: "Sub Procedures (Visual Basic) | Microsoft Docs"
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
  - "Sub procedures, about Sub procedures"
  - "statement blocks"
  - "Sub procedures, calling"
  - "procedures, calling"
  - "Sub procedures, syntax"
  - "Sub procedures"
  - "procedures, Sub"
  - "syntax, Sub procedures"
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Sub Procedures (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine `Sub`\-Prozedur ist eine Reihe von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anweisungen, die von den Anweisungen `Sub` und `End Sub` eingeschlossen sind.  Die `Sub`\-Prozedur führt eine Aufgabe aus und gibt die Steuerung anschließend an den Aufrufcode zurück; sie gibt dem Aufrufcode jedoch keinen Wert zurück.  
  
 Bei jedem Aufruf der Prozedur werden ihre Anweisungen ausgeführt. Dabei wird mit der ersten ausführbaren Anweisung nach der `Sub`\-Anweisung begonnen und mit der ersten auftretenden `End Sub`\-, `Exit Sub`\- oder `Return`\-Anweisung geendet.  
  
 `Sub`\-Prozeduren können in Modulen, Klassen und Strukturen definiert werden.  Sie sind standardmäßig als `Public` definiert. Sie können sie an jeder Stelle im Code Ihrer Anwendung aufrufen, der Zugriff auf das Modul, die Klasse oder die Struktur hat, in der sie definiert sind.  Die Bezeichnung *Methode* beschreibt eine `Sub`\-Prozedur oder `Function`\-Prozedur, die außerhalb des Moduls, der Klasse oder der Struktur aufgerufen wird, in der sie definiert ist.  Weitere Informationen finden Sie unter [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md).  
  
 Eine `Sub`\-Prozedur kann Argumente wie Konstanten, Variablen oder Ausdrücke annehmen, die durch den Aufrufcode an sie übergeben werden.  
  
## Deklarationssyntax  
 Die Syntax zur Deklaration einer `Sub`\-Prozedur lautet wie folgt:  
  
 `[` *Modifizierer* `] Sub`  *Subname* `[(` *Parameterliste* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Mithilfe von `modifiers` werden die Zugriffsebene und Informationen zum Überladen, Überschreiben, Freigeben und Shadowing angegeben.  Weitere Informationen finden Sie unter [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Parameterdeklaration  
 Jeder Prozedurparameter wird ähnlich wie eine Variable deklariert, nämlich durch Angabe des Parameternamens und des Datentyps.  Sie können auch den Übergabemechanismus festlegen und bestimmen, ob der Parameter optional oder ein Parameterarray ist.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet folgendermaßen:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *Parametername*  `As`  *Datentyp*  
  
 Wenn der Parameter optional ist, müssen Sie bei seiner Deklaration auch einen Standardwert angeben.  Die Syntax zur Angabe eines Standardwerts lautet folgendermaßen:  
  
 `Optional [ByVal | ByRef]`  *Parametername*  `As`  *Datentyp*  `=`  *Standardwert*  
  
### Parameter als lokale Variablen  
 Wenn die Steuerung an die Prozedur übergeben wird, wird jeder Parameter als lokale Variable behandelt.  Dies bedeutet, dass die Lebensdauer der Parameter derjenigen der Prozedur entspricht und ihr Gültigkeitsbereich die gesamte Prozedur umfasst.  
  
## Aufrufsyntax  
 `Sub`\-Prozeduren werden explizit mit eigenständigen Aufrufanweisungen aufgerufen.  Sie können nicht unter Verwendung ihres Namens in einem Ausdruck aufgerufen werden.  Sie müssen Werte für alle nicht optionalen Argumente angeben und die Argumentliste in Klammern setzen.  Wenn keine Argumente angegeben werden, können Sie die Klammern auch weglassen.  Die Verwendung des `Call`\-Schlüsselworts ist optional, wird aber empfohlen.  
  
 Die Syntax für den Aufruf einer `Sub`\-Prozedur lautet wie folgt:  
  
 `[Call]`  *Subname* `[(` *Argumentliste* `)]`  
  
 Sie können eine `Sub`\-Methode außerhalb der Klasse aufrufen, in der sie definiert ist.  Zunächst müssen Sie mithilfe des `New`\-Schlüsselworts eine Instanz der Klasse erstellen oder eine Methode aufrufen, die eine Instanz der Klasse zurückgibt.  Weitere Informationen finden Sie unter [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).  Anschließend können Sie die folgende Syntax verwenden, um die `Sub`\-Methode für das Instanzobjekt aufzurufen:  
  
 *Objekt*.*Methodenname*`[(`*Argumentliste*`)]`  
  
### Darstellung von Deklaration und Aufruf  
 Die folgende `Sub`\-Prozedur meldet den Computerbenutzern, welche Aufgabe die Anwendung als nächste ausführt. Außerdem wird ein Timestamp angezeigt.  Anstatt den Code zu Beginn jeder Aufgabe zu duplizieren, wird  `tellOperator` von verschiedenen Stellen durch die Anwendung aufgerufen.  Bei jedem Aufruf wird eine Zeichenfolge an das `task` \-Argument übergeben, die die gestartete Aufgabe identifiziert.  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 Im folgenden Beispiel wird ein typischer Aufruf von `tellOperator` dargestellt.  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)   
 [How to: Call an Event Handler in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)