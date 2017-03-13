---
title: "Lambda Expressions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.LambdaFunction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "functions [Visual Basic], lambda expressions"
  - "lambda expressions [Visual Basic]"
  - "expressions [Visual Basic], lambda"
  - "inline functions [Visual Basic]"
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 52
---
# Lambda Expressions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Ein *Lambda\-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die Sie an Stellen verwenden können, an denen die Verwendung eines Delegattypen gültig ist.  Lambda\-Ausdrücke können Funktionen oder Unterroutinen und einzeilig oder mehrzeilig sein.  Sie können Werte aus dem aktuellen Gültigkeitsbereich an einen Lambda\-Ausdruck übergeben.  
  
> [!NOTE]
>  Die `RemoveHandler`\-Anweisung ist eine Ausnahme.  Ein Lambda\-Ausdruck kann nicht als Delegatparameter an `RemoveHandler` übergeben werden.  
  
 Lambda\-Ausdrücke werden ebenso wie Standardfunktionen oder \-unterroutinen mit dem `Function`\-Schlüsselwort oder dem `Sub`\-Schlüsselwort erstellt.  Lambda\-Ausdrücke sind jedoch in eine Anweisung eingeschlossen.  
  
 Im folgenden Beispiel wird ein Lambda\-Ausdruck dargestellt, der das Argument inkrementiert und den Wert zurückgibt.  Im Beispiel wird die Syntax für einzeilige und mehrzeilige Lambda\-Ausdrücke für eine Funktion veranschaulicht.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 Das folgende Beispiel enthält einen Lambda\-Ausdruck, der einen Wert in die Konsole schreibt.  Dabei wird die Syntax für einzeilige und mehrzeilige Lambda\-Ausdrücke für eine Unterroutine veranschaulicht.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Beachten Sie, dass in den vorherigen Beispielen die Lambda\-Ausdrücke einem Variablennamen zugewiesen wurden.  Bei jedem Verweis auf die Variable wird der Lambda\-Ausdruck aufgerufen.  Sie können einen Lambda\-Ausdruck auch deklarieren und gleichzeitig aufrufen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Ein Lambda\-Ausdruck kann als Wert eines Funktionsaufrufs zurückgegeben \(dies wird weiter unten in diesem Thema im [Kontext](#context) als Beispiel dargestellt\) oder wie im folgenden Beispiel gezeigt als Argument an einen Parameter übergeben werden, der einen Delegattyp akzeptiert.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## Lambda\-Ausdruckssyntax  
 Die Syntax eines Lambda\-Ausdrucks ähnelt der einer Standardfunktion oder \-unterroutine.  Die Unterschiede sind:  
  
-   Ein Lambda\-Ausdruck verfügt über keinen Namen.  
  
-   Lambda\-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.  
  
-   In einzeiligen Lambda\-Funktionen wird der Rückgabetyp nicht mit einer `As`\-Klausel festgelegt.  Stattdessen wird der Typ von dem Wert abgeleitet, der sich aus der Auswertung des Lambda\-Ausdruckstext ergibt.  Wenn der Text des Lambda\-Ausdrucks z. B. `cust.City = "London"` lautet, ist dessen Rückgabetyp `Boolean`  
  
-   In mehrzeiligen Lambda\-Funktionen können Sie einen Rückgabetyp entweder mit einer `As`\-Klausel angeben, oder Sie können die `As`\-Klausel auslassen, sodass der Rückgabetyp abgeleitet wird.  Wenn die `As`\-Klausel für eine mehrzeilige Lambda\-Funktion ausgelassen wird, wird der Rückgabetyp als bestimmender Typ aus allen `Return`\-Anweisungen in der mehrzeiligen Lambda\-Funktion abgeleitet.  Die  *dominante* ist ein eindeutiger Typ, der zu anderen Typen erweitert werden können.  Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, auf den alle anderen Typen im Array eingegrenzt werden können.  Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`.  In diesem Fall tritt ein Compilerfehler auf, wenn `Option Strict` auf `On` festgelegt ist.  
  
     Beispielsweise, wenn die Ausdrücke geliefert der `Return` \-Anweisung enthalten Werte vom Typ `Integer`, `Long`, und `Double`, das resultierende Array ist vom Typ `Double`.  Sowohl `Integer` als auch `Long` können zu `Double` und nur zu `Double` erweitert werden.  Daher ist `Double` der bestimmende Typ.  Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Der Inhalt einer einzeiligen Funktion muss ein Ausdruck sein, von dem ein einzelner Wert und keine Anweisung zurückgegeben werden.  Es ist keine `Return`\-Anweisung für einzeilige Funktionen vorhanden.  Der von der einzeiligen Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Text der Funktion.  
  
-   Der Text einer einzeiligen Unterroutine muss eine einzeilige Anweisung sein.  
  
-   Einzeilige Funktionen und Unterroutinen enthalten keine `End Function`\-Anweisung oder `End Sub`\-Anweisung.  
  
-   Sie können den Datentyp eines Lambda\-Ausdruck\-Parameters mit dem `As`\-Schlüsselwort angeben. Der Datentyp des Parameters kann jedoch auch abgeleitet werden.  Entweder müssen alle Parameter über angegebene Datentypen verfügen, oder alle Datentypen müssen abgeleitet sein.  
  
-   Der `Optional`\-Parameter und der `Paramarray`\-Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## Async\-Lambda\-Ausdrücke  
 Können Sie mühelos Lambda\-Ausdrücke und Anweisungen, die asynchronen Verarbeitung mithilfe übernehmen die [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) Schlüsselwörter.  Im folgende Beispiel für Windows Forms enthält beispielsweise einen Ereignishandler, der aufruft und wartet auf eine Async\-Methode `ExampleMethodAsync`.  
  
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
  
 Sie können denselben Ereignishandler hinzufügen, mithilfe einer asynchronen Lambda in ein [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  Fügen Sie diesen Handler hinzuzufügen ein `Async` Modifizierer vor der Parameterliste des Lambda, wie im folgenden Beispiel gezeigt.  
  
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
  
 Weitere Informationen zum Erstellen und verwenden die Async\-Methoden finden Sie unter [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
##  <a name="context"></a> Kontext  
 Der Kontext eines Lambda\-Ausdrucks wird gemeinsam mit dem Bereich genutzt, in der der Ausdruck definiert ist.  Er verfügt über die gleichen Zugriffsrechte wie der Code, der im enthaltenden Bereich geschrieben wurde.  Dies schließt Zugriff auf Membervariablen, Funktionen und Subs, `Me` sowie auf Parameter und lokale Variablen im enthaltenden Bereich ein.  
  
 Der Zugriff auf lokale Variablen und Parameter im enthaltenden Bereich kann die Lebensdauer dieses Bereichs überdauern.  So lange wie ein auf einen Lambda\-Ausdruck verweisender Delegat nicht für die Garbage Collection freigegeben wird, bleibt der Zugriff auf die Variablen in der ursprünglichen Umgebung erhalten.  In dem folgenden Beispiel befindet sich die `target`\-Variable lokal zu `makeTheGame`, der Methode, in der der Lambda\-Ausdruck `playTheGame` definiert ist.  Beachten Sie, dass der zurückgegebene Lambda\-Ausdruck, der `takeAGuess` in `Main` zugewiesen wird, weiterhin über Zugriff auf die lokale `target`\-Variable verfügt.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 Im folgenden Beispiel wird der große Bereich der Zugriffsrechte des geschachtelten Lambda\-Ausdrucks veranschaulicht.  Wenn der zurückgegebene Lambda\-Ausdruck von `Main` als `aDel` ausgeführt wird, greift er auf diese Elemente zu:  
  
-   Ein Feld der Klasse, in der er definiert wird: `aField`  
  
-   Eine Eigenschaft der Klasse, in der er definiert wird: `aProp`  
  
-   Ein Parameter der `functionWithNestedLambda`\-Methode, in der er definiert wird: `level1`  
  
-   Ein lokale Variable von `functionWithNestedLambda`: `localVar`  
  
-   Ein Parameter des Lambda\-Ausdrucks, in der er geschachtelt wird: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## Konvertieren in einen Delegattyp  
 Ein Lambda\-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden.  Weitere Informationen über die allgemeinen Anforderungen an Kompatibilität finden Sie unter [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  Im folgenden Codebeispiel wird ein Lambda\-Ausdruck veranschaulicht, der implizit in `Func(Of Integer, Boolean)` oder eine entsprechende Delegatsignatur konvertiert wird.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 Im folgenden Codebeispiel wird ein lambda\-Ausdruck veranschaulicht, der implizit in `Sub(Of Double, String, Double)` oder eine entsprechende Delegatsignatur konvertiert wird.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 Wenn Lambda\-Ausdrücke Delegaten zugewiesen oder als Argumente an Prozeduren übergeben werden, können die Parameternamen angegeben werden. Die Datentypen müssen jedoch nicht angegeben werden, da sie von den Delegaten übernommen werden können.  
  
## Beispiele  
  
-   Im folgenden Beispiel wird ein Lambda\-Ausdruck definiert, der `True` zurückgibt, wenn das Argument, das NULL\-Werte zulässt, über einen zugewiesenen Wert verfügt. Der Ausdruck gibt `False` zurück, wenn der Wert `Nothing` lautet.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   In folgenden Beispiel wird ein Lambda\-Ausdruck definiert, der den Index des letzten Elements in einem Array zurückgibt.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [How to: Create a Lambda Expression](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-lambda-expression.md)   
 [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)