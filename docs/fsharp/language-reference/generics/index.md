---
title: Generika (F#)
description: Erfahren Sie, wie Sie mithilfe generischer f#-Funktionen und Typen, die Sie Code schreiben, die mit einer Vielzahl von Typen funktioniert, ohne Code wiederholen zu ermöglichen.
ms.date: 05/16/2016
ms.openlocfilehash: fc061f19c6c7fa737f7ca05aae83fd42c0010b37
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "44084961"
---
# <a name="generics"></a>Generika

F#-Funktionswerte, -Methoden, -Eigenschaften und -Aggregattypen, wie z.B. Klassen und Unterscheidungs-Unions können *generisch* sein. Generische Konstrukte enthalten mindestens einen Typparameter, die in der Regel vom Benutzer des generischen Konstrukts angegeben wird. Mit generischen Funktionen und Typen können Sie Code schreiben, der mit einer Vielzahl von Typen funktioniert, ohne den Code für jeden Typ zu wiederholen. Ihren Code generisch zu erstellen kann einfach sein, da Ihr Code häufig implizit abgeleitet wird, um durch den Typrückschluss des Compilers und durch automatische Verallgemeinerungsmechanismen generisch zu sein.

## <a name="syntax"></a>Syntax

```fsharp
// Explicitly generic function.
let function-name<type-parameters> parameter-list =
function-body

// Explicitly generic method.
[ static ] member object-identifer.method-name<type-parameters> parameter-list [ return-type ] =
method-body

// Explicitly generic class, record, interface, structure,
// or discriminated union.
type type-name<type-parameters> type-definition
```

## <a name="remarks"></a>Hinweise

Die Deklaration einer explizit generischen Funktion oder eines Typs entspricht weitgehend einer nicht generischen Funktion oder des Typs, mit Ausnahme der Spezifikation (und Verwendung) der Typparameter in spitzen Klammern nach dem Namen der Funktion oder des Typs.

Deklarationen sind oft implizit generisch. Wenn Sie den Typ jedes Parameters nicht vollständig angeben, der zum Erstellen einer Funktion oder eines Typs verwendet wird, versucht der Compiler den Typ jedes einzelnen Parameters, Werts und jeder Variablen aus dem Code, den Sie schreiben, abzuleiten. Weitere Informationen finden Sie unter [Type Inference (F#)](../type-inference.md). Wenn der Code für Ihren Typ oder die Funktion die Typen der Parameter nicht anderweitig einschränkt, ist die Funktion oder der Typ implizit generisch. Dieser Prozess heißt *automatische Verallgemeinerung*. Es gibt einige Einschränkungen für die automatische Verallgemeinerung. Wenn beispielsweise der F#-Compiler die Typen für ein generisches Konstrukt nicht ableiten kann, meldet der Compiler einen Fehler, der sich auf eine Einschränkung namens *Wertebeschränkung* bezieht. In diesem Fall müssen Sie möglicherweise einige Typanmerkungen hinzufügen. Weitere Informationen über die automatische Verallgemeinerung und die Wertebeschränkung, und wie Sie den Code ändern, um das Problem zu lösen, finden Sie unter [Automatische Verallgemeinerung](automatic-generalization.md).

In der vorherigen Syntax ist *type-parameters* eine durch Trennzeichen getrennte Liste von Parametern, die unbekannte Typen darstellen, jeweils beginnend mit einem einfachen Anführungszeichen und optional mit einer Einschränkungsklausel, die weiter begrenzt, welche Typen für den Typparameter verwendet werden können. Die Syntax für Einschränkungsklauseln verschiedener Arten und andere Informationen zu Einschränkungen finden Sie unter [Einschränkungen](constraints.md).

Die *type-definition* in der Syntax entspricht der Typdefinition für einen nicht generischen Typ. Sie enthält die Konstruktorparameter für einen Klassentyp, eine optionale `as`-Klausel, das gleiche Symbol, die Datensatzfelder, die `inherit`-Klausel, die Optionen für eine Unterscheidungs-Union, `let`- und `do`-Bindungen, die Memberdefinitionen und alles andere, was in einer nicht generischen Typdefinition zulässig ist.

Die anderen Syntaxelemente sind identisch mit denen für nicht generische Funktionen und Typen. Beispielsweise ist *object-identifier* ein Bezeichner, der das enthaltende Objekt selbst darstellt.

Eigenschaften, Felder und Konstruktoren können nicht generischer als der einschließende Typ sein. Außerdem können Werte in einem Modul nicht generisch sein.

## <a name="implicitly-generic-constructs"></a>Implizit generische Konstrukte

Wenn der F#-Compiler die Typen im Code ableitet, behandelt es automatisch alle Funktionen, die als Generische generisch sein können. Wenn Sie einen Typ explizit angeben, wie z.B. einen Parametertyp, verhindern Sie die automatische Verallgemeinerung.

Im folgenden Codebeispiel ist `makeList` generisch, obwohl weder es noch seine Parameter explizit als generisch deklariert werden.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1700.fs)]

Die Signatur der Funktion wird als `'a -> 'a -> 'a list` abgeleitet. Beachten Sie, dass `a` und `b` in diesem Beispiel abgeleitet werden, um über den gleichen Typ zu verfügen. Dies ist, da sie zusammen in einer Liste enthalten sind, und alle Elemente einer Liste müssen vom gleichen Typ sein.

Sie können auch eine Funktion generisch erstellen, indem Sie die Syntax für einfache Anführungszeichen in einer Typanmerkung verwenden, um anzugeben, dass ein Parametertyp ein generischer Typparameter ist. Im folgenden Code ist `function1` generisch, da seine Parameter auf diese Weise als Typparameter deklariert werden.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1701.fs)]

