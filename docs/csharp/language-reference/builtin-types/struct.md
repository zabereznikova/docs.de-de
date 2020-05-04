---
title: Strukturtypen – C#-Referenz
ms.date: 04/21/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: dbe9b47625589de834b7a8021640885ca0920b96
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "82021273"
---
# <a name="structure-types-c-reference"></a>Strukturtypen (C#-Referenz)

Ein *Strukturtyp* (oder *struct type*) ist ein [Werttyp](value-types.md), der Daten und zugehörige Funktionen kapseln kann. Verwenden Sie das `struct`-Schlüsselwort, um einen Strukturtyp zu definieren:

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

Strukturtypen verfügen über eine *Wertsemantik*. Das heißt, eine Variable eines Strukturtyps enthält eine Instanz des Typs. Standardmäßig werden die Variablenwerte bei der Zuweisung kopiert, dabei handelt es sich um die Übergabe eines Arguments an eine Methode oder die Rückgabe eines Methodenergebnisses. Bei Strukturtypvariablen wird eine Instanz des Typs kopiert. Weitere Informationen finden Sie unter [Werttypen](value-types.md).

In der Regel werden Strukturtypen zum Entwerfen kleiner datenorientierter Typen verwendet, die wenig oder gar kein Verhalten bereitstellen. Beispielsweise verwendet .NET Strukturtypen, um Zahlen (sowohl [Integer](integral-numeric-types.md) als auch [reelle](floating-point-numeric-types.md) Zahlen), [boolesche Werte](bool.md), [Unicode-Zeichen](char.md) und [Zeitinstanzen](xref:System.DateTime) darzustellen. Wenn Sie das Verhalten eines Typs verwenden möchten, sollten Sie eine [Klasse](../keywords/class.md) definieren. Klassentypen verfügen über *Verweissemantik*. Das heißt, eine Variable eines Klassentyps enthält einen Verweis auf eine Instanz des Typs, nicht die Instanz selbst.

Da Strukturtypen eine Wertsemantik nutzen, wird die Definition von *unveränderlichen* Strukturtypen empfohlen.

## <a name="readonly-struct"></a>`readonly`-Struktur

Ab C# 7.2 können Sie mit dem `readonly`-Modifizierer einen Strukturtyp als unveränderlich deklarieren:

