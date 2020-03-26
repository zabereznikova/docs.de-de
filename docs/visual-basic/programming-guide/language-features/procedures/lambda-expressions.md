---
title: Lambda-Ausdrücke
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249668"
---
# <a name="lambda-expressions-visual-basic"></a>Lambdaausdrücke (Visual Basic)

Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Einen Namen, der überall dort verwendet werden kann, wo ein Delegat gültig ist. Lambda-Ausdrücke können Funktionen oder Unterroutinen sein und ein- oder mehrzeilig sein. Sie können Werte aus dem aktuellen Bereich an einen Lambda-Ausdruck übergeben.

> [!NOTE]
> Die `RemoveHandler` Anweisung ist eine Ausnahme. Sie können keinen Lambda-Ausdruck für `RemoveHandler`den Delegatenparameter von übergeben.

Sie erstellen Lambda-Ausdrücke mithilfe des `Function` Schlüsselworts or, `Sub` genau wie Sie eine Standardfunktion oder Unterroutine erstellen. Lambda-Ausdrücke sind jedoch in einer Anweisung enthalten.

Das folgende Beispiel ist ein Lambda-Ausdruck, der sein Argument erhöht und den Wert zurückgibt. Das Beispiel zeigt sowohl die einzeilige als auch die mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

Das folgende Beispiel ist ein Lambda-Ausdruck, der einen Wert in die Konsole schreibt. Das Beispiel zeigt sowohl die einzeilige als auch die mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

Beachten Sie, dass in den vorherigen Beispielen die Lambda-Ausdrücke einem Variablennamen zugewiesen sind. Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck auf. Sie können auch einen Lambda-Ausdruck gleichzeitig deklarieren und aufrufen, wie im folgenden Beispiel gezeigt.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

