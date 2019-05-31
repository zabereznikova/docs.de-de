---
title: 'Operatoren für den Memberzugriff: C#-Referenz'
description: Enthält Informationen zu C#-Operatoren, die Sie für den Zugriff auf Typmember verwenden können.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: 921d69e3deb7e5bb5115eb723727462839af9b6b
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452892"
---
# <a name="member-access-operators"></a>Operatoren für den Memberzugriff

Sie können die folgenden Operatoren zum Zugriff auf einen Typmember verwenden:

- [`.` (Memberzugriff)](#member-access-operator-): für den Zugriff auf einen Member eines Namespaces oder Typs
- [`[]` (Zugriff auf Arrayelement oder Indexer) ](#indexer-operator-): Zugriff auf ein Arrayelement oder einen Typindexer
- [`?.` und `?[]` (NULL-bedingte Operatoren)](#null-conditional-operators--and-): Ausführen eines Member- oder Elementzugriffs nur dann, wenn ein Operand ungleich NULL ist.
- [`()` (Aufruf)](#invocation-operator-): Aufrufen einer Methode, auf die zugegriffen wurde, oder Aufrufen eines Delegaten

## <a name="member-access-operator-"></a>Memberzugriffsoperator „.“

Sie verwenden das `.`-Token für den Zugriff auf einen Member eines Namespace oder eines Typs, wie die folgenden Beispiele veranschaulichen:

- Verwenden Sie `.` für den Zugriff auf einen geschachtelten Namespace innerhalb eines Namespace, wie im folgenden Beispiel einer [`using`-Anweisung](../keywords/using-directive.md) gezeigt:

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- Verwenden Sie `.`, um einen *qualifizierten Namen* zu bilden, um auf einen Typ innerhalb eines Namespace zuzugreifen, wie im folgenden Code gezeigt:

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  Verwenden Sie eine [`using`-Anweisung](../keywords/using-directive.md), um die Verwendung qualifizierter Namen optional zu machen.

- Verwenden Sie `.` für den Zugriff auf [Typmember](../../programming-guide/classes-and-structs/index.md#members), statische und nicht statische, wie im folgenden Code gezeigt:

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

Sie können auch `.` verwenden, um auf eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md) zuzugreifen.

## <a name="indexer-operator-"></a>Indexeroperator []

Eckige Klammern (`[]`) werden in der Regel für den Zugriff auf Arrays, Indexer oder Zeigerelemente verwendet.

### <a name="array-access"></a>Arrayzugriff

Im folgenden Beispiel wird der Zugriff auf Elemente des Arrays veranschaulicht:

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

Wenn ein Arrayindex sich außerhalb der Grenzen der entsprechenden Dimension eines Arrays befindet, wird eine <xref:System.IndexOutOfRangeException> ausgelöst.

Wie im vorherigen Beispiel gezeigt, verwenden Sie eckige Klammern auch zur Deklaration eines Arraytyps oder Instanziierung von Arrayinstanzen.

Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).

### <a name="indexer-access"></a>Indexerzugriff

Im folgenden Beispiel wird der Indexerzugriff anhand des .NET <xref:System.Collections.Generic.Dictionary%602>-Typs veranschaulicht:

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

Mit Indexern können Sie Instanzen eines benutzerdefinierten Typs auf ähnliche Weise wie ein Array indizieren. Im Gegensatz zu Arrayindizes, die ganze Zahlen sein müssen, können die Indexerargumente mit einem beliebigen Typ deklariert werden.

Weitere Informationen über Indexer finden Sie unter [Indexer](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Andere Verwendungen von „[]“

Informationen zum Zeigerelementzugriff finden Sie unter [Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).

Sie verwenden eckige Klammern auch, um [Attribute](../../programming-guide/concepts/attributes/index.md) anzugeben:

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>NULL-bedingte Operatoren „?.“ und „?[]“

Ein in C# 6 und höher verfügbarer NULL-bedingter Operator wendet nur dann einen Memberzugriffsvorgang (`?.`) oder Elementzugriffsvorgang (`?[]`) auf seinen Operanden an, wenn dieser Operand als ungleich NULL ausgewertet wird. Wenn der Operand als `null` ausgewertet wird, ist das Ergebnis der Anwendung des Operators `null`.

Die NULL-bedingten Operatoren sind Kurzschlussoperatoren. D.h., wenn ein Vorgang in einer Kette von bedingten Member- oder Elementzugriffsvorgängen `null` zurückgibt, wird der Rest der Kette nicht ausgeführt. Im folgenden Beispiel wird `B` nicht ausgewertet, wenn `A` als `null` ausgewertet wird, und `C` wird nicht ausgewertet, wenn `A` oder `B` als `null` ausgewertet wird:

```csharp
A?.B?.Do(C);
A?.B?[C];
```

Im folgenden Beispiel wird die Verwendung des `?.`- und `?[]`-Operators veranschaulicht:

[!code-csharp-interactive[null-conditional operators](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

Das vorhergehende Beispiel zeigt auch die Verwendung des [NULL-Sammeloperators](null-coalescing-operator.md). Sie könnten den NULL-Sammeloperator verwenden, um einen alternativen Ausdruck zum Auswerten in dem Fall bereitzustellen, dass das Ergebnis des NULL-bedingten Vorgangs `null` ist.

### <a name="thread-safe-delegate-invocation"></a>Threadsicherer Delegataufruf

Verwenden Sie den `?.`-Operator, um zu überprüfen, ob ein Delegat ungleich NULL ist, und ihn auf threadsichere Weise aufzurufen (z.B. wenn Sie [ein Ereignis auslösen](../../../standard/events/how-to-raise-and-consume-events.md)), wie der folgende Code zeigt:

```csharp
PropertyChanged?.Invoke(…)
```

Dass Code dem folgenden Code entspricht, den Sie in C# 5 oder früher verwenden würden:

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a>Aufrufoperator „()“

Verwenden Sie Klammern `()` zum Aufrufen einer [Methode](../../programming-guide/classes-and-structs/methods.md), oder rufen Sie einen [Delegaten](../../programming-guide/delegates/index.md) auf.

Im folgenden Beispiel wird der Aufruf einer Methode mit oder ohne Argumente sowie eines Delegaten veranschaulicht:

[!code-csharp-interactive[invocation with ()](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

Klammern verwenden Sie auch beim Aufrufen eines [Konstruktors](../../programming-guide/classes-and-structs/constructors.md) mit einem [ `new` ](../keywords/new-operator.md)-Operator.

### <a name="other-usages-of-"></a>Andere Verwendungen von „()“

Mit Klammern geben Sie auch die Reihenfolge an, in der Vorgänge in einem Ausdruck ausgewertet werden sollen. Weitere Informationen finden Sie im Abschnitt [Hinzufügen von Klammern](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) des Artikels [Operatoren (C#-Programmierhandbuch)](../../programming-guide/statements-expressions-operators/operators.md). Die Liste der Operatoren ist nach der Rangfolge sortiert, siehe [C#-Operatoren](index.md).

[Umwandlungsausdrücke](invocation-operator.md#cast-expression), die einen Konvertierungsoperator aufrufen, verwenden auch Klammern.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Die Operatoren `.` und `()` können nicht überladen werden. Der `[]`-Operator wird auch als nicht überladbarer Operator betrachtet. Verwenden Sie [Indexer](../../programming-guide/indexers/index.md) zur Unterstützung der Indizierung mit benutzerdefinierten Typen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Member access (Memberzugriff)](~/_csharplang/spec/expressions.md#member-access)
- [Elementzugriff](~/_csharplang/spec/expressions.md#element-access)
- [NULL-bedingter Operator](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Aufrufausdrücke](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [?? (NULL-Sammeloperator)](null-coalescing-operator.md)
