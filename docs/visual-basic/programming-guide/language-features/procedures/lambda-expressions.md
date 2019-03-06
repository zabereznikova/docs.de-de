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
ms.openlocfilehash: 02377b0765144064df8d51fa63768412ca4b606a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363477"
---
# <a name="lambda-expressions-visual-basic"></a>Lambdaausdrücke (Visual Basic)
Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die verwendet werden kann, wo Delegaten gültig ist. Lambda-Ausdrücke können Funktionen oder Unterroutinen und können ein- oder mehrzeiligen. Sie können Werte aus dem aktuellen Bereich an einen Lambda-Ausdruck übergeben.  
  
> [!NOTE]
>  Die `RemoveHandler` -Anweisung ist eine Ausnahme. Sie können keine Delegaten als Parameter für einen Lambda-Ausdruck in übergeben `RemoveHandler`.  
  
 Erstellen Sie Lambda-Ausdrücke mithilfe der `Function` oder `Sub` -Schlüsselwort, wie Sie eine standard-Funktion oder Unterroutine erstellen. Lambda-Ausdrücke sind jedoch in einer Anweisung enthalten.  
  
 Im folgende Beispiel wird ein Lambda-Ausdruck, der inkrementiert des Arguments und gibt den Wert zurück. Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion.  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 Im folgende Beispiel wird ein Lambda-Ausdruck, der einen Wert an die Konsole schreibt. Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Unterroutine.  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 Beachten Sie, dass die Lambda-Ausdrücke in den vorherigen Beispielen ein Variablenname zugewiesen werden. Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck. Sie können auch deklarieren und Aufrufen ein Lambda-Ausdrucks zur gleichen Zeit, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 Ein Lambda-Ausdruck als Wert eines Funktionsaufrufs zurückgegeben werden kann (wie im Beispiel gezeigt die [Kontext](#context) weiter unten in diesem Thema), oder als Argument an einen Parameter übergeben, die akzeptiert einen Delegattyp, wie im folgenden dargestellt Beispiel:.  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion oder Unterroutine. Die Unterschiede sind wie folgt aus:  
  
-   Ein Lambda-Ausdruck ist nicht auf einen Namen haben.  
  
-   Lambda-Ausdrücke sind keine Modifizierer, z. B. `Overloads` oder `Overrides`.  
  
-   Einzeilige Lambda-Funktionen verwenden Sie keine `As` -Klausel, um den Rückgabetyp zu bestimmen. Stattdessen wird der Typ des Werts abgeleitet, der der Text des Lambda-Ausdrucks ergibt. Wenn der Text des Lambda-Ausdrucks ist z. B. `cust.City = "London"`, dessen Rückgabetyp `Boolean`.  
  
-   In mehrzeiligen Lambdafunktionen können Sie entweder einen Rückgabetyp angeben, mit einem `As` -Klausel, oder lassen Sie die `As` Klausel so, dass der Rückgabetyp abgeleitet wird. Wenn die `As` -Klausel weggelassen, bei einer mehrzeiligen Lambda-Funktion, die der Rückgabetyp abgeleitet wird, werden von der bestimmende Typ von allen die `Return` Anweisungen in der mehrzeiligen Lambda-Funktion. Die *bestimmende Typ* ist ein eindeutiger Typ, der alle anderen Typen erweitert werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, dem alle anderen Typen im Array eingegrenzt werden können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. In diesem Fall wenn `Option Strict` nastaven NA hodnotu `On`, tritt ein Compilerfehler auf.  
  
     Wenn die Ausdrücke für bereitgestellt, z. B. die `Return` -Anweisung enthalten die Werte des Typs `Integer`, `Long`, und `Double`, das resultierende Array ist vom Typ `Double`. Beide `Integer` und `Long` zu erweitert `Double` und nur `Double`. Daher ist `Double` der bestimmende Typ. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Der Text einer einzeiligen-Funktion muss ein Ausdruck sein, der keine Anweisung einen Wert zurückgibt. Es gibt keine `Return` -Anweisung für einzeilige Funktionen. Der von der einzeilige-Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Textkörper der Funktion.  
  
-   Der Text der Unterroutine einzeilige muss es sich um einzeilige-Anweisung sein.  
  
-   Einzeilige Funktionen und Unterroutinen enthalten kein `End Function` oder `End Sub` Anweisung.  
  
-   Sie können den Datentyp eines Parameters des Lambda-Ausdruck angeben, mit der `As` Schlüsselwort oder den Datentyp des Parameters abgeleitet werden kann. Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen per Rückschluss abgeleitet werden müssen.  
  
-   `Optional` und `Paramarray` Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## <a name="async-lambdas"></a>Asynchrone Lambdas  
 Sie können ganz einfach erstellen, Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, mit der [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md) Schlüsselwörter. Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.  
  
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
  
 Sie können denselben Ereignishandler hinzufügen, indem Sie mit einem asynchronem Lambda-Ausdruck in einem [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Um diesen Handler hinzuzufügen, fügen Sie einen `Async` -Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.  
  
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
  
 Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [asynchrone Programmierung mit Async und Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
## <a name="context"></a> Kontext  
 Ein Lambda-Ausdruck teilt der Kontext durch den Bereich, in dem sie definiert ist. Es verfügt über die gleichen Zugriffsrechte wie der Code in der enthaltenden Bereich geschrieben. Dies schließt den Zugriff auf Member-Variablen, Funktionen und Subroutinen, `Me`, Parameter und lokalen Variablen in den Gültigkeitsbereich.  
  
 Zugriff auf lokale Variablen und Parameter in der enthaltenden Bereich kann über die Lebensdauer, Bereich hinaus erweitern. Solange ein Delegat, der auf einen Lambda-Ausdruck nicht bei der Garbagecollection verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten. Im folgenden Beispiel Variablen `target` lediglich auf `makeTheGame`, Methode, in der Lambda-Ausdrucks `playTheGame` definiert ist. Beachten Sie, die der zurückgegebenen Lambdaausdruck, zugewiesen, `takeAGuess` in `Main`, immer noch Zugriff auf die lokale Variable `target`.  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 Das folgende Beispiel zeigt die Bandbreite der Zugriffsrechte des geschachtelten Lambda-Ausdrucks. Wenn der zurückgegebenen Lambda-Ausdruck ausgeführt wird `Main` als `aDel`, greift er auf diese Elemente:  
  
-   Ein Feld der Klasse, die in der sie definiert ist: `aField`  
  
-   Eine Eigenschaft der Klasse, die in der sie definiert ist: `aProp`  
  
-   Ein Parameter der Methode `functionWithNestedLambda`, in dem sie definiert ist: `level1`  
  
-   Eine lokale Variable vom `functionWithNestedLambda`: `localVar`  
  
-   Ein Parameter des Lambdaausdrucks darstellen, in dem sie geschachtelt ist: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a>Konvertieren in einen Delegattyp aufweisen  
 Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden. Weitere Informationen zu den allgemeinen Anforderungen für die Kompatibilität, finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Das folgende Codebeispiel zeigt z. B. einen Lambda-Ausdruck, der implizit in konvertiert `Func(Of Integer, Boolean)` oder einer übereinstimmenden Delegatsignatur.  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit in konvertiert `Sub(Of Double, String, Double)` oder einer übereinstimmenden Delegatsignatur.  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 Wenn Sie Lambda-Ausdrücke an Delegaten zuweisen oder diese als Argumente, Prozeduren übergeben, können Sie die Parameternamen angeben jedoch auslassen von deren Datentypen, sodass die Typen des Delegaten ausgeführt werden.  
  
## <a name="examples"></a>Beispiele  
  
-   Das folgende Beispiel definiert einen Lambda-Ausdruck, der zurückgibt `True` , wenn das Argument NULL-Werte zulässt, einen Wert zugewiesen wurde und `False` Wenn der Wert `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
-   Das folgende Beispiel definiert einen Lambda-Ausdruck, der den Index des letzten Elements in einem Array zurückgibt.  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Vorgehensweise: Erstellen Sie einen Lambda-Ausdruck](./how-to-create-a-lambda-expression.md)
- [Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
