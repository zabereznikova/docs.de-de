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
ms.openlocfilehash: 568489d6034316e895cd999801241fa995aadefa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864402"
---
# <a name="function-procedures-visual-basic"></a>Function-Prozeduren (Visual Basic)
Ein `Function` Prozedur ist eine Reihe von Visual Basic Anweisungen durch die `Function` und `End Function` Anweisungen. Die `Function` Prozedur führt eine Aufgabe aus und gibt dann die Steuerung an den aufrufenden Code zurück. Wenn er die Steuerung zurückgibt, gibt es auch einen Wert an den aufrufenden Code zurück.  
  
 Jedes Mal, die die Prozedur aufgerufen wird, werden die Anweisungen ausgeführt werden, wobei die erste ausführbare Anweisung nach der `Function` -Anweisung und beendet mit dem ersten `End Function`, `Exit Function`, oder `Return` Anweisung wurde gefunden.  
  
 Sie können definieren, eine `Function` Prozedur in einem Modul, Klasse oder Struktur. Es ist `Public` standardmäßig also können Sie ihn aufrufen, von überall aus in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, die in der Sie definiert wurde.  
  
 Ein `Function` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer `Function` Verfahren lautet wie folgt:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Die *Modifizierer* Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing angeben können. Weitere Informationen finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Jeder Parameter deklariert die gleiche Weise für [Sub-Prozeduren](./sub-procedures.md).  
  
### <a name="data-type"></a>Datentyp  
 Jede `Function` Prozedur verfügt über einen Datentyp, ebenso wie Variablen verfügt. Dieser Datentyp wird angegeben, durch die `As` -Klausel in der `Function` -Anweisung, und bestimmt den Datentyp des Werts an die Funktion an den aufrufenden Code zurückgibt. Die folgenden Beispieldeklarationen veranschaulicht.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Weitere Informationen finden Sie unter "Teile" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Zurückgeben von Werten  
 Der Wert einer `Function` sendet zurück an den aufrufenden Code wird den Rückgabewert aufgerufen. Die Prozedur gibt diesen Wert zurück, auf zwei Arten:  
  
- Er verwendet den `Return` Anweisung an den Rückgabewert, und gibt die Steuerung wird sofort an das aufrufende Programm. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- Es wird eine eigene Funktionsnamen in eine oder mehrere Anweisungen der Prozedur ein Wert zugewiesen. Steuerung wird nicht zurückgegeben, an das aufrufende Programm, bis ein `Exit Function` oder `End Function` -Anweisung ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Der Vorteil, den Namen der Funktion den Rückgabewert zugewiesen ist, dass das Steuerelement nicht von der Prozedur erst zurückgegeben wird, es findet ein `Exit Function` oder `End Function` Anweisung. Dadurch können Sie einen vorläufigen Wert zuweisen, und sie später bei Bedarf anpassen.  
  
 Weitere Informationen zur Rückgabe von Werten finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md). Informationen zur Rückgabe von Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Die Syntax aufrufen  
 Rufen Sie eine `Function` Prozedur einschließlich der Namen und die Argumente, die entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck. Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.  
  
 Die Syntax für einen Aufruf einer `Function` Verfahren lautet wie folgt:  
  
 *l-Wert*`=`*Functionname* `[(` *Argumentlist* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`  
  
 Beim Aufruf einer `Function` vor, Sie müssen nicht den Rückgabewert zu verwenden. Wenn Sie dies nicht tun, werden alle Aktionen der Funktion ausgeführt, aber der Rückgabewert wird ignoriert. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> auf diese Weise wird häufig aufgerufen werden.  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgenden `Function` Prozedur berechnet werden, die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 Das folgende Beispiel zeigt einen typischen Aufruf von `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt.](./how-to-create-a-procedure-that-returns-a-value.md)
- [Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.](./how-to-call-a-procedure-that-returns-a-value.md)
