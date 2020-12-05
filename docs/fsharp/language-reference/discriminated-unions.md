---
title: Unterscheidungs-Unions
description: 'Erfahren Sie mehr über die Verwendung von F #-diskriminierten Unions.'
ms.date: 08/15/2020
ms.openlocfilehash: f90ac2c2ea21182cf5fd3657d2ada00a763139fe
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740236"
---
# <a name="discriminated-unions"></a>Unterscheidungs-Unions

Unterscheidungs-Unions bieten Unterstützung für Werte, bei denen es sich um einen Fall aus einer Anzahl verschiedener benannter Fälle handeln kann, mit jeweils potenziell unterschiedlichen Werten und Typen. Unterscheidungs-Unions sind für heterogene Daten nützlich: Daten, die besondere Fälle enthalten können, einschließlich gültiger und fehlerhafter Fälle, Daten, die sich im Typ von einer Instanz zur nächsten unterscheiden und als Alternative für kleine Objekthierarchien. Außerdem werden rekursive Unterscheidungs-Unions verwendet, um Baumstrukturdatenstrukturen darzustellen.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>Bemerkungen

Unterscheidungs-Unions ähneln Union-Typen in anderen Sprachen, aber es gibt Unterschiede. Wie bei einem Union-Typ in C++ oder einem Variantentyp in Visual Basic werden die im Wert gespeicherten Daten nicht korrigiert. Der Typ kann einer von mehreren unterschiedlichen Optionen sein. Im Gegensatz zu Unions in diesen anderen Sprachen erhält jede der möglichen Optionen einen *Fall Bezeichner*. Die Fallbezeichner sind Namen für die verschiedenen möglichen Typen von Werten, die Objekte dieses Typs aufweisen können. Die Werte sind optional. Wenn keine Werte vorhanden sind, entspricht der Fall einem Enumerationsfall. Wenn Werte vorhanden sind, kann jeder Wert entweder ein einzelner Wert eines angegebenen Typs oder ein Tupel sein, das mehrere Felder gleicher oder unterschiedlicher Typen aggregiert. Sie können einem einzelnen Feld einen Namen einräumen, aber der Name ist optional, auch wenn andere Felder im gleichen Fall benannt werden.

Der Zugriff auf diskriminierte Unions ist standardmäßig `public` .

Betrachten Sie zum Beispiel die folgende Deklaration eines Formtyps:

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

Der vorangehende Code deklariert eine Unterscheidungs-Union-Form, die Werte der folgenden drei Fälle haben kann: Rechteck, Kreis und Prisma. Jeder Fall hat einen anderen Satz von Feldern. Der Rechteckfall hat zwei benannte Felder, beide vom Typ `float` mit den Namen Breite und Länge. Der Kreisfall hat nur ein benanntes Feld, nämlich Radius. Der Prism-Fall verfügt über drei Felder, von denen zwei (Breite und Höhe) benannte Felder sind. Unbenannte Felder werden als anonyme Felder bezeichnet.

Sie erstellen Objekte, indem Sie Werte für die benannten und anonymen Felder bereitstellen, wie in den folgenden Beispielen dargestellt.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Dieser Code zeigt, dass Sie entweder die benannten Felder in der Initialisierung verwenden können, oder Sie können die Reihenfolge der Felder in der Deklaration erstellen und nur die Werte für jedes Feld bereitstellen. Der Konstruktoraufruf für `rect` im vorherigen Code verwendet benannte Felder, der Konstruktoraufruf für `circ` hingegen die Reihenfolge. Sie können die angeordneten Felder und benannten Felder wie in der Konstruktion von `prism` kombinieren.

Der `option`-Typ ist eine einfache Unterscheidungs-Union in der F#-Kernbibliothek. Der `option`-Typ wird folgendermaßen deklariert.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

Der vorherige Code gibt an, dass der `Option`-Typ eine Unterscheidungs-Union mit den beiden Fällen `Some` und `None` ist. Der `Some`-Fall verfügt über einen zugeordneten Wert, der aus einem anonymen Feld besteht, dessen Typ durch den Typparameter `'a` dargestellt wird. Der `None`-Fall verfügt über keinen zugeordneten Wert. Der `option`-Typ gibt also einen generischen Typ an, der entweder einen Wert eines Typs oder keinen Wert aufweist. Der `Option`-Typ weist außerdem ein kleingeschriebenes Typalias auf, `option`, das häufig verwendet wird.

Die Fallbezeichner können für den Unterscheidungs-Union-Typ als Konstruktoren verwendet werden. Der folgende Code wird z. B. verwendet, um Werte des `option`-Typs zu erstellen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Die Fallbezeichner werden auch in Musterabgleichsausdrücken verwendet. In einem Musterabgleichsausdruck werden Bezeichner für die Werte bereitgestellt, die den einzelnen Fällen zugeordnet sind. Im folgenden Code ist `x` z. B. der Bezeichner, dem der Wert des `Some`-Falls des `option`-Typs zugeordnet ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

in Mustervergleichsausdrücken können Sie benannte Felder verwenden, um Unterscheidungs-Union-Übereinstimmungen anzugeben. Für den zuvor deklarierten Formtyp können Sie die benannten Felder verwenden, um die Werte von Feldern zu extrahieren, wie der folgende Code zeigt.

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

