---
title: 'C#-Referenz: Typtestoperatoren und Cast-Ausdrücke'
description: Erfahren Sie mehr über C#-Operatoren, mit denen Sie den Typ eines Ausdrucksergebnisses überprüfen und bei Bedarf in einen anderen Typ konvertieren können.
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
- as
- typeof
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: 0bf0c3b1cea667456780ff56deb43467fd3bbffd
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916643"
---
# <a name="type-testing-operators-and-cast-expression-c-reference"></a>Typtestoperatoren und Cast-Ausdrücke (C#-Referenz)

Sie können die folgenden Operatoren und Ausdrücke zur Überprüfung oder Konvertierung von Typen verwenden:

- [is-Operator](#is-operator): Prüft, ob der Laufzeittyp eines Ausdrucks mit einem angegebenen Typ kompatibel ist.
- [as-Operator](#as-operator): Konvertiert einen Ausdruck explizit in einen angegebenen Typ, wenn der Laufzeittyp mit diesem Typ kompatibel ist.
- [Cast-Ausdruck](#cast-expression): Führt eine explizite Konvertierung durch
- [typeof-Operator](#typeof-operator): Ruft die <xref:System.Type?displayProperty=nameWithType>-Instanz für einen Typ ab.

## <a name="is-operator"></a>is-Operator

Der `is`-Operator prüft, ob der Laufzeittyp eines Ausdrucksergebnisses mit einem angegebenen Typ kompatibel ist. Ab C# 7.0 überprüft der `is`-Operator ein Ausdrucksergebnis auch anhand eines Musters.

Der Ausdruck mit dem `is`-Operator für die Typüberprüfung weist folgende Form auf:

```csharp
E is T
```

Hierbei ist `E` ein Ausdruck, der einen Wert zurückgibt, und `T` ist der Name eines Typs oder Typparameters. `E` kann weder eine anonyme Methode noch ein Lambdaausdruck sein.

Der `E is T`-Ausdruck gibt `true` zurück, wenn das Ergebnis von `E` nicht NULL ist und durch eine Verweis-, eine Boxing- oder eine Unboxingkonvertierung in den Typ `T` konvertiert werden kann. Andernfalls gibt der Ausdruck `false` zurück. Der `is`-Operator berücksichtigt keine benutzerdefinierten Konvertierungen.

Das folgende Beispiel zeigt, dass der `is`-Operator `true` zurückgibt, wenn der Laufzeittyp eines Ausdrucksergebnisses von einem angegebenen Typ abgeleitet ist, wenn also eine Verweiskonvertierung zwischen Typen besteht:

[!code-csharp[is with reference conversion](snippets/shared/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

Das nächste Beispiel zeigt, dass der `is`-Operator Boxing- und Unboxingkonvertierungen berücksichtigt, [numerische Konvertierungen](../builtin-types/numeric-conversions.md) aber nicht:

[!code-csharp-interactive[is with int](snippets/shared/TypeTestingAndConversionOperators.cs#IsWithInt)]

Informationen zu C#-Konvertierungen finden Sie im Kapitel [Konvertierungen](~/_csharplang/spec/conversions.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

### <a name="type-testing-with-pattern-matching"></a>Typüberprüfung mit Musterabgleich

Ab C# 7.0 überprüft der `is`-Operator ein Ausdrucksergebnis auch anhand eines Musters. Insbesondere wird das Typmuster in der folgenden Form unterstützt:

```csharp
E is T v
```

Hierbei ist `E` ein Ausdruck, der einen Wert zurückgibt, `T` ist der Name eines Typs oder Typparameters, und `v` ist eine neue lokale Variable des Typs `T`. Wenn das Ergebnis von `E` ungleich NULL ist und durch eine Verweis-, eine Boxing- oder eine Unboxingkonvertierung in `T` konvertiert werden kann, gibt der `E is T v`-Ausdruck `true` zurück, und der konvertierte Wert des Ergebnisses von `E` wird der Variable `v` zugewiesen.

Das folgende Beispiel veranschaulicht die Verwendung des `is`-Operators mit dem Typmuster:

[!code-csharp-interactive[is with type pattern](snippets/shared/TypeTestingAndConversionOperators.cs#IsTypePattern)]

Weitere Informationen zum Typmuster und weiteren unterstützten Mustern finden Sie unter [Musterabgleich mit „is“](../keywords/is.md#pattern-matching-with-is).

## <a name="as-operator"></a>as-Operator

Der `as`-Operator konvertiert das Ergebnis eines Ausdrucks explizit in einen angegebenen Verweis- oder Nullable-Typ. Wenn die Konvertierung nicht möglich ist, gibt der `as`-Operator `null` zurück. Im Gegensatz zum [Cast-Ausdruck](#cast-expression) löst der `as`-Operator nie eine Ausnahme aus.

Sehen Sie sich diesen Ausdruck an:

```csharp
E as T
```

Hierbei ist `E` ein Ausdruck, der einen Wert zurückgibt, und `T` ist der Name eines Typs oder Typparameters. Das führt zum gleichen Ergebnis wie dies:

```csharp
E is T ? (T)(E) : (T)null
```

außer dass `E` nur einmal überprüft wird.

Der `as`-Operator berücksichtigt nur Verweis-, Nullable-, Boxing- und Unboxingkonvertierungen. Sie können den `as`-Operator nicht verwenden, um eine benutzerdefinierte Konvertierung auszuführen. Verwenden Sie hierzu einen [Cast-Ausdruck](#cast-expression).

Im folgenden Beispiel wird die Verwendung des `as`-Operators veranschaulicht:

[!code-csharp-interactive[as operator](snippets/shared/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> Wie das vorherige Beispiel zeigt, müssen Sie das Ergebnis des `as`-Ausdrucks mit `null` vergleichen, um zu überprüfen, ob die Konvertierung erfolgreich war. Ab C# 7.0 können Sie den [is-Operator](#type-testing-with-pattern-matching) verwenden, um sowohl die erfolgreiche Durchführung der Konvertierung zu überprüfen als auch bei Erfolg das Ergebnis einer neuen Variable zuzuweisen.

## <a name="cast-expression"></a>Cast-Ausdruck

Ein cast-Ausdruck der Form `(T)E` führt eine explizite Konvertierung des Ergebnisses des Ausdrucks `E` in den Typ `T` durch. Wenn keine explizite Konvertierung von Typ `E` in Typ `T` möglich ist, tritt ein Fehler während der Kompilierung auf. Möglicherweise ist eine explizite Konvertierung zur Laufzeit nicht erfolgreich, und ein cast-Ausdruck löst eine Ausnahme aus.

Das folgende Beispiel zeigt explizite numerische und Verweiskonvertierungen:

[!code-csharp-interactive[cast expression](snippets/shared/TypeTestingAndConversionOperators.cs#Cast)]

Informationen zu expliziten Konvertierungen finden Sie im Abschnitt [Explizite Konvertierungen](~/_csharplang/spec/conversions.md#explicit-conversions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md). Informationen zum Definieren einer benutzerdefinierten expliziten oder impliziten Typkonvertierung finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).

### <a name="other-usages-of-"></a>Andere Verwendungen von „()“

Sie verwenden Klammern auch zum [Aufrufen einer Methode oder eines Delegaten](member-access-operators.md#invocation-expression-).

Mit Klammern können Sie auch die Reihenfolge anpassen, in der Vorgänge in einem Ausdruck ausgewertet werden sollen. Weitere Informationen finden Sie unter [C#-Operatoren](index.md).

## <a name="typeof-operator"></a>typeof-Operator

Der `typeof`-Operator ruft die <xref:System.Type?displayProperty=nameWithType>-Instanz für einen Typ ab. Das Argument für den `typeof`-Operator muss der Name eines Typs oder Typparameters sein, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[typeof operator](snippets/shared/TypeTestingAndConversionOperators.cs#TypeOf)]

Sie können den `typeof`-Operator auch mit ungebundenen generischen Typen verwenden. Der Name eines ungebundenen generischen Typs muss die entsprechende Anzahl von Kommas enthalten: eines weniger als die Anzahl von Typparametern. Das folgende Beispiel zeigt die Verwendung des `typeof`-Operators mit einem ungebundenen generischen Typ:

[!code-csharp-interactive[typeof unbound generic](snippets/shared/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

Ein Ausdruck kann kein Argument des `typeof`-Operators sein. Verwenden Sie die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode, um die <xref:System.Type?displayProperty=nameWithType>-Instanz für den Laufzeittyp eines Ausdrucksergebnisses abzurufen.

### <a name="type-testing-with-the-typeof-operator"></a>Typüberprüfung mit dem `typeof`-Operator

Verwenden Sie den `typeof`-Operator, um zu überprüfen, ob der Laufzeittyp des Ausdrucksergebnisses exakt mit einem angegebenen Typ übereinstimmt. Das folgende Beispiel zeigt den Unterschied zwischen der Typüberprüfung mit dem `typeof`-Operator und mit dem [is-Operator](#is-operator):

[!code-csharp[typeof vs is](snippets/shared/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Die Operatoren `is`, `as` und `typeof` können nicht überladen werden.

Ein benutzerdefinierter Typ kann den `()`-Operator nicht überladen, kann aber benutzerdefinierte Typkonvertierungen definieren, die durch einen cast-Ausdruck ausgeführt werden können. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Der is-Operator](~/_csharplang/spec/expressions.md#the-is-operator)
- [Der as-Operator](~/_csharplang/spec/expressions.md#the-as-operator)
- [cast-Ausdrücke](~/_csharplang/spec/expressions.md#cast-expressions)
- [Der typeof-Operator](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und den Operatoren „is“ und „as“](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Generics in .NET](../../../standard/generics/index.md)
