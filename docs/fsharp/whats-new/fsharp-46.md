---
title: Neues in F# 4,6- F# Guide
description: Verschaffen Sie sich einen Überblick über die neuen Features F# , die in 4,6 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 81d3e988d044cb16f8ec079118fd0ede2dabc587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644133"
---
# <a name="whats-new-in-f-46"></a>Neuerungen in F# 4,6

F#4,6 Fügt der F# Sprache mehrere Verbesserungen hinzu.

## <a name="get-started"></a>Erste Schritte

F#4,6 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar. [Beginnen Sie mit F# ](../get-started/index.md) den ersten Schritten, um mehr zu erfahren.

## <a name="anonymous-records"></a>Anonyme Datensätze

[Anonyme Datensätze](../language-reference/anonymous-records.md) sind eine neue Art F# von Typ, F# der in 4,6 eingeführt wurde. Dabei handelt es sich um einfache Aggregate benannter Werte, die nicht vor der Verwendung deklariert werden müssen. Sie können Sie als Strukturen oder Verweis Typen deklarieren. Sie sind standardmäßig Verweis Typen.

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

Sie können auch als Strukturen für deklariert werden, wenn Sie Werttypen gruppieren möchten und in Leistungs relevanten Szenarios betrieben werden:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

Sie sind sehr leistungsstark und können in vielen Szenarios verwendet werden. Weitere Informationen finden Sie unter [Anonyme Datensätze](../language-reference/anonymous-records.md).

## <a name="valueoption-functions"></a>Valueoption-Funktionen

Der in 4,5 hinzugefügte valueoption-Typ weist nun "Modul gebundene Funktions Parität" mit dem Optionstyp auf F# . Im folgenden finden Sie einige häufig verwendete Beispiele:

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> None
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> Some

let reversedString = strOpt |> Option.bind reverse
```

Dies ermöglicht die Verwendung von valueoption in Szenarios, in denen ein Werttyp die Leistung verbessert.