[!code-csharp[readonly struct](snippets/StructType.cs#ReadonlyStruct)]

Alle Datenmember einer `readonly`-Struktur müssen als schreibgeschützt gekennzeichnet sein:

- Alle Felddeklarationen müssen den [`readonly`-Modifizierer](../keywords/readonly.md) aufweisen.
- Alle Eigenschaften – auch automatisch implementierte – müssen schreibgeschützt sein.

Auf diese Weise ist garantiert, dass kein Member einer `readonly`-Struktur den Status der Struktur ändert.

> [!NOTE]
> In einer `readonly`-Struktur kann ein Datenmember eines änderbaren Verweistyps weiterhin den eigenen Status ändern. Beispielsweise können Sie eine <xref:System.Collections.Generic.List%601>-Instanz nicht ersetzen, aber neue Elemente zur Instanz hinzufügen.

## <a name="readonly-instance-members"></a>`readonly`-Instanzmember

Ab C# 8.0 können Sie auch den `readonly`-Modifizierer verwenden, um zu deklarieren, dass ein Instanzmember den Zustand einer Struktur nicht ändert. Wenn Sie nicht den gesamten Strukturtyp als `readonly` deklarieren können, verwenden Sie den `readonly`-Modifizierer, um die Instanzmember zu markieren, die den Zustand der Struktur nicht ändern. In einer `readonly`-Struktur ist jeder Instanzmember implizit `readonly`.

Innerhalb eines `readonly`-Instanzmembers können Sie den Instanzfeldern einer Struktur nichts zuweisen. Ein `readonly`-Member kann jedoch ein Nicht-`readonly`-Member aufrufen. In diesem Fall erstellt der Compiler eine Kopie der Strukturinstanz und ruft den Nicht-`readonly`-Member in dieser Kopie auf. Folglich wird die ursprüngliche Strukturinstanz nicht geändert.

In der Regel wenden Sie den `readonly`-Modifizierer auf die folgenden Arten von Instanzmembern an:

- Methoden:

  [!code-csharp[readonly method](snippets/StructType.cs#ReadonlyMethod)]

  Sie können den `readonly`-Modifizierer auch auf Methoden anwenden, die in <xref:System.Object?displayProperty=nameWithType> deklarierte Methoden überschreiben:

  [!code-csharp[readonly override](snippets/StructType.cs#ReadonlyOverride)]

- Eigenschaften und Indexer:

  [!code-csharp[readonly property get](snippets/StructType.cs#ReadonlyProperty)]

  Wenn Sie den `readonly`-Modifizierer auf die Accessoren sowohl einer Eigenschaft als auch eines Indexers anwenden müssen, wenden Sie ihn in der Deklaration der Eigenschaft bzw. des Indexers an.

  > [!NOTE]
  > Der Compiler deklariert einen `get`-Accessor einer [automatisch implementierten Eigenschaft](../../programming-guide/classes-and-structs/auto-implemented-properties.md) als `readonly`, unabhängig davon, ob der `readonly`-Modifizierer in einer Eigenschaftsdeklaration vorhanden ist.

Sie können den `readonly`-Modifizierer nicht auf statische Member eines Strukturtyps anwenden.

Der Compiler kann den `readonly`-Modifizierer für Leistungsoptimierungen verwenden. Weitere Informationen finden Sie unter [Schreiben von sicherem und effizientem C#-Code](../../write-safe-efficient-code.md).

## <a name="limitations-with-the-design-of-a-structure-type"></a>Einschränkungen beim Entwerfen eines Strukturtyps

Beim Entwerfen eines Strukturtyps verfügen Sie über dieselben Funktionen wie bei einem [Klassentyp](../keywords/class.md) mit folgenden Ausnahmen:

- Sie können keinen parameterlosen Konstruktor deklarieren. Jeder Strukturtyp stellt bereits einen impliziten parameterlosen Konstruktor bereit, der den [Standardwert](default-values.md) des Typs erzeugt.

- Sie können kein Instanzfeld und keine Eigenschaft in der Deklaration initialisieren. Sie können jedoch ein [static](../keywords/static.md)- oder [const](../keywords/const.md)-Feld oder eine statische Eigenschaft in der Deklaration initialisieren.

- Der Konstruktor einer Strukturtyps muss alle Instanzfelder des Typs initialisieren.

- Ein Strukturtyp kann nicht von einer anderen Klasse oder einem anderen Strukturtyp erben, und er kann nicht die Basis einer Klasse sein. Allerdings kann ein Strukturtyp [Schnittstellen](../keywords/interface.md) implementieren.

- Innerhalb eines Strukturtyps können Sie keinen [Finalizer](../../programming-guide/classes-and-structs/destructors.md) deklarieren.

## <a name="instantiation-of-a-structure-type"></a>Instanziierung eines Strukturtyps

In C# müssen Sie eine deklarierte Variable initialisieren, bevor sie verwendet werden kann. Da eine Strukturtypvariable nicht den Wert `null` aufweisen kann (es sei denn, es handelt sich um eine Variable eines [Nullable-Werttyps](nullable-value-types.md)), müssen Sie eine Instanz des entsprechenden Typs instanziieren. Dafür stehen verschiedene Möglichkeiten zur Verfügung.

Normalerweise instanziieren Sie einen Strukturtyp, indem Sie einen entsprechenden Konstruktor mit dem Operator [`new`](../operators/new-operator.md) aufrufen. Jeder Strukturtyp verfügt über mindestens einen Konstruktor. Dabei handelt es sich um einen impliziten parameterlosen Konstruktor, der den [Standardwert](default-values.md) des Typs erzeugt. Sie können einen [Standardwertausdruck](../operators/default.md) auch zum Erzeugen des Standardwerts für einen Typ verwenden.

Wenn alle Instanzfelder eines Strukturtyps zugänglich sind, können Sie ihn auch ohne den `new`-Operator instanziieren. In diesem Fall müssen Sie alle Instanzfelder vor der ersten Verwendung der Instanz initialisieren. Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

Verwenden Sie für [integrierte Werttypen](value-types.md#built-in-value-types) die entsprechenden Literale, um den Wert des Typs festzulegen.

## <a name="passing-structure-type-variables-by-reference"></a>Übergeben von Strukturtypvariablen als Verweis

Wenn Sie eine Strukturtypvariable als Argument an eine Methode übergeben oder einen Strukturtypvariable einer Methode zurückgeben, wird die gesamte Instanz des Strukturtyps kopiert. Dies kann sich in Hochleistungsszenarios mit großen Strukturtypen auf die Leistung Ihres Codes auswirken. Sie können das Kopieren von Werten vermeiden, indem Sie eine Strukturtypvariable als Verweis übergeben. Verwenden Sie die Methodenparametermodifizierer [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) oder [`in`](../keywords/in-parameter-modifier.md), um anzugeben, dass ein Argument als Verweis übergeben werden muss. Verwenden Sie [ref returns](../../programming-guide/classes-and-structs/ref-returns.md), um ein Methodenergebnis als Verweis zurückzugeben. Weitere Informationen finden Sie unter [Schreiben von sicherem und effizientem C#-Code](../../write-safe-efficient-code.md).

## <a name="ref-struct"></a>`ref`-Struktur

Ab C# 7.2 können Sie bei der Deklaration eines Strukturtyps den Modifizierer `ref` verwenden. Instanzen eines `ref`-Strukturtyps werden auf dem Stapel zugeordnet und können nicht in den verwalteten Heap überwechseln. Der Compiler grenzt die Nutzung von `ref`-Strukturtypen wie folgt ein, um dies sicherzustellen:

- Eine `ref`-Struktur kann nicht der Elementtyp eines Arrays sein.
- Eine `ref`-Struktur kann kein deklarierter Typ eines Felds einer Klasse oder einer Struktur sein, bei der es sich um keine `ref`-Struktur handelt.
- Eine `ref`-Struktur kann keine Schnittstellen implementieren.
- Für eine `ref`-Struktur kann kein Boxing in <xref:System.ValueType?displayProperty=nameWithType> oder <xref:System.Object?displayProperty=nameWithType> durchgeführt werden.
- Eine `ref`-Struktur kann kein Typargument sein.
- Eine `ref`-Strukturvariable kann nicht von einem [Lambdaausdruck](../../programming-guide/statements-expressions-operators/lambda-expressions.md) oder einer [lokalen Funktion](../../programming-guide/classes-and-structs/local-functions.md) erfasst werden.
- Eine `ref`-Strukturvariable kann nicht in einer [`async`](../keywords/async.md)-Methode verwendet werden. Sie können `ref`-Strukturvariablen jedoch in synchronen Methoden verwenden, z. B. in solchen, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgeben.
- Eine `ref`-Strukturvariable kann nicht in [Iteratoren](../../iterators.md) verwendet werden.

In der Regel definieren Sie einen `ref`-Strukturtyp, wenn Sie einen Typ benötigen, der auch Datenmember von `ref`-Strukturtypen enthält:

[!code-csharp[ref struct](snippets/StructType.cs#RefStruct)]

Kombinieren Sie die `readonly`- und `ref`-Modifizierer in der Typdeklaration (der `readonly`-Modifizierer muss vor dem `ref`-Modifizierer stehen), um eine `ref`-Struktur als [`readonly`](#readonly-struct) zu deklarieren:

[!code-csharp[readonly ref struct](snippets/StructType.cs#ReadonlyRef)]

In .NET sind <xref:System.Span%601?displayProperty=nameWithType> und <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> Beispiele für eine `ref`-Struktur.

## <a name="conversions"></a>Konvertierungen

Für alle Strukturtypen (außer [`ref`struct](#ref-struct)-Typen) gibt es [Boxing- und Unboxing](../../programming-guide/types/boxing-and-unboxing.md)-Umwandlungen in und aus den Typen <xref:System.ValueType?displayProperty=nameWithType> und <xref:System.Object?displayProperty=nameWithType>. Außerdem gibt es Boxing- und Unboxing-Umwandlungen zwischen einem Strukturtyp und der Schnittstelle, die ihn implementiert.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Strukturen](~/_csharplang/spec/structs.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zu in C# 7.2 und höher eingeführten Features finden Sie in den folgenden Featurevorschlägen:

- [Schreibgeschützte Strukturen](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)
- [Schreibgeschützte Instanzmember](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)
- [Kompilierzeitsicherheit für ref-ähnliche Typen](~/_csharplang/proposals/csharp-7.2/span-safety.md)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Entwurfsrichtlinien: Auswählen zwischen Klasse und Struktur](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Entwurfsrichtlinien: Strukturentwurf](../../../standard/design-guidelines/struct.md)
- [Klassen und Strukturen](../../programming-guide/classes-and-structs/index.md)
