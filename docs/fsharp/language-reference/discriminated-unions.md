---
title: Unterscheidungs-Union (F#)
description: Informationen zum Verwenden von F#-Unterscheidungs-Unions.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e2a011-c785-48c8-859f-79df7f3a0e29
ms.openlocfilehash: a374f521bcde7506bb3a9eebb627eaffcd8b94a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="discriminated-unions"></a>Unterscheidungs-Unions

Unterscheidungs-Unions bieten Unterstützung für Werte, bei denen es sich um einen Fall aus einer Anzahl verschiedener benannter Fälle handeln kann, mit jeweils potenziell unterschiedlichen Werten und Typen. Unterscheidungs-Unions sind für heterogene Daten nützlich: Daten, die besondere Fälle enthalten können, einschließlich gültiger und fehlerhafter Fälle, Daten, die sich im Typ von einer Instanz zur nächsten unterscheiden und als Alternative für kleine Objekthierarchien. Außerdem werden rekursive Unterscheidungs-Unions verwendet, um Strukturdatenstrukturen darzustellen.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
type type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a>Hinweise
Unterscheidungs-Unions ähneln Union-Typen in anderen Sprachen, aber es gibt Unterschiede. Wie bei einem Union-Typ in C++ oder einem Variantentyp in Visual Basic werden die im Wert gespeicherten Daten nicht korrigiert. Der Typ kann eine von mehreren unterschiedlichen Optionen sein. Im Gegensatz zu Unions in diesen anderen Sprachen, jedoch der möglichen Optionen wird jeweils ein *Fallbezeichner*. Die Fallbezeichner sind Namen für die verschiedenen möglichen Typen von Werten, die Objekte dieses Typs aufweisen können. Die Werte sind optional. Wenn keine Werte vorhanden sind, entspricht der Fall einem Enumerationsfall. Wenn Werte vorhanden sind, kann jeder Wert entweder ein einzelner Wert eines angegebenen Typs oder ein Tupel sein, der mehrere Felder gleicher oder unterschiedlicher Typen aggregiert. Ab F# 3.1 können Sie einem einzelnen Feld einen Namen geben, der Name ist jedoch optional, selbst wenn andere Felder im gleichen Fall benannt sind.

Betrachten Sie zum Beispiel die folgende Deklaration eines Formtyps:

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

Der vorangehende Code deklariert eine Unterscheidungs-Union-Form, die Werte der folgenden drei Fälle haben kann: Rechteck, Kreis und Prisma. Jeder Fall hat einen anderen Satz von Feldern. Der Rechteckfall hat zwei benannte Felder, beide vom Typ `float` mit den Namen Breite und Länge. Der Kreisfall hat nur ein benanntes Feld, nämlich Radius. Der prismafall hat drei Felder zwei welche (Breite und Höhe) sind benannte Felder. Unbenannte Felder werden als anonyme Felder bezeichnet.

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

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Die Fallbezeichner werden auch in Musterabgleichsausdrücken verwendet. In einem Mustervergleichsausdruck werden Bezeichner für die Werte bereitgestellt, die den einzelnen Fällen zugeordnet sind. Im folgenden Code ist `x` z. B. der Bezeichner, dem der Wert des `Some`-Falls des `option`-Typs zugeordnet ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

In Musterabgleichsausdrücken können Sie benannte Felder verwenden, um Unterscheidungs-Union-Übereinstimmungen anzugeben. Für den zuvor deklarierten Formtyp können Sie die benannten Felder verwenden, um die Werte von Feldern zu extrahieren, wie der folgende Code zeigt.

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

Normalerweise können die Fallbezeichner verwendet werden, ohne sie durch den Namen der Union zu qualifizieren. Wenn Sie soll, dass der Name immer mit dem Namen der Union qualifiziert werden, können Sie anwenden der [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) -Attribut auf die union-Typdefinition.

### <a name="unwrapping-discriminated-unions"></a>Entpacken Unterscheidungs-Unions

In f# Unterscheidungs-Unions werden häufig zum in der Domäne Modellierung Umschließen eines einzelnen Typs. Es ist einfach, um den zugrunde liegenden Wert über einen Musterabgleich sowie zu extrahieren. Sie müssen nicht für einen einzelnen Fall einen Vergleichsausdruck verwenden:
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

Dies wird im folgenden Beispiel veranschaulicht:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a>Struktur Unterscheidungs-Unions

Ab f# 4.1, können Sie auch Unterscheidungs-Unions als Strukturen darstellen.  Dies erfolgt mit der `[<Struct>]` Attribut.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of string
    | Case2 of int
    | Case3 of double
```

Da diese sind Werttypen und nicht auf Typen verweisen, sind zusätzliche Überlegungen, die im Vergleich mit dem Verweis Unterscheidungs-Unions:

1. Sie werden als Werttypen kopiert und Werttypsemantik haben.
2. Eine rekursive Definition können keine mit einer multicase Discriminated-Union-Struktur.
3. Sie müssen eine multicase Struktur Discriminated Union Groß-/Kleinschreibung eindeutige Namen angeben.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Verwenden von Unterscheidungs-Unions statt Objekthierarchien
Sie können oft eine Unterscheidungs-Union als einfachere Alternative zu einer kleinen Objekthierarchie verwenden. Die folgende Unterscheidungs-Union könnte z. B. statt einer `Shape`-Basisklasse verwendet werden, die abgeleitete Typen für Kreis, Quadrat usw. aufweist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

Statt einer virtuellen Methode zur Berechnung eines Bereich oder eines Umkreises, wie sie in einer objektorientierten Implementierung verwendet werden würde, können Sie mithilfe des Mustervergleichs die entsprechenden Formeln branchen, um die Mengen zu berechnen. Im folgenden Beispiel werden andere Formeln verwendet, um den Bereich abhängig von der Form zu berechnen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

Die Ausgabe lautet wie folgt:

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Verwenden von Unterscheidungs-Unions für Baumdatenstrukturen
Unterscheidungs-Unions können rekursiv sein, d. h., dass die Union selbst im Typ eines Falles oder mehrerer Fälle enthalten sein kann. Rekursive Unterscheidungs-Unions können verwendet werden, um Strukturen zur Gestaltung von Ausdrücken in Programmiersprachen zu erstellen. Im folgenden Code wird eine rekursive Unterscheidungs-Union verwendet, um eine binäre Strukturdatenstruktur zu erstellen. Die Union besteht aus zwei Fällen: `Node`, der ein Knoten mit einem ganzzahligen Wert und linken und rechten Teilstrukturen ist, und `Tip`, der die Struktur beendet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

Im vorherigen Code verfügt `resultSumTree` über den Wert 10. Die folgende Abbildung zeigt die Struktur für `myTree` an.

![Struktur für myTree](../media/TreeStructureDiagram.png)

Unterscheidungs-Unions funktionieren gut, wenn die Knoten in der Struktur heterogen sind. Im folgenden Code stellt der `Expression`-Typ die abstrakte Syntaxstruktur eines Ausdrucks in einer einfachen Programmiersprache dar, die Addition und Multiplikation von Zahlen und Variablen unterstützt. Einige der Union-Fälle sind nicht rekursiv und stellen entweder Zahlen (`Number`) oder Variablen (`Variable`) dar. Andere Fälle sind rekursiv und stellen Operationen (`Add` und `Multiply`) dar, wobei die Operanden auch Ausdrücke sind. Die `Evaluate`-Funktion verwendet einen Vergleichsausdruck, um den Syntaxbaum rekursiv zu verarbeiten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Wenn dieser Code ausgeführt wird, beträgt der Wert von `result` 5.

## <a name="common-attributes"></a>Allgemeine Attribute

Die folgenden Attribute werden häufig im Unterscheidungs-Unions angezeigt:

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]`(F# 4.1 und höher)

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
