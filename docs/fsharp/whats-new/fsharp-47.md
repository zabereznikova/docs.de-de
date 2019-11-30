---
title: Neues in F# 4,7- F# Guide
description: Verschaffen Sie sich einen Überblick über die neuen Features F# , die in 4,7 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644121"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="28a3b-103">Neuerungen in F# 4,7</span><span class="sxs-lookup"><span data-stu-id="28a3b-103">What's new in F# 4.7</span></span>

<span data-ttu-id="28a3b-104">F#4,7 fügt der F# Sprache mehrere Verbesserungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="28a3b-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="28a3b-105">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="28a3b-105">Get started</span></span>

<span data-ttu-id="28a3b-106">F#4,7 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28a3b-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="28a3b-107">[Beginnen Sie mit F# ](../get-started/index.md) den ersten Schritten, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="28a3b-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="28a3b-108">Sprachversion</span><span class="sxs-lookup"><span data-stu-id="28a3b-108">Language version</span></span>

<span data-ttu-id="28a3b-109">Der F# 4,7-Compiler führt die Möglichkeit ein, ihre effektive Sprachversion über eine Eigenschaft in der Projektdatei festzulegen:</span><span class="sxs-lookup"><span data-stu-id="28a3b-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="28a3b-110">Sie können Sie auf die Werte `4.6`, `4.7`, `latest`und `preview`festlegen.</span><span class="sxs-lookup"><span data-stu-id="28a3b-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="28a3b-111">Der Standardwert ist `latest`.</span><span class="sxs-lookup"><span data-stu-id="28a3b-111">The default is `latest`.</span></span>

<span data-ttu-id="28a3b-112">Wenn Sie `preview`festlegen, aktiviert der Compiler alle F# Vorschau Features, die in Ihrem Compiler implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="28a3b-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="28a3b-113">Implizite Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="28a3b-113">Implicit yields</span></span>

<span data-ttu-id="28a3b-114">Sie müssen das `yield`-Schlüsselwort nicht mehr in Arrays, Listen, Sequenzen oder Berechnungs Ausdrücken anwenden, in denen der Typ abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="28a3b-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="28a3b-115">Im folgenden Beispiel benötigen beide Ausdrücke die `yield`-Anweisung für jeden Eintrag vor F# 4,7:</span><span class="sxs-lookup"><span data-stu-id="28a3b-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="28a3b-116">Wenn Sie ein einzelnes `yield`-Schlüsselwort einführen, muss für jedes andere Element ebenfalls `yield` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="28a3b-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="28a3b-117">Implizite Ergebnisse werden nicht aktiviert, wenn Sie in einem Ausdruck verwendet werden, der auch `yield!` verwendet, um eine Sequenz zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="28a3b-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="28a3b-118">In diesen Fällen müssen Sie `yield` noch heute verwenden.</span><span class="sxs-lookup"><span data-stu-id="28a3b-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="28a3b-119">Platzhalter Bezeichner</span><span class="sxs-lookup"><span data-stu-id="28a3b-119">Wildcard identifiers</span></span>

<span data-ttu-id="28a3b-120">In F# Code, der Klassen einschließt, muss der Self-Identifier in Element Deklarationen immer explizit sein.</span><span class="sxs-lookup"><span data-stu-id="28a3b-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="28a3b-121">In Fällen, in denen der selbst Bezeichner niemals verwendet wird, war es jedoch üblich, einen doppelten unterstrich zu verwenden, um einen namenlosen Self-Identifier anzugeben.</span><span class="sxs-lookup"><span data-stu-id="28a3b-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="28a3b-122">Sie können nun einen einzelnen Unterstrich verwenden:</span><span class="sxs-lookup"><span data-stu-id="28a3b-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="28a3b-123">Dies gilt auch für `for` Schleifen:</span><span class="sxs-lookup"><span data-stu-id="28a3b-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="28a3b-124">Einrückungen</span><span class="sxs-lookup"><span data-stu-id="28a3b-124">Indentation relaxations</span></span>

<span data-ttu-id="28a3b-125">Vor F# 4,7 erforderten die Einzugs Anforderungen für primäre Konstruktoren und statische Member-Argumente einen übermäßigen Einzug.</span><span class="sxs-lookup"><span data-stu-id="28a3b-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="28a3b-126">Sie benötigen jetzt nur einen einzelnen Einzugsbereich:</span><span class="sxs-lookup"><span data-stu-id="28a3b-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
