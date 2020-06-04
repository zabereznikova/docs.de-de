---
title: Sub-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: e50b79c31c92ac116d6c82bcececba3340894d74
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404173"
---
# <a name="sub-statement-visual-basic"></a>Sub-Anweisung (Visual Basic)

Deklariert den Namen, die Parameter und den Code, die eine `Sub` Prozedur definieren.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Bestandteile

- `attributelist`

  Optional. Siehe [Attribut Liste](attribute-list.md).

- `Partial`

  Optional. Gibt die Definition einer partiellen Methode an. Siehe [partielle Methoden](../../programming-guide/language-features/procedures/partial-methods.md).

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

- `name`

  Erforderlich. Der Name der Prozedur. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md). Zum Erstellen einer konstruktorprozedur für eine Klasse legen Sie den Namen einer `Sub` Prozedur auf das `New` Schlüsselwort fest. Weitere Informationen finden Sie unter [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Optional. Liste der Typparameter für eine generische Prozedur. Siehe [Typliste](type-list.md).

- `parameterlist`

  Optional. Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen. Siehe [Parameter Liste](parameter-list.md).

- `Implements`

  Optional. Gibt an, dass diese Prozedur eine oder mehrere `Sub` Prozeduren implementiert, die in einer Schnittstelle definiert sind, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird. Siehe [implementierende Anweisung](implements-statement.md).

- `implementslist`

  Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Sub`-Prozeduren.

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

  Optional. Block von-Anweisungen, die in dieser Prozedur ausgeführt werden sollen.

- `End Sub`

  Beendet die Definition dieser Prozedur.

## <a name="remarks"></a>Bemerkungen

Der gesamte ausführbare Code muss sich in einer Prozedur befinden. Verwenden Sie eine- `Sub` Prozedur, wenn Sie keinen Wert an den aufrufenden Code zurückgeben möchten. Verwenden Sie eine- `Function` Prozedur, um einen Wert zurückzugeben.

## <a name="defining-a-sub-procedure"></a>Definieren einer unter Prozedur

Sie können eine `Sub` Prozedur nur auf Modulebene definieren. Der Deklarations Kontext für eine unter Prozedur muss daher eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es darf sich nicht um eine Quelldatei, einen Namespace, eine Prozedur oder einen Block handeln. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

`Sub`Prozeduren werden standardmäßig öffentlich zugänglich. Sie können Ihre Zugriffsebenen anpassen, indem Sie die Zugriffsmodifizierer verwenden.

Wenn die Prozedur das `Implements` Schlüsselwort verwendet, muss die enthaltende Klasse oder Struktur über eine- `Implements` Anweisung verfügen, die direkt auf die- `Class` oder-Anweisung folgt `Structure` . Die `Implements` -Anweisung muss jede Schnittstelle enthalten, die in angegeben ist `implementslist` . Der Name, mit dem eine Schnittstelle `Sub` (in) definiert, `definedname` muss jedoch nicht mit dem Namen dieser Prozedur (in) identisch sein `name` .

## <a name="returning-from-a-sub-procedure"></a>Zurückgeben aus einer unter Prozedur

Wenn eine `Sub` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung nach der Anweisung fortgesetzt, die Sie aufgerufen hat.

Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Prozedur.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Die `Exit Sub` -und- `Return` Anweisungen verursachen einen sofortigen Abbruch einer `Sub` Prozedur. Eine beliebige Anzahl von `Exit Sub` -und- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können die `Exit Sub` -und- `Return` Anweisungen

## <a name="calling-a-sub-procedure"></a>Aufrufen einer unter Prozedur

Sie führen eine `Sub` Prozedur aus, indem Sie den Prozedur Namen in einer-Anweisung verwenden und diesem Namen dann die Argumentliste in Klammern folgen. Sie können die Klammern nur weglassen, wenn Sie keine Argumente angeben. Der Code ist jedoch besser lesbar, wenn Sie immer die Klammern einschließen.

Eine `Sub` Prozedur und eine `Function` Prozedur können über Parameter verfügen und eine Reihe von-Anweisungen ausführen. Eine `Function` Prozedur gibt jedoch einen-Wert zurück, und eine- `Sub` Prozedur ist nicht. Daher können Sie keine `Sub` Prozedur in einem Ausdruck verwenden.

Sie können das `Call` Schlüsselwort verwenden, wenn Sie eine Prozedur aufzurufen `Sub` , aber dieses Schlüsselwort wird für die meisten Verwendungen nicht empfohlen. Weitere Informationen finden Sie unter [callananweisung](call-statement.md).

Visual Basic ordnet arithmetische Ausdrücke manchmal neu an, um die interne Effizienz zu erhöhen. Wenn Ihre Argumentliste Ausdrücke enthält, die andere Prozeduren aufrufen, sollten Sie daher nicht davon ausgehen, dass diese Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.

## <a name="async-sub-procedures"></a>Async-unter Prozeduren

Mithilfe der Async-Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe zu verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke aufzuteilen.

Wenn Sie eine Prozedur mit dem [Async](../modifiers/async.md) -Modifizierer markieren, können Sie den [Erwartungs Operator in](../operators/await-operator.md) der Prozedur verwenden. Wenn das Steuerelement einen `Await` Ausdruck in der `Async` Prozedur erreicht, wird die Steuerung an den Aufrufer zurückgegeben, und der Status der Prozedur wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe vollständig ist, kann die Ausführung in der Prozedur fortgesetzt werden.

> [!NOTE]
> Eine `Async` Prozedur kehrt zum Aufrufer zurück, wenn entweder das erste erwartete Objekt, das noch nicht abgeschlossen ist, gefunden wird oder das Ende der `Async` Prozedur erreicht wird, je nachdem, welcher Wert zuerst auftritt.

Sie können auch eine [Function-Anweisung](function-statement.md) mit dem- `Async` Modifizierer markieren. Eine `Async` Funktion kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601> oder aufweisen <xref:System.Threading.Tasks.Task> . Ein Beispiel weiter unten in diesem Thema zeigt eine `Async` Funktion mit dem Rückgabetyp <xref:System.Threading.Tasks.Task%601> .

`Async``Sub`Prozeduren werden hauptsächlich für Ereignishandler verwendet, bei denen ein Wert nicht zurückgegeben werden kann. Eine `Async` `Sub` Prozedur kann nicht erwartet werden, und der Aufrufer einer `Async` `Sub` Prozedur kann keine Ausnahmen abfangen, die von der Prozedur ausgelöst werden `Sub` .

Eine `Async` Prozedur kann keine [ByRef](../modifiers/byref.md) -Parameter deklarieren.

Weitere Informationen zu `Async` Prozeduren finden Sie unter [asynchrone Programmierung mit Async und warten](../../programming-guide/concepts/async/index.md), [Ablauf Steuerung in](../../programming-guide/concepts/async/control-flow-in-async-programs.md)asynchronen Programmen und asynchronen [Rückgabe Typen](../../programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die- `Sub` Anweisung verwendet, um den Namen, die Parameter und den Code zu definieren, die den Text einer `Sub` Prozedur bilden.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel ist ein-Wert, `DelayAsync` `Async` `Function` der den Rückgabetyp aufweist <xref:System.Threading.Tasks.Task%601> . `DelayAsync` enthält eine `Return` -Anweisung, die eine ganze Zahl zurückgibt. Daher muss die Funktionsdeklaration von den `DelayAsync` Rückgabetyp aufweisen `Task(Of Integer)` . Da der Rückgabetyp ist `Task(Of Integer)` , ergibt die Auswertung des `Await` Ausdrucks in `DoSomethingAsync` eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask` .

Das `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur. Da `DoSomethingAsync` eine `Async` Funktion ist, muss die Aufgabe für den-Aufrufvorgang `DoSomethingAsync` erwartet werden, wie die folgende-Anweisung zeigt: `Await DoSomethingAsync()` . Die `startButton_Click` `Sub` Prozedur muss mit dem- `Async` Modifizierer definiert werden, da Sie über einen `Await` Ausdruck verfügt.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- [Implements-Anweisung](implements-statement.md)
- [Function-Anweisung](function-statement.md)
- [Parameterliste](parameter-list.md)
- [Dim-Anweisung](dim-statement.md)
- [Call-Anweisung](call-statement.md)
- [Natürlich](of-clause.md)
- [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Problembehandlung bei Prozeduren](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Partielle Methoden](../../programming-guide/language-features/procedures/partial-methods.md)
