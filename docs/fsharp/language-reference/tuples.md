---
title: Tupel
description: Erfahren Sie mehr über die F# Tupel eine Gruppierung von unbenannter aber sortierter Werte möglicherweise von anderen Typen.
ms.date: 05/16/2016
ms.openlocfilehash: a1fc31d4dc97c0921545e53b91dcde0547002006
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611047"
---
# <a name="tuples"></a>Tupel

Ein *Tupel* ist eine Gruppierung von unbenannter aber sortierter Werte möglicherweise von anderen Typen.  Tupel kann es sich entweder um Verweistypen oder Strukturen sein.

## <a name="syntax"></a>Syntax

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>Hinweise

Jede *Element* in der vorherigen Syntax kann eine beliebige gültige F# Ausdruck.

## <a name="examples"></a>Beispiele

Beispiele für Tupel sind Paare-Tripeln und usw., der denselben oder unterschiedlichen Typen. Beispiele sind in den folgenden Code dargestellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>Abrufen von einzelnen Werten

Sie können Musterabgleich zugreifen, und weisen Sie Namen für Elemente des Tupels, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

Sie können auch dekonstruieren ein Tupels über Mustervergleich außerhalb einer `match` Ausdruck über `let` Bindung:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

Oder Sie können Muster für Tupel als Eingaben für Funktionen entsprechen:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Wenn Sie nur ein Element des Tupels benötigen, kann das Platzhalterzeichen (Unterstrich) verwendet werden, um zu vermeiden, erstellen einen neuen Namen für ein Wert, den Sie nicht benötigen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Kopieren Elemente aus einem Verweis Tupel in einer Struktur Tupel ist ebenfalls einfach:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Die Funktionen `fst` und `snd` (nur Tupel verweisen) die ersten und zweite Sie bzw. Elemente eines Tupels.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

Es gibt keine integrierte Funktion, die das dritte Element der ein Tripel zurückgibt, aber Sie können ganz einfach wie folgt schreiben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

Im Allgemeinen ist es besser, die den Zugriff auf einzelne Tupelelemente mithilfe des musterabgleichs.

## <a name="using-tuples"></a>Verwendung von Tupeln

Tupel bieten eine bequeme Möglichkeit, mehrere Werte aus einer Funktion zurückgeben, wie im folgenden Beispiel gezeigt. In diesem Beispiel führt die Ganzzahldivision und gibt das gerundete Ergebnis des Vorgangs als erste Member eines Paars Tupel und den Rest als einen zweiten Members des Paares.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Tupel können auch als Funktionsargumente verwendet werden, wenn Sie möchten, um zu vermeiden, die implizitem currying der Argumente der Funktion, die durch die üblichen Funktionssyntax impliziert ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

Der üblichen Syntax für die Definition der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion, die die partielle Anwendung von das erste Argument der Funktion ist zu definieren, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

Currying über ein Tupel als Parameter deaktiviert werden. Weitere Informationen finden Sie unter "Partielle Anwendung von Argumenten" in [Funktionen](functions/index.md).

## <a name="names-of-tuple-types"></a>Namen der Tuple-Typen

Wenn Sie den Namen eines Typs, die ein Tupel ist schreiben, verwenden Sie die `*` Symbol, um Elemente zu trennen. Für ein Tupel, das umfasst eine `int`, `float`, und ein `string`, z. B. `(10, 10.0, "ten")`, Typs würde wie folgt geschrieben werden.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperation mit c#-Tupel

C# 7.0 eingeführt Tupel für die Sprache an.  Tupel in c# sind Strukturen und Strukturieren von Tupeln in F# entsprechen.  Wenn Sie mit c# zusammenarbeiten müssen, müssen Sie Strukturieren von Tupeln verwenden.

Dies ist ganz einfach.  Beispiel: Angenommen Sie, Sie verfügen über ein Tupel an eine C#-Klasse übergeben, und klicken Sie dann nutzen das Ergebnis, das auch ein Tupel ist:

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

In Ihrer F# Code, Sie können ein Tupel Struktur als Parameter übergibt, und nutzen Sie das Ergebnis als Struktur Tupel.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Konvertieren zwischen Verweis Tupel und Strukturieren von Tupeln

Da der Verweis Tupel und Struct-Tuples eine vollständig andere zugrunde liegende Darstellung haben, sind sie nicht implizit konvertiert werden.  D. h. kompiliert nicht Code wie den folgenden:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

Sie müssen Muster für ein Tupel übereinstimmen, und erstellen Sie das andere hat die Bestandteile.  Zum Beispiel:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Kompilierte Form von Tupeln mit Verweis

Dieser Abschnitt erläutert die Form von Tupeln an, wenn sie kompiliert werden.  Die folgenden Informationen ist es nicht notwendig, zu lesen, wenn Sie .NET Framework 3.5 verwenden oder niedriger.

Tupel werden in Objekte eines von mehreren generischen Typen, die alle benannten kompiliert `System.Tuple`, für die Stelligkeit oder die Anzahl der Typparameter überladen sind. Tuple-Typen werden in diesem Formular angezeigt, bei der Anzeige in einer anderen Sprache, z. B. c# oder Visual Basic, oder wenn Sie ein Tool verwenden, die F#-Konstrukte unbekannt ist. Die `Tuple` Typen in .NET Framework 4 eingeführt wurden. Wenn Sie eine frühere Version von .NET Framework Anzielen, verwendet der Compiler Versionen der [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) aus der Version 2.0 der F#-Kernbibliothek. Nur für Anwendungen, die auf der 2.0, 3.0 und 3.5 von .NET Framework-Versionen abzielen, werden die Typen in dieser Bibliothek verwendet. Weiterleiten von Typen wird verwendet, um sicherzustellen, dass binäre Kompatibilität zwischen .NET Framework 2.0 und .NET Framework 4 F# Komponenten.

### <a name="compiled-form-of-struct-tuples"></a>Kompilierte Form von Strukturieren von Tupeln

Strukturieren von Tupeln (z. B. `struct (x, y)`), unterscheiden sich grundlegend von Verweis Tupel.  Sie kompiliert werden, in der <xref:System.ValueTuple> Typ Stelligkeit oder die Anzahl der Typparameter überladen.  Sie entsprechen dem [c# 7.0-Tupel](../../csharp/tuples.md) und [Visual Basic 2017 Tupel](../../visual-basic/programming-guide/language-features/data-types/tuples.md), und bidirektional zusammenarbeiten.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)