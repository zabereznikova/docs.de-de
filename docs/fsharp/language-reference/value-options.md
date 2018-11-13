---
title: Wertoptionen (F#)
description: Erfahren Sie, bis des F#-Option "Value"-Typs, der eine Version der Struktur des Typs Option ist.
ms.date: 06/16/2018
ms.openlocfilehash: 978bd1713c16f7c050ccb097cb134973d10ef6f5
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "50185835"
---
# <a name="value-options"></a><span data-ttu-id="f1c6c-103">Wertoptionen</span><span class="sxs-lookup"><span data-stu-id="f1c6c-103">Value Options</span></span>

<span data-ttu-id="f1c6c-104">Die Option "Value"-Typ in F# wird verwendet, wenn halten die folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="f1c6c-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="f1c6c-105">Ein Szenario eignet sich für ein [F#-Option](options.md).</span><span class="sxs-lookup"><span data-stu-id="f1c6c-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="f1c6c-106">Verwenden eine Struktur bietet einen Leistungsvorteil in Ihrem Szenario.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="f1c6c-107">Nicht alle Szenarien die Leistung "gelöst" werden Strukturen.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="f1c6c-108">Berücksichtigen Sie die zusätzliche Kosten der kopieren, wenn sie anstelle von Verweistypen mit ein.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="f1c6c-109">Große F#-Programmen instanziiert jedoch häufig viele optionale Typen, die langsamsten Pfad durchlaufen werden, weil Strukturen manchmal eine bessere gesamtleistung während der Lebensdauer eines Programms führen können.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, because structs can sometimes yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="f1c6c-110">Definition</span><span class="sxs-lookup"><span data-stu-id="f1c6c-110">Definition</span></span>

<span data-ttu-id="f1c6c-111">Option "Value" ist definiert als eine [diskriminierte Union](discriminated-unions.md#struct-discriminated-unions) ähnelt der Option-Verweistyp.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="f1c6c-112">Auf diese Weise kann ihre Definition betrachtet werden:</span><span class="sxs-lookup"><span data-stu-id="f1c6c-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="f1c6c-113">Option "Value" entspricht strukturelle Gleichheit und Vergleich.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="f1c6c-114">Der Hauptunterschied besteht darin, dass der kompilierte Name, Typnamen und Groß-/Kleinschreibung Namen anzugeben, dass es sich um einen Werttyp handelt.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="f1c6c-115">Mithilfe der Wertoptionen</span><span class="sxs-lookup"><span data-stu-id="f1c6c-115">Using Value Options</span></span>

<span data-ttu-id="f1c6c-116">Wertoptionen wie dienen [Optionen](options.md).</span><span class="sxs-lookup"><span data-stu-id="f1c6c-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="f1c6c-117">`ValueSome` wird verwendet, um anzugeben, dass ein Wert vorhanden ist und `ValueNone` wird verwendet, wenn ein Wert nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="f1c6c-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="f1c6c-118">Wie bei [Optionen](options.md), die Namenskonvention für eine Funktion, die gibt `ValueOption` besteht darin, ihn mit Präfix `try`.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="f1c6c-119">Werteigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="f1c6c-119">Value Option properties and methods</span></span>

<span data-ttu-id="f1c6c-120">Es gibt eine Eigenschaft für die Werte können zu diesem Zeitpunkt: `Value`.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="f1c6c-121">Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn kein Wert vorhanden ist, wenn diese Eigenschaft aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="f1c6c-122">Wert der Option-Funktionen</span><span class="sxs-lookup"><span data-stu-id="f1c6c-122">Value Option functions</span></span>

<span data-ttu-id="f1c6c-123">Es gibt derzeit eine Modul-Bound-Funktion für Wertoptionen, `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="f1c6c-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="f1c6c-124">Wie bei der `defaultArg` Funktion `defaultValueArg` zugrunde liegenden Wert der angegebenen Option "Value" zurückgegeben, falls es vorhanden ist; andernfalls wird den angegebene Standardwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="f1c6c-125">Zu diesem Zeitpunkt müssen Sie keine anderen Modul-Bound-Funktionen für Wertoptionen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f1c6c-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1c6c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1c6c-126">See also</span></span>

- [<span data-ttu-id="f1c6c-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="f1c6c-127">Options</span></span>](options.md)
