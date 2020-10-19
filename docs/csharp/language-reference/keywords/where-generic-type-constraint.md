---
description: where (generischer Typconstraint) – C#-Referenz
title: where (generischer Typconstraint) – C#-Referenz
ms.date: 04/15/2020
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
- classconstraint_CSharpKeyword
- structconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 75885e21173d31ff0a4ba34fbbd3558f934ae5b7
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050317"
---
# <a name="where-generic-type-constraint-c-reference"></a>where (generischer Typconstraint) (C#-Referenz)

In einer generischen Typdefinition wird die `where`-Klausel verwendet, um Constraints für Typen anzugeben, die als Argumente für einen Typenparameter in generischen Typen, Methoden, Delegaten oder lokalen Funktionen verwendet werden können. Constraints können Schnittstellen und Basisklassen angeben oder einen generischen Typ als Verweis-, Wert- oder nicht verwalteten Typ anfordern. Sie deklarieren die Funktionen, die das Typargument aufweisen muss.

So können Sie beispielsweise eine generische Klasse erstellen, `MyGenericClass`, deren Typparameter `T` die Schnittstelle <xref:System.IComparable%601> implementiert:

[!code-csharp[using an interface constraint](snippets/GenericWhereConstraints.cs#1)]

> [!NOTE]
> Weitere Informationen über die where-Klausel in einem Abfrageausdruck finden Sie unter [where-Klausel](where-clause.md).

Die `where`-Klausel kann auch einen Basisklassenconstraint enthalten. Der Basisklassenconstraint gibt an, dass ein Typ, der als Typargument für den generischen Typ verwendet wird, über die angegebene Klasse als Basisklasse verfügen oder diese Basisklasse sein muss. Wenn ein Basisklassenconstraint verwendet wird, muss er vor jedem anderen Constraint für den Typparameter angezeigt werden. Einige Typen sind nicht als Basisklassenconstraints zulässig: <xref:System.Object>, <xref:System.Array> und <xref:System.ValueType>. Vor C# 7.3 waren <xref:System.Enum>, <xref:System.Delegate> und <xref:System.MulticastDelegate> ebenfalls nicht als Basisklassenconstraints zulässig. Das folgende Beispiel zeigt die Typen, die jetzt als Basisklasse angegeben werden können:

[!code-csharp[using an interface constraint](snippets/GenericWhereConstraints.cs#2)]

In einem Nullable-Kontext in C# 8.0 und höher wird die NULL-Zulässigkeit des Basisklassentyps erzwungen. Wenn die Basisklasse ein Non-Nullable-Typ ist (z. B. `Base`), muss das Typargument ein Non-Nullable-Typ sein. Ist die Basisklasse ein Nullable-Typ (z. B. `Base?`), muss das Typargument ein Nullable- oder Non-Nullable-Verweistyp sein. Der Compiler gibt eine Warnung aus, wenn das Typargument ein Nullable-Verweistyp ist und die Basisklasse ein Non-Nullable-Typ.

Die `where`-Klausel kann angeben, ob der Typ `class` oder `struct` ist. Aufgrund des `struct`-Constraints ist die Angabe eines Basisklassenconstraints von `System.ValueType` nicht notwendig. Der `System.ValueType`-Typ darf nicht als Basisklassenconstraint verwendet werden. Im folgenden Beispiel werden die `class`- und `struct`-Constraints dargestellt:

[!code-csharp[using the class and struct constraints](snippets/GenericWhereConstraints.cs#3)]

In einem Nullable-Kontext in C# 8.0 und höher erfordert der `class`-Constraint einen Non-Nullable-Verweistyp. Um Nullable-Verweistypen zuzulassen, verwenden Sie den `class?`-Constraint, der sowohl Nullable- als auch Non-Nullable-Verweistypen zulässt.

Die `where`-Klausel kann den `notnull`-Constraint enthalten. Der `notnull`-Constraint begrenzt den Typparameter auf Nicht-Nullable-Typen. Bei diesem Typ kann es sich um einen [Werttyp](../builtin-types/value-types.md) oder einen Nicht-Nullable-Verweistyp handeln. Der `notnull`-Constraint ist ab C  8.0 für Code verfügbar, der in einem [`nullable enable`-Kontext](../../nullable-references.md#nullable-contexts) kompiliert wird. Im Gegensatz zu anderen Constraints generiert der Compiler eine Warnung statt eines Fehlers, wenn ein Typargument den `notnull`-Constraint verletzt. Warnungen werden nur in einem `nullable enable`-Kontext generiert.

> [!IMPORTANT]
> Generische Deklarationen, die den `notnull`-Constraint enthalten, können in einem Kontext verwendet werden, in dem nicht bekannt ist, ob NULL-Werte zugelassen sind, aber der Compiler erzwingt den Constraint nicht.

[!code-csharp[using the nonnull constraint](snippets/GenericWhereConstraints.cs#NotNull)]

Die `where`-Klausel kann auch einen `unmanaged`-Constraint einschließen. Der `unmanaged`-Constraint schränkt den Typparameter auf Typen ein, die als [nicht verwaltete Typen](../builtin-types/unmanaged-types.md) bekannt sind. Der `unmanaged`-Constraint erleichtert das Schreiben von Interop-Code in C# auf niedriger Ebene. Dieser Constraint ermöglicht wiederverwendbare Routinen für alle nicht verwalteten Typen. Der `unmanaged`-Constraint kann nicht mit dem `class`- oder `struct`-Constraint kombiniert werden. Der `unmanaged`-Constraint erzwingt, dass der Typ `struct` sein muss:

[!code-csharp[using the unmanaged constraint](snippets/GenericWhereConstraints.cs#4)]

Die `where`-Klausel kann auch einen `new()`-Konstruktorconstraint einschließen. Dieser Constraint ermöglicht das Erstellen einer Instanz eines Typparameters unter Verwendung des `new`-Operators. Der [new()-Constraint](new-constraint.md) informiert den Compiler, dass jedes angegebene Typargument über einen zugänglichen parameterlosen Konstruktor verfügen muss. Zum Beispiel:

[!code-csharp[using the new constraint](snippets/GenericWhereConstraints.cs#5)]

Der `new()`-Constraint wird in der `where`-Klausel als Letztes angezeigt. Der `new()`-Constraint kann nicht mit dem `struct`- oder `unmanaged`-Constraint kombiniert werden. Alle Typen, die diese Constraints erfüllen, müssen einen zugänglichen parameterlosen Konstruktor aufweisen, wodurch der `new()`-Constraint redundant wird.

Bei mehreren Typparametern müssen Sie für jeden davon eine eigene `where`-Klausel verwenden, z.B.:

[!code-csharp[using multiple where constraints](snippets/GenericWhereConstraints.cs#6)]

Sie können auch Constraints wie folgt an Typparameter generischer Methoden anfügen:

[!code-csharp[where constraints with generic methods](snippets/GenericWhereConstraints.cs#7)]

Beachten Sie, dass die Syntax zum Beschreiben der Parameterconstraints für Delegaten mit der Syntax von Methoden identisch ist:

[!code-csharp[where constraints with generic methods](snippets/GenericWhereConstraints.cs#8)]

Informationen zu generischen Delegaten finden Sie unter [Generic Delegates (Generische Delegaten)](../../programming-guide/generics/generic-delegates.md).

Weitere Informationen zur Syntax und der Verwendung von Constraints finden Sie unter [Constraints für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Einführung in Generics](../../programming-guide/generics/index.md)
- [new-Constraint](./new-constraint.md)
- [Constraints für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md)
