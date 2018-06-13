---
title: Function-Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 887c930cb757b012542c97d64a57a62882a2eed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655534"
---
# <a name="function-procedures-visual-basic"></a>Function-Prozeduren (Visual Basic)
Ein `Function` Verfahren besteht aus einer Reihe von Visual Basic-Anweisungen von der `Function` und `End Function` Anweisungen. Die `Function` Prozedur, eine Aufgabe ausführt, und klicken Sie dann die Steuerung an den aufrufenden Code zurückgegeben. Wenn er die Steuerung zurückgibt, gibt es auch einen Wert an den aufrufenden Code zurück.  
  
 Jedes Mal, die die Prozedur aufgerufen wird, werden die Anweisungen ausgeführt werden, beginnend mit der ersten ausführbaren Anweisung nach der `Function` -Anweisung und endet mit dem ersten `End Function`, `Exit Function`, oder `Return` Anweisung wurde gefunden.  
  
 Sie können definieren, eine `Function` Prozedur in einem Modul, Klasse oder Struktur. Es ist `Public` standardmäßig, d. h. Sie können von überall aus aufrufen in der Anwendung, die Zugriff auf das Modul, Klasse oder Struktur an, in dem Sie definiert, wurde.  
  
 Ein `Function` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer `Function` Prozedur lautet wie folgt:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Die *Modifizierer* Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing angeben können. Weitere Informationen finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Deklarieren Sie jeden Parameter genauso wie Sie für [Sub-Prozeduren](./sub-procedures.md).  
  
### <a name="data-type"></a>Datentyp  
 Jede `Function` Prozedur verfügt über einen Datentyp, ebenso wie Variablen enthält. Dieser Datentyp wird angegeben, indem die `As` -Klausel in der `Function` -Anweisung, und er ermittelt den Datentyp des Werts, der die Funktion an den aufrufenden Code zurückgibt. Die folgenden Beispieldeklarationen veranschaulicht.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Weitere Informationen finden Sie unter "Teilen" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Zurückgeben von Werten  
 Der Wert einer `Function` Prozedur sendet zurück an den aufrufenden Code den Rückgabewert aufgerufen wird. Die Prozedur gibt diesen Wert zurück, auf zwei Arten:  
  
-   Er verwendet die `Return` Anweisung an den Rückgabewert, und gibt die Steuerung wird sofort an das aufrufende Programm. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Eigene Funktionsnamen in eine oder mehrere Anweisungen der Prozedur wird ein Wert zugewiesen. Steuerung ist nicht an das aufrufende Programm, bis ein `Exit Function` oder `End Function` -Anweisung ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Der Vorteil den Rückgabewert für den Namen der Funktion zuzuweisen ist die Steuerung erst gefundenen nicht aus der Prozedur zurückgegeben wird ein `Exit Function` oder `End Function` Anweisung. Dadurch können Sie einen vorläufigen Wert zuweisen und sie später bei Bedarf anpassen.  
  
 Weitere Informationen zum Zurückgeben von Werten finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md). Weitere Informationen zu Arrays zurückgeben, finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Rufen Sie eine `Function` Prozedur durch den Namen und die Argumente, die entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck einschließen. Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente übergeben werden, können Sie die Klammern optional weglassen.  
  
 Die Syntax für einen Aufruf einer `Function` Prozedur lautet wie folgt:  
  
 *Lvalue*`=`*Funktionsname* `[(` *Argumentlist*  `)]`  
  
 `If ((` *Funktionsname* `[(` *Argumentlist* `)] / 3) <=` *Ausdruck*  `) Then`  
  
 Beim Aufruf einer `Function` Prozedur, Sie müssen nicht den Rückgabewert verwenden. Wenn Sie nicht alle Aktionen, die sich von der Funktion ausgeführt werden, aber der Rückgabewert wird ignoriert. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> auf diese Weise wird häufig aufgerufen werden.  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt einen typischen Aufruf `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