Ein Lambda-Ausdruck kann als Wert eines Funktionsaufrufs zurückgegeben werden (wie im Beispiel im [Kontextabschnitt](#context) weiter unten in diesem Thema gezeigt wird) oder als Argument an einen Parameter übergeben werden, der einen Delegatentyp annimmt, wie im folgenden Beispiel gezeigt.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax

Die Syntax eines Lambdaausdrucks ähnelt der einer Standardfunktion oder Unterroutine. Es gibt die folgenden Unterschiede:

- Ein Lambda-Ausdruck hat keinen Namen.

- Lambda-Ausdrücke können keine Modifikatoren haben, z. `Overloads` B. oder `Overrides`.

- Einzeilige Lambda-Funktionen verwenden `As` keine Klausel, um den Rückgabetyp zu bestimmen. Stattdessen wird der Typ aus dem Wert abgeleitet, den der Text des Lambda-Ausdrucks auswertet. Wenn der Text des Lambdaausdrucks `cust.City = "London"`z. B. der Rückgabetyp lautet: `Boolean`

- In mehrzeiligen Lambda-Funktionen können Sie entweder einen `As` Rückgabetyp mithilfe `As` einer Klausel angeben oder die Klausel weglassen, sodass der Rückgabetyp abgeleitet wird. Wenn `As` die Klausel für eine mehrzeilige Lambdafunktion weggelassen wird, wird der Rückgabetyp als dominanter Typ aus allen `Return` Anweisungen in der mehrzeiligen Lambdafunktion abgeleitet. Der *dominante Typ* ist ein eindeutiger Typ, auf den alle anderen Typen erweitert werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der dominante Typ der eindeutige Typ, auf den alle anderen Typen im Array eingegrenzt werden können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. In diesem Fall `Option Strict` tritt `On`ein Compilerfehler auf , wenn auf festgelegt ist.

     Wenn z. B. die `Return` für die `Integer`Anweisung `Long`bereitgestellten Ausdrücke Werte vom Typ , und `Double`enthalten, ist das resultierende Array vom Typ `Double`. Sowohl `Integer` `Long` und `Double` erweitern `Double`auf und nur . Daher ist `Double` der bestimmende Typ. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

- Der Text einer einzeiligen Funktion muss ein Ausdruck sein, der einen Wert und keine Anweisung zurückgibt. Es gibt `Return` keine Anweisung für einzeilige Funktionen. Der von der einzeiligen Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Textkörper der Funktion.

- Der Text einer einzeiligen Unterroutine muss eine einzeilige Anweisung sein.

- Einzeilige Funktionen und Unterroutinen `End Function` enthalten `End Sub` keine Oder-Anweisung.

- Sie können den Datentyp eines Lambda-Ausdrucksparameters mithilfe des `As` Schlüsselworts angeben, oder der Datentyp des Parameters kann abgeleitet werden. Entweder müssen alle Parameter über angegebene Datentypen verfügen, oder alle müssen abgeleitet werden.

- `Optional`und `Paramarray` Parameter sind nicht zulässig.

- Generische Parameter sind nicht zulässig.

## <a name="async-lambdas"></a>Asynchrone Lambdas

Sie können einfach Lambda-Ausdrücke und -Anweisungen erstellen, die asynchrone Verarbeitung mithilfe der Schlüsselwörter [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) enthalten. Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.

```vb
Public Class Form1

    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        ' ExampleMethodAsync returns a Task.
        Await ExampleMethodAsync()
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

Sie können denselben Ereignishandler hinzufügen, indem Sie einen async-Lambda in einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md)verwenden. Um diesen Handler hinzuzufügen, fügen Sie einen `Async` -Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.

```vb
Public Class Form1

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        AddHandler Button1.Click,
            Async Sub(sender1, e1)
                ' ExampleMethodAsync returns a Task.
                Await ExampleMethodAsync()
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."
            End Sub
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchrone Programmierung mit Async und Await](../../../../visual-basic/programming-guide/concepts/async/index.md).

## <a name="context"></a>Kontext

Ein Lambda-Ausdruck teilt seinen Kontext mit dem Bereich, in dem er definiert ist. Es verfügt über dieselben Zugriffsrechte wie jeder Code, der im enthaltenden Bereich geschrieben wurde. Dazu gehört der Zugriff auf Membervariablen, Funktionen und Subs sowie `Me`Parameter und lokale Variablen im enthaltenden Bereich.

Der Zugriff auf lokale Variablen und Parameter im enthaltenden Bereich kann über die Lebensdauer dieses Bereichs hinausgehen. Solange ein Delegat, der auf einen Lambda-Ausdruck verweist, für die Garbage Collection nicht verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten. Im folgenden Beispiel `target` ist die `makeTheGame`Variable lokal zu , `playTheGame` der Methode, in der der Lambdaausdruck definiert ist. Beachten Sie, dass der zurückgegebene `Main`Lambda-Ausdruck, der `target` `takeAGuess` in zugewiesen ist, weiterhin Zugriff auf die lokale Variable hat.

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

Im folgenden Beispiel wird der große Bereich der Zugriffsrechte des verschachtelten Lambdaausdrucks veranschaulicht. Wenn der zurückgegebene Lambda-Ausdruck von `Main` as `aDel`ausgeführt wird, greift er auf die folgenden Elemente zu:

- Ein Feld der Klasse, in der es definiert ist:`aField`

- Eine Eigenschaft der Klasse, in der sie definiert ist:`aProp`

- Ein Parameter `functionWithNestedLambda`der Methode , in dem sie definiert ist:`level1`

- Eine lokale `functionWithNestedLambda`Variable von:`localVar`

- Ein Parameter des Lambda-Ausdrucks, in dem er geschachtelt ist:`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>Konvertieren in einen Delegatentyp

Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden. Informationen zu den allgemeinen Kompatibilitätsanforderungen finden Sie unter [Entspannte Delegatkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Das folgende Codebeispiel zeigt beispielsweise einen Lambda-Ausdruck, `Func(Of Integer, Boolean)` der implizit in eine übereinstimmende Delegatsignatur konvertiert wird.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit in `Sub(Of Double, String, Double)` eine oder eine übereinstimmende Delegatsignatur konvertiert wird.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

Wenn Sie Delegaten Lambda-Ausdrücke zuweisen oder sie als Argumente an Prozeduren übergeben, können Sie die Parameternamen angeben, aber deren Datentypen weglassen, sodass die Typen aus dem Delegaten übernommen werden.

## <a name="examples"></a>Beispiele

- Im folgenden Beispiel wird ein Lambda-Ausdruck `True` `False` `Nothing`definiert, der zurückgibt, wenn das Argument nullable value type einen zugewiesenen Wert hat und wenn sein Wert ist.

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- Im folgenden Beispiel wird ein Lambda-Ausdruck definiert, der den Index des letzten Elements in einem Array zurückgibt.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Vorgehensweise: Erstellen eines Lambdaausdrucks](./how-to-create-a-lambda-expression.md)
- [Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
