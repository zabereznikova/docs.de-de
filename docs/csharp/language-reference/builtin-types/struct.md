---
title: Strukturtypen – C#-Referenz
ms.date: 02/24/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 6113912f176d2d7b68c77ff2e78a361b373ca31a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634638"
---
# <a name="structure-types-c-reference"></a>Strukturtypen (C#-Referenz)

Ein *Strukturtyp* (oder *struct type*) ist ein [Werttyp](value-types.md), der Daten und zugehörige Funktionen kapseln kann. Verwenden Sie das `struct`-Schlüsselwort, um einen Strukturtyp zu definieren:

[!code-csharp[struct example](~/samples/csharp/language-reference/builtin-types/StructType.cs#StructExample)]

Strukturtypen verfügen über eine *Wertsemantik*. Das heißt, eine Variable eines Strukturtyps enthält eine Instanz des Typs. Standardmäßig werden die Variablenwerte bei der Zuweisung kopiert, dabei handelt es sich um die Übergabe eines Arguments an eine Methode oder die Rückgabe eines Methodenergebnisses. Bei Strukturtypvariablen wird eine Instanz des Typs kopiert. Weitere Informationen finden Sie unter [Werttypen](value-types.md).

In der Regel werden Strukturtypen zum Entwerfen kleiner datenorientierter Typen verwendet, die wenig oder gar kein Verhalten bereitstellen. Beispielsweise verwendet .NET Strukturtypen, um Zahlen (sowohl [Integer](integral-numeric-types.md) als auch [reelle](floating-point-numeric-types.md) Zahlen), [boolesche Werte](bool.md), [Unicode-Zeichen](char.md) und [Zeitinstanzen](xref:System.DateTime) darzustellen. Wenn Sie das Verhalten eines Typs verwenden möchten, sollten Sie eine [Klasse](../keywords/class.md) definieren. Klassentypen verfügen über *Verweissemantik*. Das heißt, eine Variable eines Klassentyps enthält einen Verweis auf eine Instanz des Typs, nicht die Instanz selbst.

## <a name="limitations-with-the-design-of-a-structure-type"></a>Einschränkungen beim Entwerfen eines Strukturtyps

Beim Entwerfen eines Strukturtyps verfügen Sie über dieselben Funktionen wie bei einem [Klassentyp](../keywords/class.md) mit folgenden Ausnahmen:

- Sie können keinen parameterlosen Konstruktor deklarieren. Jeder Strukturtyp stellt bereits einen impliziten parameterlosen Konstruktor bereit, der den [Standardwert](default-values.md) des Typs erzeugt.

- Sie können kein Instanzfeld und keine Eigenschaft in der Deklaration initialisieren. Sie können jedoch ein [static](../keywords/static.md)- oder [const](../keywords/const.md)-Feld oder eine statische Eigenschaft in der Deklaration initialisieren.

- Der Konstruktor einer Strukturtyps muss alle Instanzfelder des Typs initialisieren.

- Ein Strukturtyp kann nicht von einer anderen Klasse oder einem anderen Strukturtyp erben, und er kann nicht die Basis einer Klasse sein. Allerdings kann ein Strukturtyp [Schnittstellen](../keywords/interface.md) implementieren.

- Innerhalb eines Strukturtyps können Sie keinen [Finalizer](../../programming-guide/classes-and-structs/destructors.md) deklarieren.

## <a name="instantiation-of-a-structure-type"></a>Instanziierung eines Strukturtyps

In C# müssen Sie eine deklarierte Variable initialisieren, bevor sie verwendet werden kann. Da eine Strukturtypvariable nicht den Wert `null` aufweisen kann (es sei denn, es handelt sich um eine Variable eines [auf NULL festlegbaren Werttyps](nullable-value-types.md)), müssen Sie eine Instanz des entsprechenden Typs instanziieren. Dafür stehen verschiedene Möglichkeiten zur Verfügung.

Normalerweise instanziieren Sie einen Strukturtyp, indem Sie einen entsprechenden Konstruktor mit dem Operator [`new`](../operators/new-operator.md) aufrufen. Jeder Strukturtyp verfügt über mindestens einen Konstruktor. Dabei handelt es sich um einen impliziten parameterlosen Konstruktor, der den [Standardwert](default-values.md) des Typs erzeugt. Sie können auch den [Standardoperator](../operators/default.md) oder das Standardliteral verwenden, um den Standardwert eines Typs zu erzeugen.

Wenn alle Instanzfelder eines Strukturtyps zugänglich sind, können Sie ihn auch ohne den `new`-Operator instanziieren. In diesem Fall müssen Sie alle Instanzfelder vor der ersten Verwendung der Instanz initialisieren. Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:

[!code-csharp[without new](~/samples/csharp/language-reference/builtin-types/StructType.cs#WithoutNew)]

Verwenden Sie für [integrierte Werttypen](value-types.md#built-in-value-types) die entsprechenden Literale, um den Wert des Typs festzulegen.

## <a name="passing-structure-type-variables-by-reference"></a>Übergeben von Strukturtypvariablen als Verweis

Wenn Sie eine Strukturtypvariable als Argument an eine Methode übergeben oder einen Strukturtypvariable einer Methode zurückgeben, wird die gesamte Instanz des Strukturtyps kopiert. Dies kann sich in Hochleistungsszenarios mit großen Strukturtypen auf die Leistung Ihres Codes auswirken. Sie können das Kopieren von Werten vermeiden, indem Sie eine Strukturtypvariable als Verweis übergeben. Verwenden Sie die Methodenparametermodifizierer [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) oder [`in`](../keywords/in-parameter-modifier.md), um anzugeben, dass ein Argument als Verweis übergeben werden muss. Verwenden Sie [ref returns](../../programming-guide/classes-and-structs/ref-returns.md), um ein Methodenergebnis als Verweis zurückzugeben. Weitere Informationen finden Sie unter [Schreiben von sicherem und effizientem C#-Code](../../write-safe-efficient-code.md).

## <a name="conversions"></a>Konvertierungen

Für alle Strukturtypen gibt es [Boxing- und Unboxing](../../programming-guide/types/boxing-and-unboxing.md)-Umwandlungen in und aus den Typen <xref:System.ValueType?displayProperty=nameWithType> und <xref:System.Object?displayProperty=nameWithType>. Außerdem gibt es Boxing- und Unboxing-Umwandlungen zwischen einem Strukturtyp und der Schnittstelle, die ihn implementiert.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Strukturen](~/_csharplang/spec/structs.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Entwurfsrichtlinien: Auswählen zwischen Klasse und Struktur](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Entwurfsrichtlinien: Strukturentwurf](../../../standard/design-guidelines/struct.md)
- [Klassen und Strukturen](../../programming-guide/classes-and-structs/index.md)