## <a name="explicitly-generic-constructs"></a>Explizit generische Konstrukte

Sie können eine Funktion auch generisch erstellen, indem Sie seine Typparameter explizit in spitzen Klammern (`<type-parameter>`) deklarieren. Dies wird im folgenden Code veranschaulicht.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1703.fs)]

## <a name="using-generic-constructs"></a>Verwenden von generischen Konstrukten

Wenn Sie generische Funktionen oder Methoden verwenden, müssen Sie möglicherweise nicht die Typargumente angeben. Der Compiler verwendet den Typrückschluss, um die entsprechenden Typargumente abzuleiten. Wenn immer noch eine Mehrdeutigkeit vorliegt, können Sie Typargumente in spitzen Klammern angeben und mehrere Typargumente durch Kommas trennen.

Der folgende Code zeigt die Verwendung der Funktionen, die in den vorherigen Abschnitten definiert sind.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1702.fs)]

>[!NOTE]
Es gibt zwei Möglichkeiten zum Verweisen auf einen generischen Typ anhand des Namens. Beispielsweise sind `list<int>` und `int list` zwei Methoden zum Verweisen auf einen generischen Typ `list`, der über ein einzelnes Typargument `int` verfügt. Die letztgenannte Form wird konventionell nur mit integrierten F#-Typen verwendet, wie z.B. `list` und `option`. Wenn mehrere Typargumente vorhanden sind, verwenden Sie normalerweise die Syntax `Dictionary<int, string>`, aber Sie können auch die Syntax `(int, string) Dictionary` verwenden.

## <a name="wildcards-as-type-arguments"></a>Platzhalter als Typargumente

Um anzugeben, dass ein Typargument vom Compiler abgeleitet werden soll, können Sie den Unterstrich bzw. das Platzhaltersymbol (`_`) anstatt eines benannten Typarguments verwenden. Dies wird im folgenden Code veranschaulicht.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1704.fs)]

## <a name="constraints-in-generic-types-and-functions"></a>Einschränkungen bei generischen Typen und Funktionen

In einer generischen Typ- oder Funktionsdefinition können Sie nur diese Konstrukte verwenden, die bekanntermaßen für den generischen Typparameter verfügbar sind. Dies ist erforderlich, um die Überprüfung von Funktions- und Methodenaufrufen zur Kompilierzeit zu aktivieren. Wenn Sie Ihre Typparameter explizit deklarieren, können Sie eine explizite Einschränkung für einen generischen Typparameter anwenden, um den Compiler zu informieren, dass bestimmte Methoden und Funktionen verfügbar sind. Wenn Sie F#-Compiler die generischen Parametertypen ableiten lassen, wird es jedoch die entsprechenden Einschränkungen für Sie bestimmen. Weitere Informationen finden Sie unter [Einschränkungen](constraints.md).

## <a name="statically-resolved-type-parameters"></a>Statisch aufgelöste Typparameter

Es gibt zwei Arten von Typparametern, die in F#-Programmen verwendet werden können. Die Ersten sind generische Typparameter der Art, die in den vorherigen Abschnitten beschrieben werden. Diese erste Art von Typparameter entspricht den generischen Typparametern, die in Sprachen wie Visual Basic und C# verwendet werden. Eine andere Art von Typparameter ist für F# spezifisch und wird als ein *statisch aufgelöster Typparameter* bezeichnet. Informationen zu diesen Konstrukten finden Sie unter [Statisch aufgelöste Typparameter](statically-resolved-type-parameters.md).

## <a name="examples"></a>Beispiele

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1705.fs)]

## <a name="see-also"></a>Siehe auch

- [Sprachreferenz](../index.md)
- [Typen](../fsharp-types.md)
- [Statisch aufgelöste Typparameter](statically-resolved-type-parameters.md)
- [Generika in .NET Framework](~/docs/standard/generics/index.md)
- [Automatische Verallgemeinerung](automatic-generalization.md)
- [Einschränkungen](constraints.md)
