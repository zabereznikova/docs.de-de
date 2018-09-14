---
title: Module (F#)
description: Erfahren Sie, wie eine f#-Modul eine Gruppierung von F#-Code, z. B. Werte, Typen und Funktionswerte in einem F#-Programm.
ms.date: 04/24/2017
ms.openlocfilehash: fb0aa1d508d1141933b4fbdf10633f67ed078dc7
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45528525"
---
# <a name="modules"></a>Module

Im Rahmen der Sprache f# eine *Modul* ist eine Gruppierung von F#-Code, z. B. Werte, Typen und Funktionswerte in einem F#-Programm. Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.

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

Eine f#-Modul ist eine Gruppierung von F#-Code-Konstrukte wie Typen, Werte, Werte von Funktionen und -Code in `do` Bindungen. Es wird als eine common Language Runtime (CLR)-Klasse implementiert, die nur statische Member verfügt. Es gibt zwei Arten von Moduldeklarationen, je nachdem, ob die gesamte Datei im Modul enthalten ist: eine Moduldeklaration der obersten Ebene und einem lokalen Modul-Deklaration. Eine Deklaration Modul auf oberster Ebene enthält die gesamte Datei im Modul an. Eine Moduldeklaration auf oberster Ebene kann nur als die erste Deklaration in einer Datei angezeigt werden.

In der Syntax für die Deklaration Modul auf oberster Ebene, die den optionalen *qualifizierter Namespace* ist die Sequenz der geschachtelten Namespace-Namen, die das Modul enthält. Die vollqualifizierten Namespace muss nicht zuvor deklariert werden.

Sie müssen keinen Deklarationen in einem Modul auf oberster Ebene eingezogen. Sie müssen alle Deklarationen in den lokalen Modulen einziehen. In der Deklaration einer lokalen Modul sind nur Deklarationen, die unter diesem Moduldeklaration eingezogen werden Teil des Moduls.

Wenn Sie eine Codedatei mit einer Deklaration Modul auf oberster Ebene oder eine Namespacedeklaration nicht startet, wird der gesamte Inhalt der Datei, einschließlich lokalen Module, Teil einer implizit erstellten Modul auf oberster Ebene, die den gleichen Namen wie die Datei ohne Erweiterung hat, mit dem ersten Buchstaben in Großbuchstaben konvertiert wurden. Betrachten Sie beispielsweise die folgende Datei aus.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

Diese Datei würde kompiliert werden, als ob sie auf diese Weise geschrieben wurden:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

Wenn Sie mehrere Module in einer Datei haben, müssen Sie eine lokale Moduldeklaration für jedes Modul verwenden. Wenn ein einschließenden Namespace deklariert wird, sind diese Module Teil des einschließenden Namespace an. Wenn Sie ein Namespace des einschließender nicht deklariert ist, werden die Module des Moduls implizit erstellten auf oberster Ebene. Das folgende Codebeispiel zeigt eine Codedatei, die mehrere Module enthält. Erstellt der Compiler implizit ein Modul auf oberster Ebene mit dem Namen `Multiplemodules`, und `MyModule1` und `MyModule2` in diesem Modul auf oberster Ebene geschachtelt sind.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

Wenn Sie mehrere Dateien in einem Projekt oder in einer einzigen Kompilierung haben oder wenn Sie eine Bibliothek erstellen, müssen Sie einen Standardnamespace-Deklaration oder Moduldeklaration am Anfang der Datei einschließen. F#-Compiler bestimmt einen Modulnamen nur implizit, wenn es nur eine Datei in einer Befehlszeile Projekt oder die Kompilierung, und Sie eine Anwendung erstellen.

Die *Zugriffsmodifizierer* kann einen der folgenden sein: `public`, `private`, `internal`. Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md). Der Standardwert ist „öffentlich“.

## <a name="referencing-code-in-modules"></a>Verweisen auf Code in Modulen

Wenn Sie Funktionen, Typen und Werte aus einem anderen Modul verweisen, müssen Sie einen qualifizierten Namen verwenden oder öffnen Sie das Modul. Wenn Sie einen qualifizierten Namen verwenden, müssen Sie angeben, die Namespaces, die das Modul und der Bezeichner für das gewünschte Programmelement. Sie trennen Sie jedes Teil des vollqualifizierten Pfads durch einen Punkt (.), wie folgt.

`Namespace1.Namespace2.ModuleName.Identifier`

Öffnen Sie das Modul oder eine oder mehrere Namespaces auf den Code zu vereinfachen. Weitere Informationen zum Öffnen von Namespaces und Modulen finden Sie unter [Importdeklarationen: das `open` Schlüsselwort](import-declarations-the-open-keyword.md).

Im folgenden Codebeispiel wird veranschaulicht, ein Modul auf oberster Ebene, die der gesamte Code bis zum Ende der Datei enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

Um diesen Code aus einer anderen Datei im gleichen Projekt verwenden, Sie qualifizierte Namen verwenden, oder Sie öffnen das Modul vor der Verwendung der Funktionen, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Geschachtelte Module

Module können geschachtelt werden. Inneren Module müssen eingezogen werden, so weit wie die äußere Moduldeklarationen, um anzugeben, dass sie die inneren Module, nicht um neue Module sind. Vergleichen Sie beispielsweise die folgenden beiden Beispiele. Modul `Z` ist ein inneres Modul in den folgenden Code.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

Aber Modul `Z` ein gleichgeordnetes Element Modul `Y` in den folgenden Code.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
Modul `Z` ist auch ein gleichgeordnetes Element-Modul in den folgenden Code, da sie nicht so weit wie die anderen Deklarationen in Modul eingezogen ist `Y`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
Schließlich, wenn das äußere Modul verfügt über keine Deklarationen, unmittelbar, von einem anderen Moduldeklaration gefolgt wird wird angenommen, dass der neue Moduldeklaration ein inneres Modul werden, aber der Compiler warnt Sie, wenn die zweite Moduldefinition konsequenter als nicht eingezogen ist die erste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
Um die Warnung zu vermeiden, Rücken Sie das innere-Modul.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
Wenn Sie sich der gesamte Code in einer Datei in ein einzelnes Modul des äußeren und inneren Module angezeigt werden sollen, das äußere Modul erfordert nicht das Gleichheitszeichen und die Deklarationen, einschließlich möglichen Moduldeklarationen inneren-, die in das äußere Modul gespeichert werden müssen nicht mit Einzug dargestellt werden. Deklarationen innerhalb der inneren Moduldeklarationen eingezogen werden müssen. Der folgende Code zeigt diesen Fall.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Rekursive Module

F# 4.1 führt das Konzept der Module ein, die für alle enthaltenen Code gegenseitig rekursiver sein können.  Dies erfolgt über `module rec`.  Verwenden von `module rec` können einige Probleme, nicht mehr zum Schreiben von Code für sich gegenseitig referenzielle Typen und Module verringern.  Im folgenden finden ein Beispiel hierfür:

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

Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide sich aufeinander beziehen.  Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch sich aufeinander beziehen.  Dies ist nicht möglich, die in f# zu express, wenn Sie entfernt die `rec` -Schlüsselwort aus der `RecursiveModule` Modul.

Diese Funktion ist auch möglich, im [Namespaces](namespaces.md) mit f# 4.1.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)  
- [Namespaces](namespaces.md)  
- [F#-RFC-FS-1009 – lassen Sie sich gegenseitig referenzielle Typen und Module über größere Bereiche in Dateien](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)  
