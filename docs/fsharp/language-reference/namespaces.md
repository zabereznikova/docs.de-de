---
title: Namespaces (F#)
description: Erfahren Sie, wie ein Namespace F#-Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen für die Gruppierung von Programmelementen anfügen kann.
ms.date: 04/24/2017
ms.openlocfilehash: 769a1241f76ac32d3a6a80bd637078493119bb3c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881888"
---
# <a name="namespaces"></a>Namespaces

Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.

## <a name="syntax"></a>Syntax

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>Hinweise

Wenn Sie Code in einem Namespace einfügen möchten, muss die erste Deklaration in der Datei den Namespace deklarieren. Der Inhalt der gesamten Datei werden dann Teil des Namespace.

Namespaces können nicht direkt als Werte und Funktionen enthalten. Stattdessen Werte und Funktionen in Modulen enthalten sein müssen, und Module in Namespaces enthalten sind. Namespaces kann es sich um Typen, Module enthalten.

Namespaces können explizit mit dem Schlüsselwort "Namespace" oder implizit deklariert werden, wenn ein Modul zu deklarieren. Um einen Namespace explizit deklarieren, verwenden Sie das Schlüsselwort "Namespace" gefolgt vom Namespacenamen ein. Das folgende Beispiel zeigt eine Codedatei, die einen Namespace Widgets mit einem Typ und einem Modul in diesem Namespace deklariert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Wenn der gesamte Inhalt der Datei in einem Modul sind, Sie können auch Namespaces deklarieren implizit mithilfe der `module` -Schlüsselwort und den neuen Namespacenamen in der vollqualifizierte Modulname bereitstellen. Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Moduldeklaration. In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Wenn mehr als einem Modul in der gleichen Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie die Deklarationen der lokalen Modul verwenden. Bei Verwendung von lokalen Moduldeklarationen können nicht Sie den vollqualifizierten Namespace in den Moduldeklarationen verwenden. Der folgende Code zeigt eine Datei, die eine Namespacedeklaration und zwei lokale Moduldeklarationen verfügt. In diesem Fall sind die Module direkt im Namespace enthalten. Es gibt keine implizit erstelltes Modul, das den gleichen Namen wie die Datei hat. Jeder andere code in die Datei, z. B. eine `do` binden, ist im Namespace, jedoch nicht in der inneren Module, daher Sie die Modulmember qualifizieren müssen `widgetFunction` mit den Namen des Moduls.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

Die Ausgabe dieses Beispiels ist wie folgt aus.

```fsharp
Module1 10 20
Module2 5 6
```

Weitere Informationen finden Sie unter [Module](modules.md).

## <a name="nested-namespaces"></a>Geschachtelte Namespaces

Wenn Sie einen geschachtelten Namespace erstellen, müssen Sie sie vollständig qualifizieren. Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene. Einzug wird in Namespacedeklarationen ignoriert.

Das folgende Beispiel zeigt, wie Sie einen geschachtelten Namespace zu deklarieren.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Namespaces in Dateien und Assemblys

Namespaces können mehrere Dateien in einem einzelnen Projekt oder die Kompilierung umfassen. Der Begriff *Namespacefragment* beschreibt den Teil eines Namespace, die in einer Datei enthalten ist. Namespaces können auch mehrere Assemblys umfassen. Z. B. die `System` Namespace enthält die gesamte .NET Framework, die viele Assemblys umfasst, und viele geschachtelte Namespaces enthält.

## <a name="global-namespace"></a>Globaler Namespace

Sie verwenden den vordefinierten Namespace `global` setzen Sie die Namen in den obersten Namespace von .NET.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

Sie können auch globale verwenden, z. B. den Namespace der obersten Ebene .NET zu verweisen, um Namenskonflikte mit anderen Namespaces zu vermeiden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Rekursive-namespaces

F# 4.1 führt das Konzept von Namespaces, die für alle enthaltenen Code gegenseitig rekursiver zu ermöglichen.  Dies erfolgt über `namespace rec`.  Verwenden von `namespace rec` können einige Probleme, nicht mehr zum Schreiben von Code für sich gegenseitig referenzielle Typen und Module verringern.  Im folgenden finden ein Beispiel hierfür:

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

Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide sich aufeinander beziehen.  Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch sich aufeinander beziehen.  Dies ist nicht möglich, die in f# zu express, wenn Sie entfernt die `rec` -Schlüsselwort aus der `MutualReferences` Namespace.

Dieses Feature ist auch verfügbar für die obersten Ebene [Module](modules.md) in f# 4.1 oder höher.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Module](modules.md)
- [F#-RFC-FS-1009 – lassen Sie sich gegenseitig referenzielle Typen und Module über größere Bereiche in Dateien](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
