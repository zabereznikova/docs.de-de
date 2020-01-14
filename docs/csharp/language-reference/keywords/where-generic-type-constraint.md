---
title: where (Einschränkung des generischen Typs) – C#-Referenz
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 19bf7682916336173ed93619fb6f0ff1242a1b30
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712805"
---
# <a name="where-generic-type-constraint-c-reference"></a>where (Einschränkung des generischen Typs) (C#-Referenz)

In einer generischen Typdefinition wird die `where`-Klausel verwendet, um Einschränkungen für Typen anzugeben, die als Argumente für einen Typenparameter in generischen Typen, Methoden, Delegaten oder lokalen Funktionen verwendet werden können. Einschränkungen können Schnittstellen und Basisklassen angeben oder einen generischen Typ als Verweis-, Wert- oder nicht verwalteten Typ anfordern. Sie deklarieren die Funktionen, die das Typargument besitzen muss.

So können Sie beispielsweise eine generische Klasse erstellen, `MyGenericClass`, deren Typparameter `T` die Schnittstelle <xref:System.IComparable%601> implementiert:

[!code-csharp[using an interface constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> Weitere Informationen über die where-Klausel in einem Abfrageausdruck finden Sie unter [where-Klausel](where-clause.md).

Die `where`-Klausel kann auch eine Basisklasseneinschränkung enthalten. Die Basisklasseneinschränkung gibt an, dass ein Typ, der als Typargument für den generischen Typ verwendet wird, über die angegebene Klasse als Basisklasse verfügen muss (oder diese Basisklasse sein muss), um als Typargument für diesen generischen Typ verwendet werden zu können. Wenn eine Basisklasseneinschränkung verwendet wird, muss sie vor jeder anderen Einschränkung für den Typparameter angezeigt werden. Einige Typen sind nicht als Basisklasseneinschränkungen zulässig: <xref:System.Object>, <xref:System.Array> und <xref:System.ValueType>. Vor C# 7.3 waren <xref:System.Enum>, <xref:System.Delegate> und <xref:System.MulticastDelegate> ebenfalls nicht als Basisklasseneinschränkungen zulässig. Das folgende Beispiel zeigt die Typen, die jetzt als Basisklasse angegeben werden können:

[!code-csharp[using an interface constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

Die `where`-Klausel kann angeben, ob der Typ `class` oder `struct` ist. Aufgrund der `struct`-Einschränkung ist die Angabe einer Basisklasseneinschränkung von `System.ValueType` nicht notwendig. Der `System.ValueType`-Typ darf nicht als Basisklasseneinschränkung verwendet werden. Im folgenden Beispiel werden die `class`- und `struct`-Einschränkungen dargestellt:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

Die `where`-Klausel kann die `notnull`-Einschränkung enthalten. Die `notnull`-Einschränkung begrenzt den Typparameter auf Nicht-Nullable-Typen. Bei diesem Typ kann es sich um einen [Werttyp](struct.md) oder einen Nicht-Nullable-Verweistyp handeln. Die `notnull`-Einschränkung ist ab C# 8.0 für Code verfügbar, der in einem [`nullable enable`-Kontext](../../nullable-references.md#nullable-contexts) kompiliert wird. Im Gegensatz zu anderen Einschränkungen generiert der Compiler eine Warnung statt eines Fehlers, wenn ein Typargument die `notnull`-Einschränkung verletzt. Warnungen werden nur in einem `nullable enable`-Kontext generiert. 

> [!IMPORTANT]
> Generische Deklarationen, die die `notnull`-Einschränkung enthalten, können in einem Kontext verwendet werden, in dem nicht bekannt ist, ob NULL-Werte zugelassen sind, aber der Compiler erzwingt die Einschränkung nicht.

[!code-csharp[using the nonnull constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#NotNull)]

Die `where`-Klausel kann auch eine `unmanaged`-Einschränkung einschließen. Die `unmanaged`-Einschränkung schränkt den Typparameter auf Typen ein, die als [nicht verwaltete Typen](../builtin-types/unmanaged-types.md) bekannt sind. Die `unmanaged`-Einschränkung erleichtert das Schreiben von Interop-Code in C# auf niedriger Ebene. Diese Einschränkung ermöglicht wiederverwendbare Routinen für alle nicht verwalteten Typen. Die `unmanaged`-Einschränkung kann nicht mit der `class`- oder `struct`-Einschränkung kombiniert werden. Die `unmanaged`-Einschränkung erzwingt, dass der Typ `struct` sein muss:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

Die `where`-Klausel kann auch eine `new()`-Konstruktoreinschränkung einschließen. Diese Einschränkung ermöglicht das Erstellen einer Instanz eines Typparameters unter Verwendung des `new`-Operators. Die [new()-Einschränkung](new-constraint.md) informiert den Compiler, dass jedes angegebene Typargument über einen zugänglichen parameterlosen Konstruktor verfügen muss. Zum Beispiel:

[!code-csharp[using the new constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

Die `new()`-Einschränkung wird in der `where`-Klausel als Letztes angezeigt. Die `new()`-Einschränkung kann nicht mit der `struct`- oder `unmanaged`-Einschränkung kombiniert werden. Alle Typen, die diese Einschränkungen erfüllen, müssen einen zugänglichen parameterlosen Konstruktor aufweisen, wodurch die `new()`-Einschränkung redundant wird.

Bei mehreren Typparametern müssen Sie für jeden davon eine eigene `where`-Klausel verwenden, z.B.:

[!code-csharp[using multiple where constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

Sie können auch Einschränkungen wie folgt an Typparameter generischer Methoden anfügen:

[!code-csharp[where constraints with generic methods](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

Beachten Sie, dass die Syntax zum Beschreiben der Parametereinschränkungen für Delegaten mit der Syntax von Methoden identisch ist:

[!code-csharp[where constraints with generic methods](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

Informationen zu generischen Delegaten finden Sie unter [Generic Delegates (Generische Delegaten)](../../programming-guide/generics/generic-delegates.md).

Weitere Informationen zur Syntax und der Verwendung von Einschränkungen finden Sie unter [Einschränkungen für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Einführung in Generics](../../programming-guide/generics/index.md)
- [new-Einschränkung](./new-constraint.md)
- [Einschränkungen für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md)
