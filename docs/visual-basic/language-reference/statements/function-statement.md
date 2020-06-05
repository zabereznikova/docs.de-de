---
title: Function-Anweisung
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
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404627"
---
# <a name="function-statement-visual-basic"></a>Function-Anweisung (Visual Basic)

Deklariert den Namen, die Parameter und den Code, die eine `Function` Prozedur definieren.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Bestandteile

- `attributelist`

  Optional. Siehe [Attribut Liste](attribute-list.md).

- `accessmodifier`

  Optional. Kann eines der folgenden Elemente sein:

  - [Öffentlich](../modifiers/public.md)

  - [Gebieten](../modifiers/protected.md)

  - [Kollegen](../modifiers/friend.md)

  - [Privat](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Privat geschützt](../modifiers/private-protected.md)

  Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Optional. Kann eines der folgenden Elemente sein:

  - [Overloads](../modifiers/overloads.md)

  - [Überschreibt](../modifiers/overrides.md)

  - [Overrides](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Optional. Siehe [Shared](../modifiers/shared.md).

- `Shadows`

  Optional. Siehe [Shadows](../modifiers/shadows.md).

- `Async`

  Optional. Siehe [Async](../modifiers/async.md).

- `Iterator`

  Optional. Siehe [Iterator](../modifiers/iterator.md).

- `name`

  Erforderlich. Der Name der Prozedur. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Optional. Liste der Typparameter für eine generische Prozedur. Siehe [Typliste](type-list.md).

- `parameterlist`

  Optional. Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen. Siehe [Parameter Liste](parameter-list.md).

- `returntype`

  Erforderlich, wenn `Option Strict` ist `On` . Datentyp des Werts, der von dieser Prozedur zurückgegeben wird.

- `Implements`

  Optional. Gibt an, dass diese Prozedur eine oder mehrere `Function` Prozeduren implementiert, die in einer Schnittstelle definiert sind, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird. Siehe [implementierende Anweisung](implements-statement.md).

- `implementslist`

  Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Function`-Prozeduren.

  `implementedprocedure [ , implementedprocedure ... ]`

  Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:

  `interface.definedname`

  |Teil|BESCHREIBUNG|
  |---|---|
  |`interface`|Erforderlich. Der Name einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.|
  |`definedname`|Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist.|

- `Handles`

  Optional. Gibt an, dass diese Prozedur ein oder mehrere bestimmte Ereignisse verarbeiten kann. Siehe [Handles](handles-clause.md).

- `eventlist`

  Erforderlich, wenn `Handles` angegeben wird. Die Liste der Ereignisse, die von dieser Prozedur behandelt werden.

  `eventspecifier [ , eventspecifier ... ]`

  Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:

  `eventvariable.event`

  |Teil|BESCHREIBUNG|
  |---|---|
  |`eventvariable`|Erforderlich. Objekt Variable, die mit dem Datentyp der Klasse oder Struktur deklariert wurde, die das Ereignis auslöst.|
  |`event`|Erforderlich. Der Name des Ereignisses, das diese Prozedur behandelt.|

- `statements`

  Optional. Block von-Anweisungen, die innerhalb dieser Prozedur ausgeführt werden sollen.

- `End Function`

  Beendet die Definition dieser Prozedur.

## <a name="remarks"></a>Bemerkungen

Der gesamte ausführbare Code muss sich in einer Prozedur befinden. Die einzelnen Prozeduren werden wiederum innerhalb einer Klasse, einer Struktur oder eines Moduls deklariert, das als enthaltende Klasse, Struktur oder Modul bezeichnet wird.

Um einen Wert an den aufrufenden Code zurückzugeben, verwenden Sie eine- `Function` Prozedur; andernfalls verwenden Sie eine- `Sub` Prozedur.

## <a name="defining-a-function"></a>Definieren einer Funktion

Sie können eine `Function` Prozedur nur auf Modulebene definieren. Daher muss der Deklarations Kontext für eine Funktion eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es kann sich nicht um eine Quelldatei, einen Namespace, eine Prozedur oder einen Block handeln. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

`Function`Prozeduren werden standardmäßig öffentlich zugänglich. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.

Eine `Function` Prozedur kann den Datentyp des Werts deklarieren, den die Prozedur zurückgibt. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, einer Struktur, einer Klasse oder einer Schnittstelle angeben. Wenn Sie den-Parameter nicht angeben `returntype` , gibt die Prozedur zurück `Object` .

Wenn diese Prozedur das `Implements` Schlüsselwort verwendet, muss die enthaltende Klasse oder Struktur auch über eine- `Implements` Anweisung verfügen, die direkt auf die- `Class` oder-Anweisung folgt `Structure` . Die `Implements` -Anweisung muss jede Schnittstelle enthalten, die in angegeben ist `implementslist` . Der Name, mit dem eine Schnittstelle `Function` (in) definiert, `definedname` muss jedoch nicht mit dem Namen dieser Prozedur (in `name` ) identisch sein.

> [!NOTE]
> Sie können Lambda-Ausdrücke verwenden, um Funktions Ausdrücke Inline zu definieren. Weitere Informationen finden Sie unter [Funktions Ausdruck](../operators/function-expression.md) und [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Zurückgeben von einer Funktion

Wenn die `Function` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung fortgesetzt, die der Anweisung folgt, die die Prozedur aufgerufen hat.

Wenn Sie einen Wert aus einer Funktion zurückgeben möchten, können Sie den Wert entweder dem Funktionsnamen zuweisen oder ihn in eine- `Return` Anweisung einschließen.

Die `Return` -Anweisung weist den Rückgabewert gleichzeitig zu und beendet die-Funktion, wie im folgenden Beispiel gezeigt.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

Im folgenden Beispiel wird der Rückgabewert dem Funktionsnamen zugewiesen, `myFunction` und anschließend wird die- `Exit Function` Anweisung verwendet, um zurückzugeben.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Die `Exit Function` -und- `Return` Anweisungen verursachen einen sofortigen Abbruch einer `Function` Prozedur. Eine beliebige Anzahl von `Exit Function` -und- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können die `Exit Function` -und- `Return` Anweisungen

Wenn Sie verwenden `Exit Function` , ohne einen Wert zuzuweisen `name` , gibt die Prozedur den Standardwert für den Datentyp zurück, der in angegeben ist `returntype` . Wenn `returntype` nicht angegeben wird, gibt die Prozedur zurück `Nothing` . Dies ist der Standardwert für `Object` .

## <a name="calling-a-function"></a>Aufrufen einer Funktion

Sie können eine `Function` Prozedur mit dem Prozedur Namen, gefolgt von der Argumentliste in Klammern, in einem Ausdruck aufzurufen. Sie können die Klammern nur weglassen, wenn Sie keine Argumente angeben. Der Code ist jedoch besser lesbar, wenn Sie immer die Klammern einschließen.

Sie können eine `Function` Prozedur auf dieselbe Weise wie eine beliebige Bibliotheksfunktion (z `Sqrt` . b `Cos` ., oder) aufzurufen `ChrW` .

Sie können eine Funktion auch mit dem- `Call` Schlüsselwort abrufen. In diesem Fall wird der Rückgabewert ignoriert. Die Verwendung des- `Call` Schlüssel Worts ist in den meisten Fällen nicht empfehlenswert. Weitere Informationen finden Sie unter [callananweisung](call-statement.md).

Visual Basic ordnet arithmetische Ausdrücke manchmal neu an, um die interne Effizienz zu erhöhen. Aus diesem Grund sollten Sie keine `Function` Prozedur in einem arithmetischen Ausdruck verwenden, wenn die Funktion den Wert von Variablen im gleichen Ausdruck ändert.

## <a name="async-functions"></a>Async-Funktionen

Mit der *Async* -Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda Ausdrücke aufteilen zu müssen.

Wenn Sie eine Funktion mit dem [Async](../modifiers/async.md) -Modifizierer markieren, können Sie den [Erwartungs Operator in](../operators/await-operator.md) der Funktion verwenden. Wenn das Steuerelement einen `Await` Ausdruck in der `Async` Funktion erreicht, wird die Steuerung an den Aufrufer zurückgegeben, und der Status der Funktion wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe vollständig ist, kann die Ausführung in der Funktion fortgesetzt werden.

> [!NOTE]
> Eine `Async` Prozedur wird an den Aufrufer zurückgegeben, wenn Sie entweder auf das erste erwartete Objekt trifft, das noch nicht abgeschlossen ist, oder bis zum Ende der `Async` Prozedur, je nachdem, welcher Wert zuerst auftritt.

Eine `Async` Funktion kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601> oder aufweisen <xref:System.Threading.Tasks.Task> . Ein Beispiel für eine `Async` Funktion mit dem Rückgabetyp <xref:System.Threading.Tasks.Task%601> wird unten bereitgestellt.

Eine `Async` Funktion kann keine [ByRef](../modifiers/byref.md) -Parameter deklarieren.

Eine [Sub-Anweisung](sub-statement.md) kann auch mit dem- `Async` Modifizierer gekennzeichnet werden. Dies wird hauptsächlich für Ereignishandler verwendet, bei denen kein Wert zurückgegeben werden kann. Eine `Async` `Sub` Prozedur kann nicht erwartet werden, und der Aufrufer einer `Async` `Sub` Prozedur kann keine Ausnahmen abfangen, die von der Prozedur ausgelöst werden `Sub` .

Weitere Informationen zu `Async` -Funktionen finden Sie [unter asynchrone Programmierung mit Async und warten](../../programming-guide/concepts/async/index.md), [Ablauf Steuerung in](../../programming-guide/concepts/async/control-flow-in-async-programs.md)asynchronen Programmen und [Async-Rückgabe Typen](../../programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Iteratorfunktionen

Eine *Iteratorfunktion* führt eine benutzerdefinierte iterierung für eine Auflistung aus, z. b. eine Liste oder ein Array. Eine Iteratorfunktion verwendet die [Yield](yield-statement.md) -Anweisung, um jedes Element einzeln zurückzugeben. Wenn eine [Yield](yield-statement.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Sie verwenden einen Iterator aus dem Client Code, indem Sie eine [for each-... Next](for-each-next-statement.md) -Anweisung.

Der Rückgabetyp einer Iteratorfunktion kann <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> oder sein <xref:System.Collections.Generic.IEnumerator%601> .

Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die- `Function` Anweisung verwendet, um den Namen, die Parameter und den Code, die den Text einer Prozedur bilden, zu deklarieren `Function` . Der- `ParamArray` Modifizierer ermöglicht der-Funktion, eine Variable Anzahl von Argumenten zu akzeptieren.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Funktion aufgerufen, die im vorherigen Beispiel deklariert wurde.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel ist ein-Wert, `DelayAsync` `Async` `Function` der den Rückgabetyp aufweist <xref:System.Threading.Tasks.Task%601> . `DelayAsync` enthält eine `Return` -Anweisung, die eine ganze Zahl zurückgibt. Daher muss die Funktionsdeklaration von den `DelayAsync` Rückgabetyp aufweisen `Task(Of Integer)` . Da der Rückgabetyp ist `Task(Of Integer)` , erzeugt die Auswertung des `Await` Ausdrucks in `DoSomethingAsync` eine ganze Zahl. Dies wird in dieser-Anweisung veranschaulicht: `Dim result As Integer = Await delayTask` .

Das `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur. Da `DoSomethingAsync` eine `Async` Funktion ist, muss die Aufgabe für den-Aufrufvorgang `DoSomethingAsync` erwartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()` . Die `startButton_Click` `Sub` Prozedur muss mit dem- `Async` Modifizierer definiert werden, da Sie über einen `Await` Ausdruck verfügt.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- [Sub-Anweisung](sub-statement.md)
- [Function-Prozeduren](../../programming-guide/language-features/procedures/function-procedures.md)
- [Parameterliste](parameter-list.md)
- [Dim-Anweisung](dim-statement.md)
- [Call-Anweisung](call-statement.md)
- [Natürlich](of-clause.md)
- [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Problembehandlung bei Prozeduren](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Funktions Ausdruck](../operators/function-expression.md)
