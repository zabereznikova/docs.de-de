---
title: Wertoptionen
description: Erfahren Sie mehr F# über den Wert Optionstyp, bei dem es sich um eine Struktur Version des Options Typs handelt.
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424022"
---
# <a name="value-options"></a><span data-ttu-id="2dfe5-103">Wertoptionen</span><span class="sxs-lookup"><span data-stu-id="2dfe5-103">Value Options</span></span>

<span data-ttu-id="2dfe5-104">Der Wert Optionstyp in F# wird verwendet, wenn die folgenden beiden Bedingungen vorliegen:</span><span class="sxs-lookup"><span data-stu-id="2dfe5-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="2dfe5-105">Ein Szenario ist für eine [ F# Option](options.md)geeignet.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="2dfe5-106">Die Verwendung einer Struktur bietet einen Leistungsvorteil in Ihrem Szenario.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="2dfe5-107">Nicht alle Leistungs sensiblen Szenarios werden mithilfe von Strukturen "gelöst".</span><span class="sxs-lookup"><span data-stu-id="2dfe5-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="2dfe5-108">Sie müssen die zusätzlichen Kosten für das Kopieren in Erwägung gezogen, wenn Sie Sie anstelle von Verweis Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="2dfe5-109">Große F# Programme instanziieren jedoch häufig viele optionale Typen, die durch heiße Pfade fließen, und in solchen Fällen können Strukturen im Laufe der Lebensdauer eines Programms häufig eine bessere Gesamtleistung erzielen.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="2dfe5-110">Definition</span><span class="sxs-lookup"><span data-stu-id="2dfe5-110">Definition</span></span>

<span data-ttu-id="2dfe5-111">Die Value-Option ist als [Struktur](discriminated-unions.md#struct-discriminated-unions) Unterscheidungs-Union definiert, die dem Verweis Optionstyp ähnelt.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="2dfe5-112">Die Definition kann sich wie folgt vorstellen:</span><span class="sxs-lookup"><span data-stu-id="2dfe5-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="2dfe5-113">Die Option "Value" entspricht Struktur Gleichheit und Vergleich.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="2dfe5-114">Der Hauptunterschied besteht darin, dass der kompilierte Name, der Typname und die Fallnamen alle angeben, dass es sich um einen Werttyp handelt.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="2dfe5-115">Verwenden von Wert Optionen</span><span class="sxs-lookup"><span data-stu-id="2dfe5-115">Using Value Options</span></span>

<span data-ttu-id="2dfe5-116">Wert Optionen werden genau wie [Optionen](options.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="2dfe5-117">`ValueSome` wird verwendet, um anzugeben, dass ein Wert vorhanden ist, und `ValueNone` verwendet, wenn kein Wert vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="2dfe5-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="2dfe5-118">Wie bei den [Optionen](options.md)wird die Benennungs Konvention für eine Funktion, die `ValueOption` zurückgibt, dem `try`vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="2dfe5-119">Eigenschaften und Methoden für Wert Optionen</span><span class="sxs-lookup"><span data-stu-id="2dfe5-119">Value Option properties and methods</span></span>

<span data-ttu-id="2dfe5-120">Zu diesem Zeitpunkt gibt es eine Eigenschaft für Wert Optionen: `Value`.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="2dfe5-121">Wenn diese Eigenschaft aufgerufen wird, wird ein <xref:System.InvalidOperationException> ausgelöst, wenn kein Wert vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="2dfe5-122">Optionen für Wert Optionen</span><span class="sxs-lookup"><span data-stu-id="2dfe5-122">Value Option functions</span></span>

<span data-ttu-id="2dfe5-123">Zurzeit gibt es eine Modul gebundene Funktion für Wert Optionen `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="2dfe5-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="2dfe5-124">Wie bei der `defaultArg`-Funktion gibt `defaultValueArg` den zugrunde liegenden Wert der angegebenen Wert Option zurück, wenn dieser vorhanden ist. Andernfalls wird der angegebene Standardwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="2dfe5-125">Zurzeit sind keine weiteren Modul gebundenen Funktionen für Wert Optionen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2dfe5-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dfe5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dfe5-126">See also</span></span>

- [<span data-ttu-id="2dfe5-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="2dfe5-127">Options</span></span>](options.md)
