---
title: Neues in F# 4,6- F# Guide
description: Verschaffen Sie sich einen Überblick über die neuen Features F# , die in 4,6 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 620c1edd8ea212fee306a02d5844b6b322808251
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980391"
---
# <a name="whats-new-in-f-46"></a><span data-ttu-id="4bb43-103">Neuerungen in F# 4,6</span><span class="sxs-lookup"><span data-stu-id="4bb43-103">What's new in F# 4.6</span></span>

<span data-ttu-id="4bb43-104">F#4,6 Fügt der F# Sprache mehrere Verbesserungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4bb43-104">F# 4.6 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="4bb43-105">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="4bb43-105">Get started</span></span>

<span data-ttu-id="4bb43-106">F#4,6 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4bb43-106">F# 4.6 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="4bb43-107">[Beginnen Sie mit F# ](../get-started/index.md) den ersten Schritten, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="4bb43-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="anonymous-records"></a><span data-ttu-id="4bb43-108">Anonyme Datensätze</span><span class="sxs-lookup"><span data-stu-id="4bb43-108">Anonymous records</span></span>

<span data-ttu-id="4bb43-109">[Anonyme Datensätze](../language-reference/anonymous-records.md) sind eine neue Art F# von Typ, F# der in 4,6 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="4bb43-109">[Anonymous records](../language-reference/anonymous-records.md) are a new kind of F# type introduced in F# 4.6.</span></span> <span data-ttu-id="4bb43-110">Dabei handelt es sich um einfache Aggregate benannter Werte, die nicht vor der Verwendung deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4bb43-110">They are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="4bb43-111">Sie können Sie als Strukturen oder Verweis Typen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="4bb43-111">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="4bb43-112">Sie sind standardmäßig Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="4bb43-112">They're reference types by default.</span></span>

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

<span data-ttu-id="4bb43-113">Sie können auch als Strukturen für deklariert werden, wenn Sie Werttypen gruppieren möchten und in Leistungs relevanten Szenarios betrieben werden:</span><span class="sxs-lookup"><span data-stu-id="4bb43-113">They can also be declared as structs for when you want to group value types and are operating in performance-sensitive scenarios:</span></span>

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

<span data-ttu-id="4bb43-114">Sie sind sehr leistungsstark und können in vielen Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bb43-114">They're quite powerful and can be used in numerous scenarios.</span></span> <span data-ttu-id="4bb43-115">Weitere Informationen finden Sie unter [Anonyme Datensätze](../language-reference/anonymous-records.md).</span><span class="sxs-lookup"><span data-stu-id="4bb43-115">Learn more at [Anonymous records](../language-reference/anonymous-records.md).</span></span>

## <a name="valueoption-functions"></a><span data-ttu-id="4bb43-116">Valueoption-Funktionen</span><span class="sxs-lookup"><span data-stu-id="4bb43-116">ValueOption functions</span></span>

<span data-ttu-id="4bb43-117">Der in 4,5 hinzugefügte valueoption-Typ weist nun "Modul gebundene Funktions Parität" mit dem Optionstyp auf F# .</span><span class="sxs-lookup"><span data-stu-id="4bb43-117">The ValueOption type added in F# 4.5 now has "module-bound function parity" with the Option type.</span></span> <span data-ttu-id="4bb43-118">Im folgenden finden Sie einige häufig verwendete Beispiele:</span><span class="sxs-lookup"><span data-stu-id="4bb43-118">Some of the more commonly-used examples are as follows:</span></span>

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> ValueNone
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> ValueSome

let reversedString = strOpt |> ValueOption.bind reverse
```

<span data-ttu-id="4bb43-119">Dies ermöglicht die Verwendung von valueoption in Szenarios, in denen ein Werttyp die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="4bb43-119">This allows for ValueOption to be used just like Option in scenarios where having a value type improves performance.</span></span>
