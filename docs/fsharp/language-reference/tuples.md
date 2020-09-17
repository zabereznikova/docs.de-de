---
title: Tupel
description: 'Erfahren Sie mehr über das F #-Tupel, eine Gruppierung unbenannter, aber geordneter Werte, die möglicherweise unterschiedlich sind.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f4adf7e10e22d8b7a8cf697baee15962adf3630
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720360"
---
# <a name="tuples"></a>Tupel

Ein *Tupel* ist eine Gruppierung unbenannter, aber geordneter Werte, die möglicherweise unterschiedliche Typen sind.  Tupel können entweder Verweis Typen oder Strukturen sein.

## <a name="syntax"></a>Syntax

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>Bemerkungen

Jedes *Element* in der vorherigen Syntax kann ein beliebiger gültiger F #-Ausdruck sein.

## <a name="examples"></a>Beispiele

Beispiele für Tupel sind Paare, Paare usw. desselben oder verschiedener Typen. Einige Beispiele sind im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>Abrufen einzelner Werte

Sie können den Musterabgleich zum Zugreifen auf und Zuweisen von Namen für Tupelelemente verwenden, wie im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

Sie können ein Tupel auch über einen Musterabgleich außerhalb eines `match` Ausdrucks über eine  `let` Bindung dekonstruieren:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

Oder Sie können die Übereinstimmung von Tupeln als Eingaben für Funktionen vergleichen:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Wenn Sie nur ein Element des Tupels benötigen, können Sie das Platzhalter Zeichen (Unterstrich) verwenden, um zu vermeiden, dass ein neuer Name für einen Wert erstellt wird, den Sie nicht benötigen.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Das Kopieren von Elementen aus einem verweistupel in ein strukturtupel ist ebenfalls einfach:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Die Funktionen `fst` und `snd` (nur verweistupel) geben jeweils das erste und zweite Element eines Tupels zurück.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

Es ist keine integrierte Funktion vorhanden, die das dritte Element eines Triple-Elements zurückgibt, aber Sie können es ganz einfach wie folgt schreiben.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

Im Allgemeinen ist es besser, den Musterabgleich für den Zugriff auf einzelne Tupelelemente zu verwenden.

## <a name="using-tuples"></a>Verwenden von Tupeln

Tupel stellen eine bequeme Möglichkeit dar, mehrere Werte aus einer Funktion zurückzugeben, wie im folgenden Beispiel gezeigt. Dieses Beispiel führt eine ganzzahlige Division aus und gibt das abgerundete Ergebnis des Vorgangs als ersten Member eines tupelpaars und den Rest als zweiten Member des Paars zurück.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Tupel können auch als Funktionsargumente verwendet werden, wenn Sie die implizite Currying von Funktions Argumenten vermeiden möchten, die von der üblichen Funktions Syntax impliziert werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

Die übliche Syntax zum Definieren der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion zu definieren, bei der es sich um die partielle Anwendung des ersten Arguments der Funktion handelt, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

Wenn Sie ein Tupel als Parameter verwenden, wird die Currying deaktiviert. Weitere Informationen finden Sie unter "partielle Anwendung von Argumenten" in [Functions](./functions/index.md).

## <a name="names-of-tuple-types"></a>Namen von Tupeltypen

Wenn Sie den Namen eines Typs schreiben, bei dem es sich um ein Tupel handelt, verwenden Sie das `*` Symbol zum Trennen von Elementen. Bei einem Tupel, das aus `int` ,, `float` und besteht `string` , z `(10, 10.0, "ten")` . b., würde der Typ wie folgt geschrieben werden.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperation mit c#-Tupeln

In c# 7,0 wurden Tupel in die Sprache eingeführt.  Tupel in c# sind Strukturen und entsprechen strukturtupeln in F #.  Wenn Sie mit c# interagieren müssen, müssen Sie strukturtupel verwenden.

Dies ist einfach.  Stellen Sie sich beispielsweise vor, Sie müssen ein Tupel an eine c#-Klasse übergeben und dann das Ergebnis, das auch ein Tupel ist, verbrauchen:

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

Im F #-Code können Sie dann ein strukturtupel als Parameter übergeben und das Ergebnis als strukturtupel verarbeiten.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Umrechnen zwischen verweistupeln und strukturtupeln

Da verweistupel und strukturtupel über eine völlig andere zugrunde liegende Darstellung verfügen, sind Sie nicht implizit konvertierbar.  Das heißt, dass Code wie der folgende nicht kompiliert wird:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

Sie müssen eine Muster Übereinstimmung für ein Tupel erstellen und das andere mit den Bestandteilen erstellen.  Zum Beispiel:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Kompilierte Form von verweistupeln

In diesem Abschnitt wird die Form von Tupeln erläutert, wenn Sie kompiliert werden.  Die hier aufgeführten Informationen sind nur erforderlich, wenn Sie .NET Framework 3,5 oder niedriger abzielen.

Tupel werden in Objekte von einem von mehreren generischen Typen kompiliert, die alle den Namen haben, die `System.Tuple` auf die Stelligkeit überladen werden, oder die Anzahl der Typparameter. Tupeltypen werden in dieser Form angezeigt, wenn Sie Sie aus einer anderen Sprache anzeigen, z. b. c# oder Visual Basic, oder wenn Sie ein Tool verwenden, das keine F #-Konstrukte kennt. Die `Tuple` Typen wurden in .NET Framework 4 eingeführt. Wenn Sie auf eine frühere Version von .NET Framework abzielen, verwendet der Compiler Versionen von `System.Tuple` aus der 2,0-Version der F #-Kernbibliothek. Die Typen in dieser Bibliothek werden nur für Anwendungen verwendet, die auf die Versionen 2,0, 3,0 und 3,5 von .NET Framework abzielen. Die Typweiterleitung wird verwendet, um die binäre Kompatibilität zwischen .NET Framework 2,0-und .NET Framework 4 F #-Komponenten sicherzustellen.

### <a name="compiled-form-of-struct-tuples"></a>Kompilierte Form von strukturtupeln

Strukturtupel (z. b. `struct (x, y)` ) unterscheiden sich grundlegend von verweistupeln.  Sie werden in den <xref:System.ValueTuple> Typ kompiliert, überlastet durch Stelligkeit oder die Anzahl der Typparameter.  Sie entsprechen [c# 7,0-Tupeln](../../csharp/language-reference/builtin-types/value-tuples.md) und [Visual Basic 2017-Tupeln](../../visual-basic/programming-guide/language-features/data-types/tuples.md)und interagieren bidirektional.

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
