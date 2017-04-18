---
title: "Lambda-Ausdrücke (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e50593e76afecfe8807c3cb5bac479245d2feaef
ms.lasthandoff: 03/13/2017

---
# <a name="lambda-expressions-visual-basic"></a>Lambdaausdrücke (Visual Basic)
Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die verwendet werden kann, wo ein Delegat zulässig ist. Lambda-Ausdrücke können können Funktionen oder Unterroutinen sein und ein- oder mehrzeiligen. Sie können Werte aus dem aktuellen Gültigkeitsbereich an einen Lambda-Ausdruck übergeben.  
  
> [!NOTE]
>  Die `RemoveHandler` -Anweisung ist eine Ausnahme. Sie können keine Delegaten als Parameter für einen Lambda-Ausdruck in übergeben `RemoveHandler`.  
  
 Erstellen Sie Lambda-Ausdrücke mithilfe der `Function` oder `Sub` -Schlüsselwort, wie Sie eine standard-Funktion oder Unterroutine erstellen. Lambda-Ausdrücke sind jedoch in einer Anweisung enthalten.  
  
 Im folgende Beispiel wird ein Lambda-Ausdruck ein, der Argument inkrementiert und gibt den Wert zurück. Das Beispiel zeigt sowohl die einzeilige und mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.  
  
 [!code-vb[VbVbalrLambdas&14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 Im folgende Beispiel wird ein Lambda-Ausdruck, der einen Wert in die Konsole schreibt. Das Beispiel zeigt sowohl die einzeilige und mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine.  
  
 [!code-vb[VbVbalrLambdas&#15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Beachten Sie, dass in den vorherigen Beispielen die Lambda-Ausdrücke ein Variablenname zugewiesen werden. Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck. Sie können auch deklarieren und Aufrufen ein Lambda-Ausdrucks auf einmal, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrLambdas&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Ein Lambda-Ausdruck als Wert eines Funktionsaufrufs zurückgegeben werden kann (wie in dem Beispiel in der [Kontext](#context) weiter unten in diesem Thema), oder als Argument an einen Parameter übergeben, der einen Delegattyp akzeptiert wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrLambdas&#8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt der einer standard-Funktion oder Unterroutine. Die Unterschiede sind wie folgt:  
  
-   Ein Lambda-Ausdruck keinen Namen.  
  
-   Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.  
  
-   Verwenden Sie einzeiligen Lambda-Funktionen kein `As` -Klausel, um den Rückgabetyp festzulegen. Stattdessen wird der Typ von dem Wert abgeleitet, der der Text des Lambda-Ausdrucks ergibt. Wenn der Text des Lambda-Ausdrucks ist z. B. `cust.City = "London"`, dessen Rückgabetyp `Boolean`.  
  
-   In mehrzeiligen Lambda-Funktionen können Sie entweder einen Rückgabetyp angeben, mit einer `As` -Klausel, oder lassen Sie die `As` Klausel so, dass der Rückgabetyp abgeleitet wird. Wenn die `As` -Klausel weggelassen wird, für den eine mehrzeilige Lambda-Funktion, der Rückgabetyp ist der bestimmende Typ von allen abgeleitet ist die `Return` Anweisungen in mehrzeiligen Lambda-Funktion. Die *bestimmende Typ* ist ein eindeutiger Typ, der alle anderen Typen erweitert werden können. Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, dem alle anderen Typen im Array eingegrenzt werden können. Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`. In diesem Fall, wenn `Option Strict` Wert `On`, tritt ein Compilerfehler auf.  
  
     Z. B. wenn die Ausdrücke an die `Return` -Anweisung enthalten die Werte des Typs `Integer`, `Long`, und `Double`, das resultierende Array ist vom Typ `Double`. Beide `Integer` und `Long` werden zu `Double` und nur `Double`. Daher ist `Double` der bestimmende Typ. Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Der Text einer einzeiligen Funktion muss ein Ausdruck sein, der einen Wert, der keine Anweisung zurückgibt. Es gibt keine `Return` -Anweisung für einzeilige Funktionen. Der von der einzeiligen Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Text der Funktion.  
  
-   Der Text einer einzeiligen Unterroutine muss eine einzeilige Anweisung sein.  
  
-   Einzeilige Funktionen und Unterroutinen enthalten kein `End Function` oder `End Sub` Anweisung.  
  
-   Sie können den Datentyp eines Lambda-Ausdruck-Parameters angeben, mit dem `As` Schlüsselwort oder der Datentyp des Parameters abgeleitet werden kann. Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.  
  
-   `Optional`und `Paramarray` Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## <a name="async-lambdas"></a>Asynchrone Lambdas  
 Sie können problemlos erstellen, Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten die [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md) Schlüsselwörter. Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.  
  
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
  
 Sie können denselben Ereignishandler hinzufügen, indem Sie ein asynchrones Lambda in verwenden ein [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Um diesen Handler hinzuzufügen, fügen Sie einen `Async`-Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.  
  
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
  
 Weitere Informationen zum Erstellen und Verwenden von Async-Methoden finden Sie unter [asynchrone Programmierung mit Async und Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
##  <a name="context"></a>Kontext  
 Ein Lambda-Ausdruck teilt der Kontext mit dem Bereich, in dem sie definiert ist. Er verfügt über die gleichen Zugriffsrechte wie der Code im enthaltenden Bereich geschrieben. Dies schließt Zugriff auf Membervariablen, Funktionen und Subroutinen, `Me`, Parameter und lokale Variablen im enthaltenden Bereich.  
  
 Zugriff auf lokale Variablen und Parameter im enthaltenden Bereich kann die Lebensdauer dieses Bereichs überdauern. Solange ein Delegat, der auf einen Lambda-Ausdruck verweist nicht auf die Garbagecollection verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten. Im folgenden Beispiel Variablen `target` lediglich auf `makeTheGame`, die Methode, in der der Lambda-Ausdruck `playTheGame` definiert ist. Beachten Sie, die den zurückgegebenen Lambda-Ausdruck zugewiesen, `takeAGuess` in `Main`, immer noch Zugriff auf die lokale Variable `target`.  
  
 [!code-vb[VbVbalrLambdas&#12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 Das folgende Beispiel zeigt eine Vielzahl von Zugriffsrechte des geschachtelten Lambda-Ausdrucks. Wenn der zurückgegebene Lambda-Ausdruck ausgeführt wird, von `Main` als `aDel`, greift er auf diese Elemente:  
  
-   Ein Feld der Klasse, in der er definiert wird:`aField`  
  
-   Eine Eigenschaft der Klasse, in der er definiert wird:`aProp`  
  
-   Ein Parameter der Methode `functionWithNestedLambda`, in der er definiert wird:`level1`  
  
-   Eine lokale Variable des `functionWithNestedLambda`:`localVar`  
  
-   Ein Parameter des Lambda-Ausdrucks in der er geschachtelt wird:`level2`  
  
 [!code-vb[VbVbalrLambdas&#9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a>Konvertieren in einen Delegattyp  
 Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden. Informationen über die allgemeinen Kriterien zur Kompatibilität finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Das folgende Codebeispiel zeigt z. B. einen Lambda-Ausdruck, der implizit in konvertiert `Func(Of Integer, Boolean)` oder eine entsprechende Delegatsignatur.  
  
 [!code-vb[VbVbalrLambdas Nr.&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit in konvertiert `Sub(Of Double, String, Double)` oder eine entsprechende Delegatsignatur.  
  
 [!code-vb[VbVbalrLambdas&23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 Wenn Sie Lambda-Ausdrücke Delegaten zugewiesen oder als Argumente an Prozeduren übergeben, können Sie die Parameternamen jedoch weglassen, deren Datentypen, die Typen aus dem Delegaten ausgeführt werden können.  
  
## <a name="examples"></a>Beispiele  
  
-   Im folgenden Beispiel wird einen Lambda-Ausdruck, der zurückgibt `True` verfügt das auf NULL festlegbare Argument einen Wert zugewiesen und `False` ist der Wert `Nothing`.  
  
     [!code-vb[VbVbalrLambdas&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   Das folgende Beispiel definiert einen Lambda-Ausdruck, der den Index des letzten Elements in einem Array zurückgibt.  
  
     [!code-vb[VbVbalrLambdas&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Gewusst wie: Erstellen eines Lambda-Ausdrucks](./how-to-create-a-lambda-expression.md)   
 [Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
