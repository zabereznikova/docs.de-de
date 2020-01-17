---
title: Sub-Prozeduren
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163812"
---
# <a name="sub-procedures-visual-basic"></a>Unter Prozeduren (Visual Basic)

Eine `Sub` Prozedur ist eine Reihe von Visual Basic Anweisungen, die von den Anweisungen `Sub` und `End Sub` eingeschlossen werden. Die `Sub` Prozedur führt eine Aufgabe aus und gibt dann die Steuerung an den aufrufenden Code zurück, Sie gibt jedoch keinen Wert an den aufrufenden Code zurück.

Jedes Mal, wenn die Prozedur aufgerufen wird, werden die zugehörigen-Anweisungen ausgeführt, beginnend mit der ersten ausführbaren Anweisung nach der `Sub`-Anweisung und mit der ersten `End Sub`, `Exit Sub`oder `Return` Anweisung.

Sie können eine `Sub` Prozedur in Modulen, Klassen und Strukturen definieren. Standardmäßig ist es `Public`. Dies bedeutet, dass Sie es von überall in Ihrer Anwendung aufrufen können, das Zugriff auf das Modul, die Klasse oder die Struktur hat, in der Sie es definiert haben. Der Begriff *Methode* beschreibt eine `Sub` oder `Function` Prozedur, auf die von außerhalb des definierenden Moduls, der Klasse oder Struktur zugegriffen wird. Weitere Informationen finden Sie unter [Prozeduren](./index.md).

Eine `Sub` Prozedur kann Argumente, wie z. b. Konstanten, Variablen oder Ausdrücke, verwenden, die vom aufrufenden Code an ihn übermittelt werden.

## <a name="declaration-syntax"></a>Deklarations Syntax

Die Syntax zum Deklarieren einer `Sub` Prozedur lautet wie folgt:

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

Der `modifiers` kann die Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadoading angeben. Weitere Informationen finden Sie [unter Sub-Anweisung](../../../language-reference/statements/sub-statement.md).

## <a name="parameter-declaration"></a>Parameter Deklaration

Sie deklarieren jeden Prozedur Parameter entsprechend der Art und Weise, wie Sie eine Variable deklarieren, indem Sie den Parameternamen und Datentyp angeben. Sie können auch den Übergabe Mechanismus angeben und angeben, ob der Parameter optional ist, oder ein Parameter Array.

Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben eines Standardwerts lautet wie folgt:

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a>Parameter als lokale Variablen

Wenn die Steuerung an die Prozedur übergeben wird, wird jeder Parameter als lokale Variable behandelt. Dies bedeutet, dass die Lebensdauer der Prozedur entspricht und ihr Bereich das gesamte Verfahren ist.

## <a name="calling-syntax"></a>Aufruf Syntax

Sie rufen eine `Sub` Prozedur explizit mit einer eigenständigen aufrufenden Anweisung auf. Sie können Sie nicht mit dem Namen in einem Ausdruck abrufen. Sie müssen Werte für alle nicht optionalen Argumente angeben, und Sie müssen die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen. Die Verwendung des `Call`-Schlüssel Worts ist optional, wird aber nicht empfohlen.

Die Syntax für einen aufzurufenden `Sub` Prozeduren lautet wie folgt:

```vb
[Call] SubName[(argumentlist)]
```

Sie können eine `Sub` Methode von außerhalb der Klasse, die Sie definiert, abrufen. Zunächst müssen Sie das `New`-Schlüsselwort verwenden, um eine Instanz der-Klasse zu erstellen, oder eine Methode aufzurufen, die eine Instanz der-Klasse zurückgibt. Weitere Informationen finden Sie unter [New-Operator](../../../language-reference/operators/new-operator.md). Anschließend können Sie die folgende Syntax verwenden, um die `Sub`-Methode für das Instanzobjekt aufzurufen:

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und des Aufruf

Die folgende `Sub` Prozedur teilt dem Computer Operator mit, welche Aufgabe die Anwendung ausführt, und zeigt außerdem einen Zeitstempel an. Anstatt diesen Code zu Beginn jeder Aufgabe zu duplizieren, ruft die Anwendung nur `tellOperator` von verschiedenen Speicherorten auf. Jeder-Befehl übergibt eine Zeichenfolge in das `task`-Argument, das den zu startenden Task identifiziert.

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

Das folgende Beispiel zeigt einen typischen `tellOperator`-Aufruf.

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Sub-Anweisung](../../../language-reference/statements/sub-statement.md)
- [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Gewusst wie: Abrufen eines Ereignis Handlers in Visual Basic](./how-to-call-an-event-handler.md)
