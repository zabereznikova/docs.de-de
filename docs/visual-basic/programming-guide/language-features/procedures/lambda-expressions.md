---
title: Lambdaausdrücke (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: e688beac18e782367bf39ddec8339df2b2735225
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928905"
---
# <a name="lambda-expressions-visual-basic"></a>Lambdaausdrücke (Visual Basic)
Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die überall dort verwendet werden kann, wo ein Delegat gültig ist. Lambda Ausdrücke können Funktionen oder Unterroutinen sein und können einzeilige oder mehrzeilige Zeilen sein. Sie können Werte aus dem aktuellen Gültigkeitsbereich an einen Lambda-Ausdruck übergeben.  
  
> [!NOTE]
> Die `RemoveHandler` -Anweisung ist eine Ausnahme. Sie können einen Lambda-Ausdruck in nicht für den Delegatparameter von `RemoveHandler`übergeben.  
  
 Sie können Lambda Ausdrücke erstellen, indem `Function` Sie `Sub` das-Schlüsselwort oder das-Schlüsselwort verwenden, wie Sie eine Standardfunktion oder Unterroutine erstellen. Allerdings sind Lambda-Ausdrücke in einer-Anweisung enthalten.  
  
 Das folgende Beispiel zeigt einen Lambda-Ausdruck, der sein-Argument erhöht und den-Wert zurückgibt. Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 Das folgende Beispiel ist ein Lambda-Ausdruck, der einen Wert in die Konsole schreibt. Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine.  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 Beachten Sie, dass in den vorherigen Beispielen die Lambda-Ausdrücke einem Variablennamen zugewiesen werden. Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck auf. Sie können einen Lambda-Ausdruck auch gleichzeitig deklarieren und aufrufen, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 Ein Lambda-Ausdruck kann als Wert eines Funktions Aufrufes zurückgegeben werden (wie im Beispiel im [Kontext](#context) Abschnitt weiter unten in diesem Thema gezeigt) oder als Argument an einen Parameter übergeben, der einen Delegattyp annimmt, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standardfunktion oder-Unterroutine. Die Unterschiede lauten wie folgt:  
  
- Ein Lambda-Ausdruck weist keinen Namen auf.  
  
- Lambda Ausdrücke können keine Modifizierer aufweisen, `Overloads` wie `Overrides`z. b. oder.  
  
- Einzeilige Lambda-Funktionen verwenden `As` keine-Klausel, um den Rückgabetyp festzulegen. Stattdessen wird der-Typ von dem Wert abgeleitet, zu dem der Text des Lambda-Ausdrucks ausgewertet wird. Wenn der Text des Lambda-Ausdrucks beispielsweise ist `cust.City = "London"`, ist `Boolean`der Rückgabetyp.  
  
- In mehrzeiligen Lambda-Funktionen können Sie entweder mithilfe einer `As` -Klausel einen Rückgabetyp angeben oder die `As` -Klausel weglassen, damit der Rückgabetyp abgeleitet wird. Wenn die `As` -Klausel für eine mehrzeilige Lambda-Funktion weggelassen wird, wird der Rückgabetyp als dominanter Typ aus `Return` allen Anweisungen in der mehrzeiligen Lambda-Funktion abgeleitet. Der *vorherrschende Typ* ist ein eindeutiger Typ, auf den alle anderen Typen erweitert werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, auf den alle anderen Typen im Array eingrenzen können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. In diesem Fall tritt ein `Option Strict` Compilerfehler `On`auf, wenn auf festgelegt ist.  
  
     Wenn die Ausdrücke `Return` , die für die-Anweisung bereitgestellt werden, z. b. Werte vom Typ `Integer`, `Long`und `Double`enthalten, `Double`ist das resultierende Array vom Typ. `Integer` Und werden`Long` nur aufund`Double`erweitert. `Double` Daher ist `Double` der bestimmende Typ. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
- Der Text einer einzeiligen Funktion muss ein Ausdruck sein, der einen Wert zurückgibt, nicht eine-Anweisung. Es gibt keine `Return` -Anweisung für einzeilige Funktionen. Der von der einzeiligen Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Text der Funktion.  
  
- Der Text einer einzeiligen Unterroutine muss eine einzeilige Anweisung sein.  
  
- Einzeilige Funktionen und Unterroutinen enthalten `End Function` keine-oder `End Sub` -Anweisung.  
  
- Sie können den Datentyp eines Lambda-Ausdrucks Parameters angeben, indem Sie `As` das-Schlüsselwort verwenden, oder der Datentyp des Parameters kann abgeleitet werden. Entweder müssen alle Parameter über bestimmte Datentypen verfügen, oder alle müssen abgeleitet werden.  
  
- `Optional`- `Paramarray` und-Parameter sind nicht zulässig.  
  
- Generische Parameter sind nicht zulässig.  
  
## <a name="async-lambdas"></a>Asynchrone Lambdas  
 Sie können problemlos Lambda Ausdrücke und Anweisungen erstellen, die die asynchrone Verarbeitung mithilfe der Schlüsselwörter [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Erwartung des Operators](../../../../visual-basic/language-reference/operators/await-operator.md) einschließen. Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.  
  
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
  
 Sie können denselben Ereignishandler hinzufügen, indem Sie einen Async-Lambda in einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md)verwenden. Um diesen Handler hinzuzufügen, fügen Sie einen `Async` -Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.  
  
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
  
 Weitere Informationen zum Erstellen und Verwenden von Async-Methoden finden Sie unter [asynchrone Programmierung mit Async und warten](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
## <a name="context"></a>Kontext  
 Ein Lambda-Ausdruck nutzt seinen Kontext mit dem Bereich, in dem er definiert ist. Sie verfügt über die gleichen Zugriffsrechte wie jeder Code, der in den enthaltenden Bereich geschrieben wurde. Dies schließt den Zugriff auf Member-Variablen,-Funktionen und `Me`-subs,-Parameter und-Parameter sowie lokale Variablen im enthaltenden Bereich ein.  
  
 Der Zugriff auf lokale Variablen und Parameter im enthaltenden Bereich kann über die Gültigkeitsdauer dieses Bereichs hinausgehen. Solange ein Delegat, der sich auf einen Lambda-Ausdruck bezieht, nicht für Garbage Collection verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten. Im folgenden Beispiel ist Variable `target` `makeTheGame`local in, die Methode, in der der Lambda-Ausdruck `playTheGame` definiert ist. Beachten Sie, dass der zurückgegebene Lambda- `takeAGuess` Ausdruck `Main`, der in zugewiesen ist, weiterhin auf `target`die lokale Variable zugreifen kann.  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 Im folgenden Beispiel wird der große Bereich von Zugriffsrechten für den in einem Lambda-Ausdruck aufgeführten Ausdruck veranschaulicht. Wenn der zurückgegebene Lambda-Ausdruck von `Main` als `aDel`ausgeführt wird, greift er auf diese Elemente zu:  
  
- Ein Feld der Klasse, in der es definiert ist:`aField`  
  
- Eine Eigenschaft der Klasse, in der Sie definiert ist:`aProp`  
  
- Ein Parameter der- `functionWithNestedLambda`Methode, in der er definiert ist:`level1`  
  
- Eine lokale Variable von `functionWithNestedLambda`:`localVar`  
  
- Ein Parameter des Lambda-Ausdrucks, in dem er sich befindet:`level2`  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a>Umstellen in einen Delegattyp  
 Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden. Informationen zu den allgemeinen Kompatibilitätsanforderungen finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit in `Func(Of Integer, Boolean)` oder eine entsprechende Delegatsignatur konvertiert.  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit `Sub(Of Double, String, Double)` in oder eine entsprechende Delegatsignatur konvertiert.  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 Wenn Sie Delegaten Lambda-Ausdrücke zuweisen oder Sie als Argumente an Prozeduren übergeben, können Sie die Parameternamen angeben, deren Datentypen jedoch weglassen und die Typen aus dem Delegaten entnommen werden.  
  
## <a name="examples"></a>Beispiele  
  
- Im folgenden Beispiel wird ein Lambda-Ausdruck definiert `True` , der zurückgibt, wenn das Werte zulässt-Argument `False` über einen zugewiesenen Wert `Nothing`verfügt und wenn sein Wert ist.  
  
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
- [Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Vorgehensweise: Erstellen eines Lambda Ausdrucks](./how-to-create-a-lambda-expression.md)
- [Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
