---
title: Module
description: 'Erfahren Sie, wie ein f #-Modul eine Gruppierung von f #-Code (z. b. Werte, Typen und Funktions Werte) in einem f #-Programm ist.'
ms.date: 04/24/2017
ms.openlocfilehash: 5f99bbd8069478bf0c7db2800ae545f31926728a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794363"
---
# <a name="modules"></a>Module

Im Kontext der Sprache f # ist ein *Modul* eine Gruppierung von f #-Code, wie z. b. Werte, Typen und Funktions Werte in einem F #-Programm. Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.

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

Ein f #-Modul ist eine Gruppierung von f #-Codekonstrukten, z. b. Typen, Werte, `do` Funktions Werte und Code in Bindungen. Sie wird als Common Language Runtime (CLR)-Klasse implementiert, die nur statische Member aufweist. Je nachdem, ob die gesamte Datei im Modul enthalten ist, gibt es zwei Arten von Modul Deklarationen: eine Modul Deklaration der obersten Ebene und eine lokale Modul Deklaration. Eine Modul Deklaration der obersten Ebene enthält die gesamte Datei im Modul. Eine Modul Deklaration der obersten Ebene kann nur als erste Deklaration in einer Datei angezeigt werden.

In der Syntax für die Modul Deklaration der obersten Ebene ist der optionale *qualified-Namespace* die Sequenz von Namen in den Namen des in der Tabelle enthaltenen Namespace, die das Modul enthält. Der qualifizierte Namespace muss nicht zuvor deklariert werden.

Sie müssen keine Deklarationen in einem Modul der obersten Ebene einfügen. Sie müssen alle Deklarationen in lokalen Modulen einziehen. In einer lokalen Modul Deklaration sind nur die Deklarationen, die in dieser Modul Deklaration eingezogen werden, Teil des Moduls.

Wenn eine Codedatei nicht mit einer Modul Deklaration der obersten Ebene oder einer Namespace Deklaration beginnt, wird der gesamte Inhalt der Datei, einschließlich aller lokalen Module, Teil eines implizit erstellten Moduls auf oberster Ebene, das denselben Namen wie die Datei hat, ohne die Erweiterung, wobei der erste Buchstabe in Großbuchstaben konvertiert wird. Sehen Sie sich beispielsweise die folgende Datei an.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

Diese Datei würde so kompiliert werden, als ob Sie auf diese Weise geschrieben würde:

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

Wenn Sie über mehrere Module in einer Datei verfügen, müssen Sie für jedes Modul eine lokale Modul Deklaration verwenden. Wenn ein einschließender Namespace deklariert wird, sind diese Module Teil des einschließenden Namespace. Wenn kein einschließender Namespace deklariert wird, werden die Module Teil des implizit erstellten Moduls der obersten Ebene. Das folgende Codebeispiel zeigt eine Codedatei, die mehrere Module enthält. Der Compiler erstellt implizit ein Modul der obersten Ebene mit `Multiplemodules`dem Namen `MyModule1` , `MyModule2` und und sind in diesem Modul der obersten Ebene eingebettet.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

Wenn Sie über mehrere Dateien in einem Projekt oder einer einzelnen Kompilierung verfügen oder wenn Sie eine Bibliothek erstellt haben, müssen Sie am Anfang der Datei eine Namespace Deklaration oder Modul Deklaration einschließen. Der F #-Compiler bestimmt einen Modulnamen nur implizit, wenn sich nur eine Datei in einer Projekt-oder Kompilierungs Befehlszeile befindet und Sie eine Anwendung erstellen.

Der Zugriffsmodifizierer kann eine der folgenden `public`sein `private`: `internal`,,. *accessibility-modifier* Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md). Der Standardwert ist public.

## <a name="referencing-code-in-modules"></a>Verweisen auf Code in Modulen

