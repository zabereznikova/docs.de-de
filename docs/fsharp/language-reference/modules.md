---
title: Module (F#)
description: Erfahren Sie, wie ein f#-Modul eine Gruppierung von f#-Code, z. B. Werte, Typen und Funktionswerte in einem f#-Programm ist.
ms.date: 04/24/2017
ms.openlocfilehash: b503a78abed34cbb56a7a1ceaba61f851a125831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="modules"></a>Module

Im Rahmen der Programmiersprache f# ein *Modul* ist eine Gruppierung von f#-Code, z. B. Werte, Typen und Funktionswerte in einem f#-Programm. Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.

## <a name="syntax"></a>Syntax

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>Hinweise
Ein f#-Modul ist eine Gruppierung von F#-Code-Konstrukte wie Typen, Werte Funktionswerte und Code in `do` Bindungen. Es wird als eine common Language Runtime (CLR)-Klasse implementiert, die nur statische Member verfügt. Es gibt zwei Arten von Moduldeklarationen, je nachdem, ob die gesamte Datei im Modul enthalten ist: eine Moduldeklaration der obersten Ebene und eine lokale Moduldeklaration. Eine Moduldeklaration der obersten Ebene enthält die gesamte Datei im Modul an. Eine Moduldeklaration der obersten Ebene kann nur als die erste Deklaration in einer Datei angezeigt werden.

In der Syntax für die Moduldeklaration der obersten Ebene, das optionale *qualifiziert Namespace* ist die Abfolge von geschachtelten Namespace-Namen, die das Modul enthält. Die vollqualifizierten Namespace muss nicht zuvor deklariert werden.

Sie müssen keinen Einzug Deklarationen in einem Modul der obersten Ebene. Sie müssen alle Deklarationen in den lokalen Modulen Einzug. In einer lokalen Moduldeklaration sind nur die Deklarationen, die unter diesem Moduldeklaration eingerückt sind Teil des Moduls.

Wenn eine Codedatei nicht mit einer Moduldeklaration der obersten Ebene oder eine Namespacedeklaration beginnt, wird der gesamte Inhalt der Datei, einschließlich lokaler Module, Teil eines implizit erstellten Moduls der obersten Ebene, die den gleichen Namen wie die Datei ohne Erweiterung hat, mit dem ersten Buchstaben in Großbuchstaben konvertiert wurden. Betrachten Sie beispielsweise die folgende Datei aus.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

Diese Datei würde kompiliert werden, als wäre sie auf diese Weise geschrieben wurden:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

Wenn Sie mehrere Module in einer Datei haben, müssen Sie eine lokale Moduldeklaration für jedes Modul verwenden. Wenn ein einschließender Namespace deklariert ist, sind diese Module Teil des einschließenden Namespace an. Wenn ein einschließender Namespace nicht deklariert ist, werden die Module Teil des implizit erstellten auf oberster Ebene Moduls an. Das folgende Codebeispiel zeigt eine Codedatei, die mehrere Module enthält. Der Compiler erstellt implizit ein Modul der obersten Ebene mit dem Namen `Multiplemodules`, und `MyModule1` und `MyModule2` in diesem Modul der obersten Ebene geschachtelt sind.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

Wenn Sie mehrere Dateien in einem Projekt oder in einer einzigen Kompilierung haben oder wenn Sie eine Bibliothek erstellen, müssen Sie eine Namespacedeklaration oder Moduldeklaration am Anfang der Datei einschließen. F#-Compiler bestimmt einen Modulnamen nur implizit, wenn nur eine Datei im Projekt oder die Kompilierung über die Befehlszeile vorhanden ist, und Sie eine Anwendung erstellen.

Die *Zugriffsmodifizierer* kann eines der folgenden sein: `public`, `private`, `internal`. Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md). Der Standardwert ist „öffentlich“.


## <a name="referencing-code-in-modules"></a>Verweisen auf Code in Module
Wenn Sie Funktionen, Typen und Werte aus einem anderen Modul verweisen, müssen Sie einen qualifizierten Namen verwenden oder öffnen Sie das Modul. Wenn Sie einen qualifizierten Namen verwenden, müssen Sie angeben, die Namespaces, das Modul und der Bezeichner für das gewünschte Programmelement. Sie trennen, jeden Teil des vollqualifizierten Pfads mit einem Punkt (.), wie folgt.

`Namespace1.Namespace2.ModuleName.Identifier`

Öffnen Sie das Modul und mindestens eine der Namespaces auf den Code zu vereinfachen. Weitere Informationen zum Öffnen von Namespaces und Modulen finden Sie unter [Importdeklarationen: das `open` Schlüsselwort](import-declarations-the-open-keyword.md).

Das folgende Codebeispiel zeigt ein auf oberster Ebene Modul, das den Code für die bis zum Ende der Datei enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

Um diesen Code aus einer anderen Datei im selben Projekt verwenden möchten, verwenden Sie qualifizierte Namen, oder Sie öffnen das Modul vor der Verwendung der Funktionen, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Geschachtelte Module
Module können geschachtelt werden. Innere Module müssen eingezogen werden, so weit wie äußere Moduldeklarationen, um anzugeben, dass sie die inneren Module keine neuen Module sind. Vergleichen Sie beispielsweise die folgenden zwei Beispiele. Modul `Z` ist ein inneres Modul in den folgenden Code.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

Aber Modul `Z` ein gleichgeordnetes Element Modul `Y` in den folgenden Code.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
Modul `Z` ist auch ein gleichgeordnetes Element-Modul in den folgenden Code, da sie nicht so weit wie andere Deklarationen in Modul eingezogen ist `Y`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
Schließlich, wenn das äußere Modul verfügt über keine Deklarationen und unmittelbar, von einem anderen Moduldeklaration gefolgt wird, neue Moduldeklaration wird davon ausgegangen, dass ein inneres Modul, aber der Compiler warnt Sie, wenn die zweite Moduldefinition hin als nicht eingezogen wird die erste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
Um die Warnung zu vermeiden, ziehen Sie das innere Modul ein.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
Wenn alle Code in einer Datei in einem einzelnen äußeren Modul sein soll, und inneren Module werden sollen, das äußere Modul erfordert nicht das Gleichheitszeichen und die Deklarationen, einschließlich möglichen Deklarationen innerer Module, die im äußeren Modul geleitet werden müssen nicht mit Einzug dargestellt werden. Deklarationen innerhalb der inneren Moduldeklarationen eingezogen werden müssen. Der folgende Code zeigt diesen Fall.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Rekursive Module

F#-4.1 führt das Konzept der Module, die für alle enthaltenen Code wechselseitig rekursive sein können.  Dies geschieht über `module rec`.  Verwenden von `module rec` verringern, können einige sorgen, nicht aufeinander Code für Typen und Module schreiben können.  Im folgenden finden ein Beispiel dafür:

```fsharp
module rec RecursiveModule =
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

    module private BananaHelpers =
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

Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide aufeinander verweisen.  Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch miteinander verweisen.  Dies ist nicht möglich, express in F# erläutert werden, wenn Sie entfernt die `rec` -Schlüsselwort aus der `RecursiveModule` Modul.

Diese Funktion ist außerdem möglich [Namespaces](namespaces.md) f# 4.1.

## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)
[Namespaces](namespaces.md)
[f# RFC FS 1009 - aufeinander Typen und Module über größere Bereiche innerhalb von Dateien zulassen](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