Normalerweise können die Fallbezeichner verwendet werden, ohne sie durch den Namen der Union zu qualifizieren. Wenn Sie möchten, dass der Name immer mit dem Namen der Union qualifiziert wird, können Sie das Attribut "Requirements [qualifiedaccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) " auf die Union-Typdefinition anwenden.

### <a name="unwrapping-discriminated-unions"></a>Entpacken von Unterscheidungs-Unions

In F # werden diskriminierte Unions häufig in der Domänen Modellierung zum Umwickeln eines einzelnen Typs verwendet. Der zugrunde liegende Wert kann auch einfach über den Musterabgleich extrahiert werden. Es ist nicht erforderlich, einen Vergleichs Ausdruck für einen einzelnen Fall zu verwenden:

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

Dies wird im folgenden Beispiel veranschaulicht:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

Muster Vergleiche sind auch direkt in Funktionsparametern zulässig, sodass Sie einen einzelnen Fall in einen einzelnen Fall entpacken können:

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>Struktur Unterscheidungs-Unions

Sie können auch Unterscheidungs-Unions als Strukturen darstellen.  Dies erfolgt mit dem- `[<Struct>]` Attribut.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Da es sich hierbei um Werttypen und nicht um Verweis Typen handelt, gibt es im Vergleich zu Verweises diskriminierten Unions weitere Aspekte:

1. Sie werden als Werttypen kopiert und weisen die Werttyp Semantik auf.
2. Es ist nicht möglich, eine rekursive Typdefinition mit einer Unterscheidungs-Union mit mehreren Fällen zu verwenden.
3. Sie müssen eindeutige Case-Namen für eine mehrteilige Struktur mit Unterscheidungs Unterscheidungs-Union angeben.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Verwenden von Unterscheidungs-Unions statt Objekthierarchien

Sie können oft eine Unterscheidungs-Union als einfachere Alternative zu einer kleinen Objekthierarchie verwenden. Die folgende Unterscheidungs-Union könnte z. B. statt einer `Shape`-Basisklasse verwendet werden, die abgeleitete Typen für Kreis, Quadrat usw. aufweist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

Statt einer virtuellen Methode zur Berechnung eines Bereich oder eines Umkreises, wie sie in einer objektorientierten Implementierung verwendet werden würde, können Sie mithilfe des Mustervergleichs die entsprechenden Formeln aufteilen, um die Mengen zu berechnen. Im folgenden Beispiel werden andere Formeln verwendet, um den Bereich abhängig von der Form zu berechnen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

Die Ausgabe lautet wie folgt:

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Verwenden von Unterscheidungs-Unions für Datenstrukturen

Unterscheidungs-Unions können rekursiv sein, d. h., dass die Union selbst im Typ eines Falles oder mehrerer Fälle enthalten sein kann. Rekursive Unterscheidungs-Unions können verwendet werden, um Strukturen zur Gestaltung von Ausdrücken in Programmiersprachen zu erstellen. Im folgenden Code wird eine rekursive Unterscheidungs-Union verwendet, um eine binäre Strukturdatenstruktur zu erstellen. Die Union besteht aus zwei Fällen: `Node`, der ein Knoten mit einem ganzzahligen Wert und linken und rechten Unterstrukturen ist, und `Tip`, der die Struktur beendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

Im vorherigen Code verfügt `resultSumTree` über den Wert 10. Die folgende Abbildung zeigt die Struktur für `myTree` an.

![Diagramm, das die Baumstruktur für mytree anzeigt.](../media/discriminated-unions/tree-structure-mytree.png)

Unterscheidungs-Unions funktionieren gut, wenn die Knoten in der Struktur heterogen sind. Im folgenden Code stellt der `Expression`-Typ die abstrakte Syntaxstruktur eines Ausdrucks in einer einfachen Programmiersprache dar, die Addition und Multiplikation von Zahlen und Variablen unterstützt. Einige der Union-Fälle sind nicht rekursiv und stellen entweder Zahlen (`Number`) oder Variablen (`Variable`) dar. Andere Fälle sind rekursiv und stellen Operationen (`Add` und `Multiply`) dar, wobei die Operanden auch Ausdrücke sind. Die `Evaluate`-Funktion verwendet einen Vergleichsausdruck, um die Syntaxstruktur rekursiv zu verarbeiten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Wenn dieser Code ausgeführt wird, beträgt der Wert von `result` 5.

## <a name="members"></a>Member

Es ist möglich, Elemente für Unterscheidungs-Unions zu definieren. Im folgenden Beispiel wird gezeigt, wie Sie eine-Eigenschaft definieren und eine-Schnittstelle implementieren:

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn $"Circle with radius %f{r}"
            | EquilateralTriangle s -> printfn $"Equilateral Triangle of side %f{s}"
            | Square s -> printfn $"Square with side %f{s}"
            | Rectangle(l, w) -> printfn $"Rectangle with length %f{l} and width %f{w}"
```

## <a name="common-attributes"></a>Allgemeine Attribute

Die folgenden Attribute werden häufig in Unterscheidungs-Unions angezeigt:

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
