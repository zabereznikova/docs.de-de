---
title: Tupel (F#)
description: Informationen Sie zu F#-Tupel, eine Gruppierung von unbenannte jedoch geordnete Werte möglicherweise von anderen Typen.
ms.date: 05/16/2016
ms.openlocfilehash: d017a2ce8a6ad9b3cec8dfa2ee15b47f06d8f67c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564775"
---
# <a name="tuples"></a>Tupel

Ein *Tupel* ist eine Gruppierung von unbenannte jedoch geordnete Werte möglicherweise von anderen Typen.  Tupel kann entweder Verweistypen oder Strukturen sein.

## <a name="syntax"></a>Syntax

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a>Hinweise
Jede *Element* in der vorherigen Syntax kann jeder gültiger F#-Ausdruck sein.

## <a name="examples"></a>Beispiele
Beispiele für Tupel sind Paare, Tripel, usw., der gleichen oder unterschiedliche Typen. Einige Beispiele sind in den folgenden Code dargestellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a>Abrufen einzelner Werte
Sie können mithilfe des Mustervergleichs zugreifen, und weisen Sie Aliasnamen für Tupelelemente, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

Sie können auch ein Tupel über Mustervergleich außerhalb von Löschen einer `match` Ausdruck über `let` Bindung:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

Oder Sie können Muster, die als Eingaben für Funktionen auf Tupel übereinstimmen:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Wenn Sie nur ein Element des Tupels benötigen, kann das Platzhalterzeichen (Unterstrich) verwendet werden, um zu vermeiden, erstellen einen neuen Namen für einen Wert an, dem Sie nicht benötigen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Kopieren Elemente aus einem Verweis Tupel in einer Struktur Tupel ist einfach:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Die Funktionen `fst` und `snd` (nur Tupel verweisen) die ersten und zweiten Sie Elemente eines Tupels bzw.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

Keine integrierte Funktion, die das dritte Element der Tripel zurückgibt vorhanden ist, aber Sie können problemlos wie folgt schreiben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

Im Allgemeinen ist es besser, die mithilfe des Mustervergleichs Zugriff auf Tupelelemente der einzelnen.

## <a name="using-tuples"></a>Verwenden von Tupeln
Tupel bieten eine einfache Möglichkeit, mehrere Werte aus einer Funktion zurückgeben, wie im folgenden Beispiel gezeigt. In diesem Beispiel führt die Ganzzahldivision und gibt das gerundete Ergebnis des Vorgangs als erste Member eines Paars Tupel und den Rest als zweite Element des Paars.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Tupel können auch als Funktionsargumente verwendet werden, wenn sollten vermieden werden die implizitem currying von Funktionsargumenten, die durch die üblichen Funktionssyntax impliziert ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

Der üblichen Syntax zum Definieren der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion, ist der partiellen Anwendung von das erste Argument der Funktion, zu definieren, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

Verwenden Sie ein Tupel als Parameter wird currying deaktiviert. Weitere Informationen finden Sie unter "Partielle Anwendung von Argumenten" im [Funktionen](functions/index.md).

## <a name="names-of-tuple-types"></a>Namen von Tupeltypen
Wenn Sie den Namen eines Typs, die ein Tupel ist schreiben, verwenden Sie die `*` Symbol, um Elemente zu trennen. Für ein Tupel, aus denen besteht eine `int`, `float`, und ein `string`, wie z. B. `(10, 10.0, "ten")`, Typs würde wie folgt geschrieben werden.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperation mit c# Tupel

C#-7.0 eingeführt Tupel in der Sprache.  Tupel in C# geschrieben sind Strukturen und Struktur Tupel in f# entsprechen.  Wenn Sie mit c# zusammenarbeiten müssen, müssen Sie die Struktur Tupel verwenden.

Dies ist einfach.  Angenommen Sie, Sie verfügen über ein Tupel an eine C#-Klasse übergeben und dann verwenden das Ergebnis, das auch ein Tupel ist:

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

Sie können in Ihrem f#-Code dann ein Tupel Struktur als Parameter übergeben und nutzen das Ergebnis als Struktur Tupel.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Konvertieren zwischen Verweis Tupel und Tupel-Struktur

Da Verweis Tupel und Struct-Tuples eine ganz andere zugrunde liegenden Darstellung haben, sind sie nicht implizit konvertiert werden kann.  D. h. kompiliert nicht dem folgenden Code:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

Sie müssen das Muster auf ein Tupel übereinstimmen und die andere die Bestandteile zu erstellen.  Zum Beispiel:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Kompilierte Form der Verweis Tupel
Dieser Abschnitt erklärt die Form der Tupel bei der Prozedur-sind.  Die Informationen hier nicht lesen, es sei denn, Sie .NET Framework 3.5 abzielen notwendig oder niedriger.

Tupel werden in Objekte eines von mehreren generischen Typen, die alle benannten kompiliert `System.Tuple`, für die Stelligkeit oder die Anzahl von Typparametern überladen sind. Tuple-Typen werden in dieser Form angezeigt, bei der Anzeige in einer anderen Sprache, z. B. c# oder Visual Basic, oder wenn Sie ein Tool verwenden, die f#-Konstrukte nicht beachtet. Die `Tuple` Typen in .NET Framework 4 eingeführt wurden. Wenn Sie eine frühere Version von .NET Framework abzielen, verwendet der Compiler-Versionen [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) aus der Version 2.0 der f#-Kernbibliothek. Die Typen in dieser Bibliothek dienen nur für Anwendungen, die auf dem 2.0, 3.0 und 3.5 Versionen von .NET Framework abzielen. Typweiterleitung wird verwendet, um sicherzustellen, dass binäre Kompatibilität zwischen .NET Framework 2.0 und .NET Framework 4 F#-Komponenten.

### <a name="compiled-form-of-struct-tuples"></a>Kompilierte Form der Tupel-Struktur

Struct-Tupel (z. B. `struct (x, y)`), unterscheiden sich grundlegend von Verweis Tupel.  Sie werden in kompiliert die <xref:System.ValueTuple> Typ, durch Stelligkeit oder die Anzahl von Typparametern überlastet.  Gleichwertig zu [c# 7.0 Tupel](../../csharp/tuples.md) und [Visual Basic 2017 Tupel](../../visual-basic/programming-guide/language-features/data-types/tuples.md), und bietet Interoperabilität bidirektional.

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[F#-Typen](fsharp-types.md)