Wenn Sie auf Funktionen, Typen und Werte eines anderen Moduls verweisen, müssen Sie entweder einen qualifizierten Namen verwenden oder das Modul öffnen. Wenn Sie einen qualifizierten Namen verwenden, müssen Sie die Namespaces, das Modul und den Bezeichner für das gewünschte Programmelement angeben. Sie trennen die einzelnen Teile des qualifizierten Pfades wie folgt durch einen Punkt (.).

`Namespace1.Namespace2.ModuleName.Identifier`

Sie können das Modul oder einen oder mehrere Namespaces öffnen, um den Code zu vereinfachen. Weitere Informationen zum Öffnen von Namespaces und Modulen finden Sie unter [Import Deklarationen `open` : das-Schlüsselwort](import-declarations-the-open-keyword.md).

Das folgende Codebeispiel zeigt ein Modul der obersten Ebene, das den gesamten Code bis zum Ende der Datei enthält.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

Wenn Sie diesen Code aus einer anderen Datei im selben Projekt verwenden möchten, verwenden Sie entweder qualifizierte Namen, oder öffnen Sie das Modul, bevor Sie die Funktionen verwenden, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Geduckte Module

Module können eingebettet werden. Innere Module müssen in den Deklarationen äußerer Module eingezogen werden, um anzugeben, dass es sich um interne Module, nicht um neue Module handelt. Vergleichen Sie beispielsweise die folgenden beiden Beispiele. Das `Z` Modul ist ein internes Modul im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

Das Modul `Z` ist aber ein gleich geordnetes Modul `Y` im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
Das `Z` Modul ist auch ein gleich geordnetes Modul im folgenden Code, da es nicht in das Modul eingefügt wird, das nicht in das `Y`Modul eingefügt wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
Wenn das äußere Modul keine Deklarationen hat und unmittelbar eine andere Modul Deklaration folgt, wird angenommen, dass es sich bei der neuen Modul Deklaration um ein internes Modul handelt, aber der Compiler warnt Sie, wenn die zweite Modul Definition nicht weiter als die erste eingezogen ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
Um die Warnung auszuschließen, einziehen Sie das innere Modul.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
Wenn sich der gesamte Code in einer Datei in einem einzelnen äußeren Modul befinden soll und Sie innere Module benötigen, benötigt das äußere Modul nicht das Gleichheitszeichen, und die Deklarationen, einschließlich aller inneren Modul Deklarationen, die im äußeren Modul enthalten sind, müssen nicht eingezogen werden. Deklarationen innerhalb der inneren Modul Deklarationen müssen eingezogen werden. Der folgende Code zeigt diesen Fall.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Rekursive Module

F # 4,1 führt das Konzept von Modulen ein, die es ermöglichen, dass der gesamte enthaltene Code gegenseitig rekursiv ist.  Dies erfolgt über `module rec`.  Die Verwendung `module rec` von kann einige Probleme verringern, die sich nicht gegenseitig referenziellen Code zwischen Typen und Modulen schreiben können.  Im folgenden finden Sie ein Beispiel hierfür:

```fsharp
module rec RecursiveModule =
    type Orientation = Up | Down
    type PeelState = Peeled | Unpeeled

    // This exception depends on the type below.
    exception DontSqueezeTheBananaException of Banana

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

Beachten Sie, dass `DontSqueezeTheBananaException` die Ausnahme und `Banana` die Klasse beide aufeinander verweisen.  Darüber hinaus verweisen das `BananaHelpers` Modul und die `Banana` Klasse auch aufeinander.  Dies wäre in F # nicht möglich, wenn Sie das `rec` -Schlüsselwort aus dem `RecursiveModule` Modul entfernt haben.

Diese Funktion ist auch in [Namespaces](namespaces.md) mit F # 4,1 möglich.

## <a name="see-also"></a>Weitere Informationen

- [F #-Sprachreferenz](index.md)
- [Namespaces](namespaces.md)
- [F # RFC FS-1009-zulassen von sich gegenseitig referenziellen Typen und Modulen über größere Bereiche innerhalb von Dateien](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
