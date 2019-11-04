---
title: Namespaces
description: Erfahren Sie, F# wie ein Namespace Ihnen ermöglicht, Code in Bereichen verwandter Funktionalität zu organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen können.
ms.date: 12/08/2018
ms.openlocfilehash: a55da1592b04c64576b4c66de61b5ca137289a6f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425046"
---
# <a name="namespaces"></a>Namespaces

Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von F# Programmelementen anfügen können. Namespaces sind in der Regel Elemente der obersten F# Ebene in Dateien.

## <a name="syntax"></a>Syntax

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a>Hinweise

Wenn Sie Code in einem Namespace platzieren möchten, muss die erste Deklaration in der Datei den Namespace deklarieren. Der Inhalt der gesamten Datei wird dann Teil des Namespaces, sofern keine weitere Namespace-Deklaration in der Datei vorhanden ist. Wenn dies der Fall ist, wird der gesamte Code bis zur nächsten Namespace Deklaration als innerhalb des ersten Namespaces betrachtet.

Namespaces können nicht direkt Werte und Funktionen enthalten. Stattdessen müssen Werte und Funktionen in Module enthalten sein, und Module sind in Namespaces enthalten. Namespaces können Typen, Module enthalten.

XML-Dokument Kommentare können über einem Namespace deklariert werden, werden jedoch ignoriert. Compilerdirektiven können auch über einem Namespace deklariert werden.

Namespaces können explizit mit dem Namespace-Schlüsselwort oder implizit beim Deklarieren eines Moduls deklariert werden. Um einen Namespace explizit zu deklarieren, verwenden Sie das Namespace-Schlüsselwort, gefolgt vom Namespace Namen. Das folgende Beispiel zeigt eine Codedatei, die einen Namespace `Widgets` mit einem Typ und einem Modul deklariert, das in diesem Namespace enthalten ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Wenn sich der gesamte Inhalt der Datei in einem Modul befindet, können Sie Namespaces auch implizit deklarieren, indem Sie das `module`-Schlüsselwort verwenden und den neuen Namespace Namen im voll qualifizierten Modulnamen angeben. Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Modul Deklaration. In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

Wenn mehr als ein Modul in derselben Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie lokale Modul Deklarationen verwenden. Wenn Sie lokale Modul Deklarationen verwenden, kann der qualifizierte Namespace in den Modul Deklarationen nicht verwendet werden. Der folgende Code zeigt eine Datei mit einer Namespace Deklaration und zwei Deklarationen von lokalen Modulen. In diesem Fall sind die Module direkt im-Namespace enthalten. Es ist kein implizit erstelltes Modul vorhanden, das denselben Namen wie die Datei hat. Jeder andere Code in der Datei, z. b. eine `do` Bindung, befindet sich im-Namespace, jedoch nicht in den inneren Modulen. Daher müssen Sie das Modulmember `widgetFunction` mithilfe des Modul namens qualifizieren.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

Die Ausgabe dieses Beispiels lautet wie folgt.

```fsharp
Module1 10 20
Module2 5 6
```

Weitere Informationen finden Sie unter [Module](modules.md).

## <a name="nested-namespaces"></a>Schsted Namespaces

Wenn Sie einen in einem netsted Namespace erstellten Namespace erstellen, müssen Sie ihn vollständig qualifizieren. Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene. Der Einzug wird in Namespace Deklarationen ignoriert.

Im folgenden Beispiel wird gezeigt, wie ein schsted Namespace deklariert wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Namespaces in Dateien und Assemblys

Namespaces können mehrere Dateien in einem einzelnen Projekt oder einer Kompilierung umfassen. Der Begriff *Namespace Fragment* beschreibt den Teil eines Namespace, der in einer Datei enthalten ist. Namespaces können sich auch über mehrere Assemblys erstrecken. Der `System`-Namespace enthält z. b. den gesamten .NET Framework, der sich über viele Assemblys erstreckt und viele eingefügte Namespaces enthält.

## <a name="global-namespace"></a>Globaler Namespace

Sie verwenden den vordefinierten Namespace `global`, um Namen in den .NET-Namespace auf oberster Ebene zu platzieren.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

Sie können auch global verwenden, um auf den .NET-Namespace der obersten Ebene zu verweisen, z. b. um Namenskonflikte mit anderen Namespaces aufzulösen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Rekursive Namespaces

Namespaces können auch als rekursiv deklariert werden, damit der gesamte enthaltene Code gegenseitig rekursiv ist.  Dies erfolgt über `namespace rec`. Die Verwendung von `namespace rec` kann einige Probleme verringern, die sich nicht gegenseitig referenziellen Code zwischen Typen und Modulen schreiben können. Im folgenden finden Sie ein Beispiel hierfür:

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up ->
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die-Klasse `Banana` beide aufeinander verweisen.  Außerdem verweisen das Modul `BananaHelpers` und die Klasse `Banana` auch aufeinander. Dies wäre nicht möglich, F# Wenn Sie das `rec`-Schlüsselwort aus dem `MutualReferences`-Namespace entfernt haben.

Diese Funktion ist auch für [Module](modules.md)der obersten Ebene verfügbar.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Module](modules.md)
- [F#RFC FS-1009-zulassen von sich gegenseitig referenziellen Typen und Modulen über größere Bereiche innerhalb von Dateien](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
