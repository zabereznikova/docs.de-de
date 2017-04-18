---
title: Function-Prozeduren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 11baaa6985f0681aa9c67c4f2470fb9917db5b78
ms.lasthandoff: 03/13/2017

---
# <a name="function-procedures-visual-basic"></a>Function-Prozeduren (Visual Basic)
Ein `Function` Prozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anweisungen, die durch die `Function` und `End Function` Anweisungen. Die `Function` Prozedur eine Aufgabe ausführt, und dann wird die Steuerung an den aufrufenden Code zurückgegeben. Wenn sie die Steuerung zurückgibt, gibt auch einen Wert an den aufrufenden Code zurück.  
  
 Jedes Mal die Prozedur aufgerufen wird, werden ihre Anweisungen ausgeführt werden, beginnend mit der ersten ausführbaren Anweisung nach der `Function` -Anweisung und endet mit dem ersten `End Function`, `Exit Function`, oder `Return` Anweisung aufgetreten.  
  
 Sie können eine `Function` Prozedur in einem Modul, Klasse oder Struktur. Es ist `Public` standardmäßig d. h. Sie können überall aufrufen in der Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, in der Sie definiert, wurde.  
  
 Ein `Function` -Prozeduren können Argumente, wie z. B. Konstanten, Variablen oder Ausdrücke, die durch den Aufrufcode an sie übergeben werden.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer `Function` Prozedur lautet wie folgt:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Die *Modifizierer* Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing angeben können. Weitere Informationen finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Sie deklarieren jeden Parameter auf die gleiche Weise bei [Sub-Prozeduren](./sub-procedures.md).  
  
### <a name="data-type"></a>Datentyp  
 Jede `Function` Prozedur verfügt über einen Datentyp, ebenso wie Variablen enthält. Dieser Datentyp wird angegeben, indem die `As` -Klausel in der `Function` -Anweisung, und es bestimmt den Datentyp des Werts an den aufrufenden Code zurückgegeben. Die folgenden Beispieldeklarationen veranschaulicht.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Weitere Informationen finden Sie unter "Webparts" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Zurückgeben von Werten  
 Der Wert einer `Function` sendet ihren Rückgabewert zurück an den aufrufenden Code aufgerufen. Die Prozedur gibt diesen Wert zurück, auf zwei Arten:  
  
-   Er verwendet die `Return` Anweisung an den Rückgabewert und gibt die Steuerung wird sofort an das aufrufende Programm. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Eigene Funktionsnamen in eine oder mehrere Anweisungen der Prozedur wird ein Wert zugewiesen. Steuerung ist nicht an das aufrufende Programm, bis ein `Exit Function` oder `End Function` ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Der Vorteil den Rückgabewert dem Funktionsnamen weisen ist die Steuerung von der Prozedur zurückgibt, bis zum Erreichen einer `Exit Function` oder `End Function` Anweisung. Dadurch können Sie einen vorläufigen Wert zuweisen und ihn später bei Bedarf anpassen.  
  
 Weitere Informationen zum Zurückgeben von Werten, finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md). Informationen zum Zurückgeben von Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Rufen Sie eine `Function` Prozedur durch den Namen und die Argumente, die entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck einschließen. Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben sind, können Sie die Klammern auch weglassen.  
  
 Die Syntax für einen Aufruf einer `Function` Prozedur lautet wie folgt:  
  
 *Lvalue*`=`*Funktionsname* `[(` *Argumentlist*    `)]`  
  
 `If ((`*Funktionsname* `[(` *Argumentlist* `)] / 3) <=` *Ausdruck*  `) Then`  
  
 Beim Aufruf einer `Function` Prozedur, Sie müssen keinen Rückgabewert verwenden. Wenn Sie nicht sämtliche Aktionen der Funktion durchgeführt werden, der Rückgabewert wird jedoch ignoriert. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>auf diese Weise wird häufig aufgerufen werden.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
### <a name="illustration-of-declaration-and-call"></a>Darstellung von Deklaration und Aufruf  
 Die folgenden `Function` -Prozedur wird die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks anhand der Werte der beiden anderen Seiten berechnet.  
  
 [!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt einen normalen Aufruf `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Gewusst wie: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)   
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
