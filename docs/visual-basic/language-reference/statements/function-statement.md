---
title: Funktion-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: af87477f81fab8406d726ebc8c81260b371d71c8
ms.lasthandoff: 03/13/2017

---
# <a name="function-statement-visual-basic"></a>Function-Anweisung (Visual Basic)
Deklariert den Namen, Parameter und Code, definieren ein `Function` Verfahren.  
  
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
  
     Optional. Finden Sie unter [Attributliste](attribute-list.md).  
  
-   `accessmodifier`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Optional. Finden Sie unter [freigegebenen](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Optional. Finden Sie unter [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `Iterator`  
  
     Optional. Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Prozedur. Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `typeparamlist`  
  
     Optional. Liste mit Typparametern für eine generische Prozedur. Finden Sie unter [Liste](type-list.md).  
  
-   `parameterlist`  
  
     Optional. Die Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt. Finden Sie unter [Parameterliste](parameter-list.md).  
  
-   `returntype`  
  
     Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp des Werts, der von dieser Prozedur zurückgegeben.  
  
-   `Implements`  
  
     Optional. Gibt an, dass diese Prozedur eine oder mehrere implementiert `Function` Prozeduren, die jeweils in einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert definiert. Finden Sie unter [Anweisung implementiert](implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Function`-Prozeduren.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`interface`|Erforderlich. Name der Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist.|  
  
-   `Handles`  
  
     Optional. Gibt an, dass diese Prozedur eine oder mehrere bestimmte Ereignisse behandeln kann. Finden Sie unter [behandelt](handles-clause.md).  
  
-   `eventlist`  
  
     Erforderlich, wenn `Handles` angegeben wird. Die Liste der Ereignisse, die diese Prozedur behandelt.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:  
  
     `eventvariable.event`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`eventvariable`|Erforderlich. Objektvariable deklariert, die mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.|  
    |`event`|Erforderlich. Der Name des Ereignisses, die diese Prozedur behandelt.|  
  
-   `statements`  
  
     Optional. Der Block von Anweisungen, die innerhalb dieser Prozedur ausgeführt werden.  
  
-   `End Function`  
  
     Beendet die Definition dieser Prozedur.  
  
## <a name="remarks"></a>Hinweise  
 Der gesamte ausführbare Code muss innerhalb einer Prozedur sein. Jede Prozedur deklariert, innerhalb einer Klasse, eine Struktur oder ein Modul, das als die enthaltende Klasse, Struktur oder Modul bezeichnet wird.  
  
 Verwenden, um einen Wert an den aufrufenden Code zurückgeben, eine `Function` Verfahren; verwenden Sie andernfalls ein `Sub` Verfahren.  
  
## <a name="defining-a-function"></a>Definieren einer Funktion  
 Sie können eine `Function` Prozedur nur auf Modulebene. Aus diesem Grund Deklarationskontext für eine Funktion muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein und darf keine Quelldatei, einen Namespace, eine Prozedur oder ein Block sein. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](declaration-contexts-and-default-access-levels.md).  
  
 `Function`-Prozeduren weisen standardmäßig öffentlichen Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
 Ein `Function` Prozedur deklariert den Datentyp des Werts, der die Prozedur zurückgibt. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, einer Struktur, einer Klasse oder Schnittstelle angeben. Wenn Sie keinen der `returntype` -Parameter der Prozedur zurückgegebenen `Object`.  
  
 Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur müssen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Function` (in `definedname`) muss mit dem Namen dieser Prozedur übereinstimmen (in `name`).  
  
> [!NOTE]
>  Lambda-Ausdrücke können Inlinefunktion Ausdrücken definieren. Weitere Informationen finden Sie unter [Funktionsausdruck](../../../visual-basic/language-reference/operators/function-expression.md) und [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="returning-from-a-function"></a>Zurückgeben aus einer Funktion  
 Wenn die `Function` -Prozedur zum aufrufenden Code zurückkehrt, Ausführung mit der Anweisung fortgesetzt, die auf die Anweisung folgt, die die Prozedur aufgerufen.  
  
 Um einen Wert aus einer Funktion zurückgeben, Sie können entweder den Wert dem Funktionsnamen zuweisen oder ihn in eine `Return` Anweisung.  
  
 Die `Return` Anweisung gleichzeitig weist den Rückgabewert und beendet die Funktion wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrStatements&#24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 Das folgende Beispiel weist den Rückgabewert an den Funktionsnamen `myFunction` und verwendet dann die `Exit Function` -Anweisung zurückgegeben.  
  
 [!code-vb[VbVbalrStatements&23;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 Die `Exit Function` und `Return` -Anweisung führen zur unmittelbare Beendigung einer `Function` Prozedur. Eine beliebige Anzahl von `Exit Function` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Function` und `Return` Anweisungen.  
  
 Bei Verwendung von `Exit Function` ohne Zuweisen eines Werts zur `name`, die Prozedur gibt den Standardwert für den Datentyp, der im angegebenen `returntype`. Wenn `returntype` nicht angegeben ist, gibt die Prozedur `Nothing`, der Standardwert für `Object`.  
  
## <a name="calling-a-function"></a>Aufrufen einer Funktion  
 Rufen Sie eine `Function` Prozedur über den Prozedurnamen, gefolgt von der Argumentliste in Klammern in einem Ausdruck. Sie können die Klammern weglassen, nur dann, wenn Sie Argumente angeben, werden nicht. Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.  
  
 Rufen Sie eine `Function` Prozedur genauso, als Sie jede Bibliothek aufrufen, wie z. B. Funktion `Sqrt`, `Cos`, oder `ChrW`.  
  
 Sie können auch eine Funktion aufrufen, mit dem `Call` Schlüsselwort. In diesem Fall ist der Rückgabewert ignoriert. Verwenden der `Call` Schlüsselwort wird nicht in den meisten Fällen empfohlen. Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).  
  
 Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz zu erhöhen. Aus diesem Grund sollten Sie nicht verwenden einer `Function` Prozedur in einem arithmetischen Ausdruck, wenn die Funktion den Wert von Variablen im selben Ausdruck ändert.  
  
## <a name="async-functions"></a>Async-Funktion  
 Die *Async* Feature können Sie zum Aufrufen von asynchronen Funktionen ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke teilen.  
  
 Das Markieren eine Funktion mit der [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Funktion. Wenn das Steuerelement erreicht eine `Await` Ausdruck in der `Async` Funktion, die Steuerung an den Aufrufer zurückgegeben, und Status in der Funktion wird angehalten, bis die Aufgabe abgeschlossen ist. Wenn der Vorgang abgeschlossen ist, können in der Funktion die Ausführung fortsetzen.  
  
> [!NOTE]
>  Ein `Async` Prozedur an den Aufrufer zurückgegeben, wenn entweder das erste await-Objekt gefunden, die noch nicht abgeschlossen ist oder das Ende erreicht die `Async` Verfahren, welches Ereignis zuerst eintritt.  
  
 Ein `Async` Funktion kann keinen Rückgabetyp aufweisen oder <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Ein Beispiel für eine `Async` -Funktion, die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>finden Sie weiter unten.</xref:System.Threading.Tasks.Task%601>  
  
 Ein `Async` Funktion kann nicht deklariert werden, keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.  
  
 Ein [Sub-Anweisung](sub-statement.md) kann auch gekennzeichnet werden, mit der `Async` Modifizierer. Dies wird hauptsächlich für Ereignishandler verwendet, kann ein Wert zurückgegeben werden. Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur kann nicht von ausgelösten Ausnahmen abfangen der `Sub` Verfahren.  
  
 Weitere Informationen zu `Async` -Funktionen finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>Iteratorfunktionen  
 Ein *Iterator* Funktion führt eine benutzerdefinierte Iteration durch eine Auflistung, z. B. eine Liste oder ein Array. Eine Iteratorfunktion verwendet die [ergeben](yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben. Wenn ein [ergeben](yield-statement.md) -Anweisung erreicht ist, wird die aktuelle Position im Code gespeichert. Die Ausführung wird von diesem Speicherort das nächste Mal neu gestartet, wenn, das die Iteratorfunktion aufgerufen wird.  
  
 Sie rufen den Iterator im Client-Code mit einem [für jeden... Nächste](for-each-next-statement.md) Anweisung.  
  
 Der Rückgabetyp einer Funktion Iterator kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
 Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Function` Anweisung deklariert den Namen, Parameter und Code, der den Text der form einer `Function` Prozedur. Die `ParamArray` -Modifizierer kann eine Funktion eine Variable Anzahl von Argumenten akzeptieren.  
  
 [!code-vb[VbVbalrStatements&#25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird die im vorangehenden Beispiel deklarierte Funktion aufgerufen.  
  
 [!code-vb[VbVbalrStatements&#26;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `DelayAsync` ist ein `Async``Function` , bei dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> `DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund der Deklaration des `DelayAsync` muss einen Rückgabetyp haben `Task(Of Integer)`. Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl. Dies wird in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.  
  
 Die `startButton_Click` Verfahren ist ein Beispiel für ein `Async Sub` Verfahren. Da `DoSomethingAsync` ist ein `Async` -Funktion, die die Aufgabe für den Aufruf von `DoSomethingAsync` muss gewartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()`. Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, weil sie verfügt über eine `Await` Ausdruck.  
  
 [!code-vb[CsAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
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
