---
title: Neuerungen in F- 4.7 - F-Leitfaden
description: Verschaffen Sie sich einen Überblick über die neuen Funktionen, die in F- 4.7 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185875"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="3b88e-103">Neuerungen in F- 4.7</span><span class="sxs-lookup"><span data-stu-id="3b88e-103">What's new in F# 4.7</span></span>

<span data-ttu-id="3b88e-104">F-4.7 fügt der Sprache F- 4.7 mehrere Verbesserungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b88e-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="3b88e-105">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="3b88e-105">Get started</span></span>

<span data-ttu-id="3b88e-106">Die F-4.7 ist in allen .NET Core-Verteilungen und Visual Studio-Tools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b88e-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="3b88e-107">[Beginnen Sie mit f',](../get-started/index.md) um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="3b88e-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="3b88e-108">Sprachversion</span><span class="sxs-lookup"><span data-stu-id="3b88e-108">Language version</span></span>

<span data-ttu-id="3b88e-109">Der Compiler "F- 4.7" bietet die Möglichkeit, Ihre effektive Sprachversion über eine Eigenschaft in der Projektdatei festzulegen:</span><span class="sxs-lookup"><span data-stu-id="3b88e-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3b88e-110">Sie können sie auf `4.6` `4.7`die `latest`Werte `preview`, , und festlegen.</span><span class="sxs-lookup"><span data-stu-id="3b88e-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="3b88e-111">Der Standardwert lautet `latest`.</span><span class="sxs-lookup"><span data-stu-id="3b88e-111">The default is `latest`.</span></span>

<span data-ttu-id="3b88e-112">Wenn Sie es `preview`auf festlegen, aktiviert der Compiler alle F-Vorschaufeatures, die in Ihrem Compiler implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="3b88e-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="3b88e-113">Implizite Erträge</span><span class="sxs-lookup"><span data-stu-id="3b88e-113">Implicit yields</span></span>

<span data-ttu-id="3b88e-114">Sie müssen das `yield` Schlüsselwort nicht mehr in Arrays, Listen, Sequenzen oder Berechnungsausdrücken anwenden, aus denen der Typ abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b88e-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="3b88e-115">Im folgenden Beispiel erforderten `yield` beide Ausdrücke die Anweisung für jeden Eintrag vor F.4.7:</span><span class="sxs-lookup"><span data-stu-id="3b88e-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]
```

<span data-ttu-id="3b88e-116">Wenn Sie ein `yield` einzelnes Schlüsselwort einführen, muss auch jedes andere Element darauf angewendet haben. `yield`</span><span class="sxs-lookup"><span data-stu-id="3b88e-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="3b88e-117">Implizite Erträge werden nicht aktiviert, wenn `yield!` sie in einem Ausdruck verwendet werden, der auch verwendet wird, um so etwas wie eine Sequenz abzuflachen.</span><span class="sxs-lookup"><span data-stu-id="3b88e-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="3b88e-118">In diesen Fällen `yield` müssen Sie auch heute noch verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b88e-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="3b88e-119">Platzhalterbezeichner</span><span class="sxs-lookup"><span data-stu-id="3b88e-119">Wildcard identifiers</span></span>

<span data-ttu-id="3b88e-120">In F-Code, der Klassen enthält, muss die Selbstbezeichnerin immer explizit in Memberdeklarationen sein.</span><span class="sxs-lookup"><span data-stu-id="3b88e-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="3b88e-121">Aber in Fällen, in denen die Selbstbezeichnernie nie verwendet wird, ist es traditionell eine Konvention, einen Doppelunterstrich zu verwenden, um eine namenlose Selbstkennung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b88e-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="3b88e-122">Sie können jetzt einen einzelnen Unterstrich verwenden:</span><span class="sxs-lookup"><span data-stu-id="3b88e-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="3b88e-123">Dies gilt `for` auch für Schleifen:</span><span class="sxs-lookup"><span data-stu-id="3b88e-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="3b88e-124">Einzugsentspannungen</span><span class="sxs-lookup"><span data-stu-id="3b88e-124">Indentation relaxations</span></span>

<span data-ttu-id="3b88e-125">Vor F-4.7 erforderten die Einzugsanforderungen für primäre Konstruktor- und statische Memberargumente einen übermäßigen Einzug.</span><span class="sxs-lookup"><span data-stu-id="3b88e-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="3b88e-126">Sie benötigen jetzt nur noch einen einzigen Einzugsbereich:</span><span class="sxs-lookup"><span data-stu-id="3b88e-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
