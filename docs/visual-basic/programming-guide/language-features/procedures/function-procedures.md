---
title: "Function-Prozeduren (Visual Basic) | Microsoft Docs"
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
  - "Function-Prozeduren"
  - "Rückgabewerte, Function-Prozeduren"
  - "Visual Basic-Code, Prozeduren"
  - "Prozeduren, Aufrufen"
  - "Prozeduren, Function-Prozeduren"
  - "Syntax, Function-Prozeduren"
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Function-Prozeduren (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine `Function`\-Prozedur ist eine Reihe von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anweisungen, die von den Anweisungen `Function` und `End Function` eingeschlossen sind.  Die `Function`\-Prozedur führt eine Aufgabe aus und gibt die Steuerung dann an den Aufrufcode zurück.  Wenn sie die Steuerung zurückgibt, gibt sie auch einen Wert an den Aufrufcode zurück.  
  
 Bei jedem Aufruf der Prozedur werden ihre Anweisungen ausgeführt. Die Ausführung wird mit der ersten ausführbaren Anweisung nach der `Function`\-Anweisung begonnen und mit der ersten auftretenden `End Function`\-, `Exit Function`\- oder `Return`\-Anweisung beendet.  
  
 Sie können eine `Function`\-Prozedur in einem Modul, einer Klasse oder Struktur definieren.  Standardmäßig sind Function\-Prozeduren `Public`, d. h. sie können überall in der Anwendung aufgerufen werden, die Zugriff auf das Modul, die Klasse oder Struktur hat, in dem bzw. der die Prozedur definiert ist.  
  
 `Function`\-Prozeduren können Argumente \(z. B. Konstanten, Variablen oder Ausdrücke\) verarbeiten, die durch den Aufrufcode an sie übergeben werden.  
  
## Deklarationssyntax  
 Die Syntax zur Deklaration einer `Function`\-Prozedur lautet wie folgt:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Mithilfe von *Modifizierern* werden die Zugriffsebene und Informationen zum Überladen, Überschreiben, Freigeben und Shadowing angegeben.  Weitere Informationen hierzu finden Sie unter [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Sie deklarieren alle Parameter auf die gleiche Weise wie [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).  
  
### Datentyp  
 Ebenso wie Variablen weisen auch `Function`\-Prozeduren einen Datentyp auf.  Der Datentyp wird durch die `As`\-Klausel in der `Function`\-Anweisung festgelegt. Er bestimmt den Datentyp des Werts, den die Funktion an den Aufrufcode zurückgibt.  Die folgenden Beispieldeklarationen verdeutlichen dies.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Weitere Informationen finden Sie im Abschnitt "Bestandteile" unter [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## Rückgabewerte  
 Der Wert, den eine `Function` Prozedur zurück an den aufrufenden Code sendet, wird als Rückgabewert aufgerufen.  Die Prozedur gibt den Wert auf zwei Arten zurück:  
  
-   Hier wird mit der `Return`\-Anweisung der Rückgabewert angegeben, und die Steuerung wird sofort an das aufrufende Programm zurückgegeben.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ' The following statement immediately transfers control back  
        ' to the calling code and returns the value of Expression.  
        Return Expression  
    End Function  
    ```  
  
-   Sie weist ihrem eigenen Funktionsnamen in mindestens einer Anweisung der Prozedur einen Wert zu.  Die Steuerung wird solange nicht an das aufrufende Programm zurückgegeben, bis eine `Exit Function` oder `End Function` ausgeführt wird.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ‘ The following statement does not transfer control back to the calling code.  
        FunctionName = Expression  
        ' When control returns to the calling code, Expression is the return value.  
    End Function  
    ```  
  
 Der Vorteil beim Zuweisen des Rückgabewerts an den Funktionsnamen liegt darin, dass die Prozedur die Steuerung erst zurückgibt, wenn das Programm die Anweisung `Exit Function` oder `End Function` erreicht.  Dadurch können Sie einen vorläufigen Wert zuweisen und diesen gegebenenfalls später korrigieren.  
  
 Weitere Informationen zum Zurückgeben von Werten, finden Sie unter [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).  Informationen zum Zurückgeben von Arrays, finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Aufrufsyntax  
 Zum Aufrufen einer `Function`\-Prozedur geben Sie deren Namen und die Argumente entweder auf der rechten Seite einer Zuweisungsanweisung oder in einem Ausdruck an.  Sie müssen Werte für alle nicht optionalen Argumente angeben und die Argumentliste in Klammern setzen.  Wenn keine Argumente angegeben werden, können Sie die Klammern auch weglassen.  
  
 Die Syntax für den Aufruf einer `Function`\-Prozedur lautet wie folgt:  
  
 *l\-Wert* `=` *functionname* `[(` *argumentlist* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *Ausdruck* `) Then`  
  
 Wenn Sie eine `Function`\-Prozedur aufrufen, müssen Sie deren Rückgabewert nicht verwenden.  In diesem Fall werden sämtliche Aktionen der Funktion durchgeführt, der Rückgabewert wird jedoch ignoriert.  <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> wird oft auf diese Weise aufgerufen.  
  
### Darstellung von Deklaration und Aufruf  
 Mit der folgenden `Function`\-Prozedur wird die längste Seite \(die Hypotenuse\) eines rechtwinkligen Dreiecks anhand der Werte der beiden anderen Seiten berechnet.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 Im folgenden Beispiel wird ein typischer Aufruf von `hypotenuse` gezeigt.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [How to: Create a Procedure that Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [How to: Return a Value from a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)