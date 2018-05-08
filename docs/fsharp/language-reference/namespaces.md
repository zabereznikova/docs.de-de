---
title: Namespaces (F#)
description: Erfahren Sie, wie ein f#-datennamespace Sie Code in Funktionsbereichen organisieren, indem Sie einen Namen für die Gruppierung von Programmelemente anfügen kann.
ms.date: 04/24/2017
ms.openlocfilehash: 81d1648dbdc111984ddeb77d11b2bd81cbca57cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="namespaces"></a>Namespaces

Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.


## <a name="syntax"></a>Syntax

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>Hinweise
Wenn Code in einem Namespace platziert werden sollen, muss die erste Deklaration in der Datei den Namespace deklarieren. Der Inhalt der gesamten Datei wird dann Teil des Namespace.

Namespaces kann nicht direkt, Werte und Funktionen enthalten. Stattdessen Werte und Funktionen in Modulen enthalten sein müssen, und Module in Namespaces enthalten sind. Namespaces können Typen, Module enthalten.

Namespaces können explizit mit dem namespaceschlüsselwort oder implizit deklariert werden, wenn ein Modul deklariert. Um einen Namespace explizit zu deklarieren, verwenden Sie die Namespace-Schlüsselwort, gefolgt vom Namespacenamen. Das folgende Beispiel zeigt eine Codedatei, die einen Namespace mit dem Typ und ein Modul, das in diesem Namespace enthaltenen Widgets deklariert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Wenn der gesamte Inhalt der Datei in einem Modul sind, Sie können auch Namespaces deklarieren implizit mithilfe der `module` -Schlüsselwort und den neuen Namespacenamen in den vollständig qualifizierten Modulnamen bereitstellen. Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Moduldeklaration. In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Wenn mehr als einem Modul in der gleichen Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie lokale Moduldeklarationen verwenden. Bei Verwendung von lokalen Moduldeklarationen kann nicht die vollqualifizierten Namespace in den Moduldeklarationen verwenden werden. Der folgende Code zeigt eine Datei, die eine Namespacedeklaration und zwei lokale Moduldeklarationen verfügt. In diesem Fall sind die Module direkt im Namespace enthalten. Es ist kein implizit erstelltes Modul, das den gleichen Namen wie die Datei verfügt. Alle anderen code in die Datei, z. B. eine `do` binden, ist im Namespace, jedoch nicht in den inneren Modulen, daher Sie das Modul-Element zu qualifizieren müssen `widgetFunction` mit den Namen des Moduls.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

Die Ausgabe dieses Beispiels lautet wie folgt.

```fsharp
Module1 10 20
Module2 5 6
```

Weitere Informationen finden Sie unter [Module](modules.md).

## <a name="nested-namespaces"></a>Geschachtelte Namespaces
Wenn Sie einen geschachtelten Namespace erstellen, müssen Sie vollständig qualifizieren. Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene. Einzug wird in Namespacedeklarationen ignoriert.

Im folgende Beispiel wird das Deklarieren eines geschachtelten Namespaces veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Namespaces in Dateien und Assemblys
Namespaces können mehrere Dateien in einem einzelnen Projekt oder die Kompilierung umfassen. Der Begriff *Namespacefragment* beschreibt den Teil eines Namespaces, die in einer Datei enthalten ist. Namespaces können auch mehrere Assemblys umfassen. Z. B. die `System` Namespace enthält die gesamte .NET Framework, die viele Assemblys umfasst und zahlreiche geschachtelte Namespaces enthält.


## <a name="global-namespace"></a>Globaler Namespace
Sie verwenden den vordefinierten Namespace `global` Namen in den Namespace der obersten Ebene .NET aufgenommen werden sollen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

Sie können auch globale verwenden, z. B. den Namespace der obersten Ebene .NET verweisen, um Namenskonflikte mit anderen Namespaces zu vermeiden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Rekursive namespaces

F#-4.1 führt das Konzept von Namespaces, die für alle enthaltenen Code wechselseitig rekursive werden zu ermöglichen.  Dies geschieht über `namespace rec`.  Verwenden von `namespace rec` verringern, können einige sorgen, nicht aufeinander Code für Typen und Module schreiben können.  Im folgenden finden ein Beispiel dafür:

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
    let peel (b : Banana) =
        let flip banana =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides banana =
            for side in banana.Sides do
                if side = Unpeeled then
                    side <- Peeled

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide aufeinander verweisen.  Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch miteinander verweisen.  Dies ist nicht möglich, express in F# erläutert werden, wenn Sie entfernt die `rec` -Schlüsselwort aus der `MutualReferences` Namespace.

Diese Funktion steht auch für die obersten Ebene [Module](modules.md) in f# 4.1 oder höher.

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Module](modules.md)

[F#-RFC-EA-1009 - aufeinander Typen und Module über größere Bereiche innerhalb von Dateien zulassen](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
