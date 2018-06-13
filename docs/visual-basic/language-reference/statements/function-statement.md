---
title: Function-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 908aa594ecbdd8ae2ec5a06de8181a1b16bb7e40
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234123"
---
# <a name="function-statement-visual-basic"></a>Function-Anweisung (Visual Basic)
Deklariert den Namen, Parameter und Code, definieren eine `Function` Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Teile  
  
-   `attributelist`  
  
     Dies ist optional. Finden Sie unter [Attributliste](attribute-list.md).  
  
-   `accessmodifier`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)

    - [Geschützt privat](../../language-reference/modifiers/private-protected.md)  
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Dies ist optional. Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Dies ist optional. Finden Sie unter [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `Iterator`  
  
     Dies ist optional. Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Prozedur. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `typeparamlist`  
  
     Dies ist optional. Liste mit Typparametern für eine generische Prozedur. Finden Sie unter [geben Liste](type-list.md).  
  
-   `parameterlist`  
  
     Dies ist optional. Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt. Finden Sie unter [Parameterliste](parameter-list.md).  
  
-   `returntype`  
  
     Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp des Werts, der von dieser Prozedur zurückgegeben.  
  
-   `Implements`  
  
     Dies ist optional. Gibt an, dass dieses Verfahren eine oder mehrere implementiert `Function` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert. Finden Sie unter [Anweisung implementiert](implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Function`-Prozeduren.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`interface`|Erforderlich. Name einer Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist.|  
  
-   `Handles`  
  
     Dies ist optional. Gibt an, dass dieses Verfahren eine oder mehrere bestimmte Ereignisse verarbeiten kann. Finden Sie unter [behandelt](handles-clause.md).  
  
-   `eventlist`  
  
     Erforderlich, wenn `Handles` angegeben wird. Die Liste der Ereignisse, die diese Prozedur behandelt.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:  
  
     `eventvariable.event`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`eventvariable`|Erforderlich. Mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst deklarierte Objektvariable.|  
    |`event`|Erforderlich. Der Name des Ereignisses, das dieses Verfahren behandelt.|  
  
-   `statements`  
  
     Dies ist optional. Der Block von Anweisungen in diesem Verfahren ausgeführt werden.  
  
-   `End Function`  
  
     Beendet die Definition dieses Verfahrens fort.  
  
## <a name="remarks"></a>Hinweise  
 Alle ausführbaren Code muss innerhalb einer Prozedur sein. Jede Prozedur deklariert wiederum innerhalb einer Klasse, eine Struktur oder ein Modul, das als die enthaltende Klasse, Struktur oder Modul bezeichnet wird.  
  
 Um einen Wert an den aufrufenden Code zurückzugeben, verwenden eine `Function` Prozedur; verwenden Sie andernfalls eine `Sub` Prozedur.  
  
## <a name="defining-a-function"></a>Definieren einer Funktion  
 Sie können definieren, eine `Function` Prozedur nur auf Modulebene. Aus diesem Grund wird der Deklarationskontext für eine Funktion muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und nicht mit einer Quelldatei, einen Namespace, eine Prozedur oder eines Blocks. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).  
  
 `Function` Prozeduren standardmäßig öffentlichen Zugriff auf. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
 Ein `Function` Prozedur deklariert den Datentyp des Werts, der die Prozedur zurückgibt. Sie können einen beliebigen Datentyp aufweisen oder den Namen des eine Enumeration, eine Struktur, eine Klasse oder einer Schnittstelle angeben. Wenn Sie nicht angeben, die `returntype` -Parameter der Prozedur zurückgibt `Object`.  
  
 Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen auch eine `Implements` -Anweisung, die unmittelbar folgt seine `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Function` (in `definedname`) muss nicht mit dem Namen dieser Prozedur übereinstimmen (in `name`).  
  
> [!NOTE]
>  Lambda-Ausdrücke können Funktion Ausdrücke Inline definiert werden. Weitere Informationen finden Sie unter [Funktionsausdruck](../../../visual-basic/language-reference/operators/function-expression.md) und [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="returning-from-a-function"></a>Zurückgeben aus einer Funktion  
 Wenn die `Function` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, mit der Anweisung, die die Anweisung folgt, die die Prozedur aufgerufen.  
  
 Um einen Wert aus einer Funktion zurückgeben, können Sie entweder den Wert dem Funktionsnamen zuweisen bzw. Fügen Sie ihn in eine `Return` Anweisung.  
  
 Die `Return` Anweisung gleichzeitig weist den Rückgabewert und die Funktion beendet, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 Im folgende Beispiel weist den Rückgabewert den Namen der Funktion `myFunction` und verwendet dann die `Exit Function` -Anweisung zurückgegeben.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 Die `Exit Function` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung von einem `Function` Prozedur. Eine beliebige Anzahl von `Exit Function` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Function` und `Return` Anweisungen.  
  
 Bei Verwendung von `Exit Function` ohne Zuweisen eines Werts zur `name`, die Prozedur gibt zurück, der Standardwert für den Datentyp, der im angegebenen `returntype`. Wenn `returntype` nicht angegeben ist, gibt die Prozedur `Nothing`, dies ist der Standardwert für `Object`.  
  
## <a name="calling-a-function"></a>Aufrufen einer Funktion  
 Rufen Sie eine `Function` Prozedur mithilfe der Prozedurname gefolgt von der Argumentliste in Klammern in einem Ausdruck. Sie können die Klammern weglassen, nur dann, wenn Sie Argumente angeben, werden nicht. Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.  
  
 Rufen Sie eine `Function` Prozedur, die die gleiche Weise, dass Sie jede Bibliothek aufrufen, wie z. B. Funktion `Sqrt`, `Cos`, oder `ChrW`.  
  
 Sie können auch eine Funktion aufrufen, mit dem `Call` Schlüsselwort. In diesem Fall wird der zurückgegebene Wert ignoriert. Verwenden der `Call` Schlüsselwort wird nicht in den meisten Fällen empfohlen. Weitere Informationen finden Sie unter [-Anweisung Call](call-statement.md).  
  
 Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern. Aus diesem Grund verwenden Sie keine `Function` Prozedur in einem arithmetischen Ausdruck, wenn die Funktion den Wert von Variablen im selben Ausdruck ändert.  
  
## <a name="async-functions"></a>Asynchrone Funktionen  
 Die *Async* Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder manuell über mehrere Funktionen oder Lambda-Ausdrücke Teilen Codes zu müssen.  
  
 Wenn Sie eine Funktion mit kennzeichnen der [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Funktion. Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` Funktion, Steuerung an den Aufrufer zurückgegeben, und die Funktion Ausführung wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Funktion fortgesetzt.  
  
> [!NOTE]
>  Ein `Async` Prozedur an den Aufrufer zurückgegeben, wenn entweder das erste erwartete Objekt gefunden wird, die noch nicht abgeschlossen ist, oder er ruft am Ende der `Async` Prozedur, welches Ereignis zuerst eintritt.  
  
 Ein `Async` Funktion kann den Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>. Ein Beispiel für eine `Async` -Funktion, die einen Rückgabetyp <xref:System.Threading.Tasks.Task%601> wird unten bereitgestellt.  
  
 Ein `Async` Funktion kann nicht deklariert werden alle [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.  
  
 Ein [Sub-Anweisung](sub-statement.md) kann auch mit gekennzeichnet werden die `Async` Modifizierer. Dies wird in erster Linie für Ereignishandler verwendet, in dem ein Wert kann nicht zurückgegeben werden. Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur kann nicht durch ausgelöste Ausnahmen abfangen der `Sub` Prozedur.  
  
 Weitere Informationen zu `Async` -Funktionen finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>Iteratorfunktionen  
 Ein *Iterator* Funktion führt eine benutzerdefinierte Iteration durch eine Auflistung, z. B. eine Liste oder ein Array. Eine Iteratorfunktion verwendet die [Yield](yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben. Wenn eine [Yield](yield-statement.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste](for-each-next-statement.md) Anweisung.  
  
 Der Rückgabetyp einer Funktion Iterator kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Function` -Anweisung zum Deklarieren, deren Name, Parameter und Code, der den Text der bilden eine `Function` Prozedur. Die `ParamArray` Modifizierer ermöglicht die Funktion eine Variable Anzahl von Argumenten akzeptieren.  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird die Funktion deklariert, die im vorherigen Beispiel aufgerufen.  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `DelayAsync` ist ein `Async``Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>. `DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund die Funktionsdeklaration von `DelayAsync` muss einen Rückgabetyp verfügen `Task(Of Integer)`. Da der Rückgabetyp ist `Task(Of Integer)`, der Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl. Dies wird in dieser Anweisung dargestellt: `Dim result As Integer = Await delayTask`.  
  
 Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur. Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` muss abgewartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()`. Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da es wurde ein `Await` Ausdruck.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Anweisung](sub-statement.md)  
 [Function-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Parameterliste](parameter-list.md)  
 [Dim-Anweisung](dim-statement.md)  
 [Call-Anweisung](call-statement.md)  
 [Of](of-clause.md)  
 [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md)
