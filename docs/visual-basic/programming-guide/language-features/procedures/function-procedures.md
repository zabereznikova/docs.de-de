---
title: Function-Prozeduren
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: b0ba96a875fd8785e45eee565beefe4b961ffc9d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388750"
---
# <a name="function-procedures-visual-basic"></a>Funktions Prozeduren (Visual Basic)

Eine `Function` Prozedur ist eine Reihe von Visual Basic-Anweisungen, die von den `Function` Anweisungen und eingeschlossen werden `End Function` . Die `Function` Prozedur führt eine Aufgabe aus und gibt dann die Steuerung an den aufrufenden Code zurück. Wenn die Steuerung zurückgegeben wird, wird auch ein Wert an den aufrufenden Code zurückgegeben.

Jedes Mal, wenn die Prozedur aufgerufen wird, werden Ihre-Anweisungen ausgeführt, beginnend mit der ersten ausführbaren Anweisung nach der `Function` -Anweisung und endende mit der ersten `End Function` , `Exit Function` , oder- `Return` Anweisung.

Sie können eine `Function` Prozedur in einem Modul, einer Klasse oder einer Struktur definieren. Dies `Public` bedeutet standardmäßig, dass Sie Sie von überall in Ihrer Anwendung aufrufen können, die Zugriff auf das Modul, die Klasse oder die Struktur hat, in der Sie Sie definiert haben.

Eine `Function` Prozedur kann Argumente, wie z. b. Konstanten, Variablen oder Ausdrücke, verwenden, die vom aufrufenden Code an Sie übermittelt werden.

## <a name="declaration-syntax"></a>Deklarations Syntax

Die Syntax zum Deklarieren einer `Function` Prozedur lautet wie folgt:

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

Die *Modifizierer* können Zugriffsebene und Informationen zum überschreiben, überschreiben, freigeben und shadoading angeben. Weitere Informationen finden Sie unter [Function-Anweisung](../../../language-reference/statements/function-statement.md).

Sie deklarieren jeden Parameter auf dieselbe Weise wie für [unter Prozeduren](./sub-procedures.md).

### <a name="data-type"></a>Datentyp

Jede `Function` Prozedur weist einen Datentyp auf, so wie jede Variable dies tut. Dieser Datentyp wird von der `As` -Klausel in der `Function` -Anweisung angegeben und bestimmt den Datentyp des Werts, der von der Funktion an den aufrufenden Code zurückgegeben wird. Dies wird in den folgenden Beispiel Deklarationen veranschaulicht.

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

Weitere Informationen finden Sie unter "Parts" in der [Function-Anweisung](../../../language-reference/statements/function-statement.md).

### <a name="returning-values"></a>Zurückgeben von Werten

Der Wert, den eine `Function` Prozedur an den aufrufenden Code zurücksendet, wird als Rückgabewert bezeichnet. Die Prozedur gibt diesen Wert auf zwei Arten zurück:

- Dabei wird die `Return` -Anweisung verwendet, um den Rückgabewert anzugeben, und die Steuerung wird sofort an das aufrufenden Programm zurückgegeben. Dies wird anhand des folgenden Beispiels veranschaulicht.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- In einer oder mehreren Anweisungen der Prozedur wird dem eigenen Funktionsnamen ein Wert zugewiesen. Das-Steuerelement kehrt erst zum aufrufenden Programm zurück, wenn eine- `Exit Function` oder- `End Function` Anweisung ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

Der Vorteil der Zuweisung des Rückgabewerts zum Funktionsnamen besteht darin, dass das Steuerelement nicht von der Prozedur zurückgegeben wird, bis auf eine- `Exit Function` oder- `End Function` Anweisung stößt. Dies ermöglicht es Ihnen, einen vorläufigen Wert zuzuweisen und ihn später bei Bedarf anzupassen.

Weitere Informationen zum Zurückgeben von Werten finden Sie unter [Function-Anweisung](../../../language-reference/statements/function-statement.md). Weitere Informationen zum Zurückgeben von Arrays finden Sie unter [Arrays](../arrays/index.md).

## <a name="calling-syntax"></a>Aufruf Syntax

Sie rufen eine `Function` Prozedur auf, indem Sie den Namen und die Argumente entweder auf der rechten Seite einer Zuweisungsanweisung oder in einem Ausdruck einschließen. Sie müssen Werte für alle nicht optionalen Argumente angeben, und Sie müssen die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.

Die Syntax für einen aufzurufenden `Function` Vorgang ist wie folgt.

*Lvalue* `=` *FunctionName* `[(` Argument *Liste*    `)]`

`If ((`*FunctionName* `[(` Argument *Liste* `)] / 3) <=` *Ausdruck*  `) Then`

Wenn Sie eine Prozedur aufzurufen `Function` , müssen Sie ihren Rückgabewert nicht verwenden. Andernfalls werden alle Aktionen der Funktion ausgeführt, aber der Rückgabewert wird ignoriert. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>wird häufig auf diese Weise aufgerufen.

### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und des Aufruf

Im folgenden `Function` Verfahren wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten angegeben werden.

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

Das folgende Beispiel zeigt einen typischen-Rückruf `hypotenuse` .

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../language-reference/statements/function-statement.md)
- [Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
