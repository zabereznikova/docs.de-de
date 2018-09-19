---
title: Maßeinheiten (F#)
description: Erfahren Sie, wie für Gleitkommawerte und signierten Integer-Werte in f# können Einheiten, die in der Regel verwendet werden, Länge, Volumen und die Masse an verknüpft haben.
ms.date: 05/16/2016
ms.openlocfilehash: ad2193e25f3c0cee6e73cd529ab43d1e4b6b549b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972516"
---
# <a name="units-of-measure"></a><span data-ttu-id="5bb51-103">Maßeinheiten</span><span class="sxs-lookup"><span data-stu-id="5bb51-103">Units of Measure</span></span>

<span data-ttu-id="5bb51-104">Gleitkomma- und signierten Integer-Werte in f# kann Maßeinheiten zugeordnet haben die in der Regel an Länge, Volumen, Masse usw. verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="5bb51-105">Mengen mit Einheiten verwenden, aktivieren Sie den Compiler an, überprüfen Sie, ob arithmetische Beziehungen die richtigen Einheiten, die verhindert, dass Programmierfehler.</span><span class="sxs-lookup"><span data-stu-id="5bb51-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="5bb51-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bb51-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="5bb51-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bb51-107">Remarks</span></span>

<span data-ttu-id="5bb51-108">Die vorherige Syntax definiert *Einheitenname* als eine Einheit.</span><span class="sxs-lookup"><span data-stu-id="5bb51-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="5bb51-109">Das optionale Teil wird verwendet, um ein neues Measure in Bezug auf die zuvor definierte Einheiten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5bb51-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="5bb51-110">Die folgende Zeile definiert z. B. das Measure `cm` (Zentimeter).</span><span class="sxs-lookup"><span data-stu-id="5bb51-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="5bb51-111">Die folgende Zeile definiert das Measure `ml` (Milliliter) als ein kubische Zentimeter (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="5bb51-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="5bb51-112">In der vorherigen Syntax *Measure* ist eine Formel, die Einheiten umfasst.</span><span class="sxs-lookup"><span data-stu-id="5bb51-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="5bb51-113">Klicken Sie in Formeln, die Einheiten umfassen, ganzzahlige Potenzen werden unterstützt (positive und negative), Leerzeichen zwischen Einheiten geben ein Produkt der beiden Einheiten an, `*` gibt auch an einem Produkt Einheiten und `/` einen Quotienten von Einheiten angibt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="5bb51-114">Für eine gegenseitige Einheit, können Sie entweder eine negative ganze Zahl Potenz verwenden oder ein `/` , die eine Trennung zwischen der Zähler und Nenner eine Einheitenformel angibt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="5bb51-115">Mehrere Einheiten im Nenner müssen in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="5bb51-116">Einheiten durch Leerzeichen getrennt nach einer `/` interpretiert werden, als Teil der Nenner jedoch Einheiten nach einer `*` als Teil der Zähler interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="5bb51-117">Sie können 1 Einheitenausdrücke, entweder allein an eine dimensionslose Größe oder zusammen mit anderen Einheiten, z. B. in der Zähler verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="5bb51-118">Beispielsweise würde die Einheit für die Geschwindigkeit geschrieben werden, als `1/s`, wobei `s` Sekunden angibt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="5bb51-119">In Komponententests Formeln werden keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bb51-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="5bb51-120">Sie angeben nicht numerische Konvertierungskonstanten in den Formeln für Komponententest; Allerdings können Sie Konvertierungskonstanten separat mit Einheiten definieren und deren Verwendung in Berechnungen Einheit überprüft.</span><span class="sxs-lookup"><span data-stu-id="5bb51-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="5bb51-121">Unit-Formeln, die das gleiche gemeint, können auf verschiedene Weise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="5bb51-122">Aus diesem Grund konvertiert der Compiler Einheitenformeln in ein konsistentes Format, der negative Zehnerpotenzen Umkehrwerte, die Gruppen-Einheiten in einer einzelnen Zähler und Nenner konvertiert werden soll, und sortiert sie alphabetisch die Einheiten, in der Zähler und Nenner.</span><span class="sxs-lookup"><span data-stu-id="5bb51-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="5bb51-123">Z. B. die Einheitenformeln `kg m s^-2` und `m /s s * kg` werden in konvertiert `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="5bb51-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="5bb51-124">Sie verwenden die Maßeinheiten in Gleitkommaausdrücken.</span><span class="sxs-lookup"><span data-stu-id="5bb51-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="5bb51-125">Gleitkommazahlen zusammen mit zugehörigen Einheiten des Measures mit einer weiteren Ebene der typsicherheit hinzugefügt, und trägt so zur fehlervermeidung die Einheit Konflikt-Fehler, die bei der Verwendung von schwach typisierten Gleitkommazahlen in Formeln auftreten können.</span><span class="sxs-lookup"><span data-stu-id="5bb51-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="5bb51-126">Wenn Sie einen Gleitkommawert schreiben Point-Ausdruck, der Einheiten, die Einheiten, in dem Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5bb51-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="5bb51-127">Sie können Literale mit einer Einheitenformel in spitzen Klammern versehen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="5bb51-128">Sie sind nicht auf ein Leerzeichen zwischen der Anzahl und die Spitze Klammer abzulegen. Sie können jedoch einschließen, ein literales Suffix wie z. B. `f`, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5bb51-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="5bb51-129">Eine solche Anmerkung ändert den Typ des Literals aus einem primitiven Typ (z. B. `float`) in einem dimensionierten Typ, z. B. `float<cm>` oder, in diesem Fall `float<miles/hour>`.</span><span class="sxs-lookup"><span data-stu-id="5bb51-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="5bb51-130">Eine Einheit Anmerkung `<1>` gibt an, dass eine dimensionslose Größe und Typ der primitive Typ ohne Parameter Einheit entspricht.</span><span class="sxs-lookup"><span data-stu-id="5bb51-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="5bb51-131">Der Typ des eine Maßeinheit ist ein Gleitkomma oder ganzzahligen Typ mit Vorzeichen zusammen mit der eine zusätzliche Einheit-Anmerkung, die in Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="5bb51-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="5bb51-132">Daher beim Schreiben des Typs einer Konvertierung von `g` (g), `kg` (kg), geben Sie die Typen, die wie folgt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="5bb51-133">Maßeinheiten dienen zur Kompilierzeit Einheit überprüft jedoch nicht in der Runtime-Umgebung beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="5bb51-134">Aus diesem Grund sie die Leistung nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="5bb51-135">Maßeinheiten können auf einen beliebigen Typ, nicht nur die Gleitkommatypen angewendet werden. allerdings nur Gleitkommatypen, ganzzahlige Typen und Mengen von Dezimaltypen dimensioniert Unterstützung angemeldet.</span><span class="sxs-lookup"><span data-stu-id="5bb51-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="5bb51-136">Aus diesem Grund ist es nur sinnvoll, Maßeinheiten zu verwenden, auf den primitiven Typen und Aggregate, die die primitive Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5bb51-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="5bb51-137">Das folgende Beispiel veranschaulicht die Verwendung von Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="5bb51-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="5bb51-138">Im folgenden Codebeispiel wird veranschaulicht, wie eine dimensionslose Gleitkommazahl in eine dimensionierten Gleitkommawert konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="5bb51-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="5bb51-139">Sie multiplizieren Sie einfach mit 1,0, der Dimensionen auf der 1.0 angewendet.</span><span class="sxs-lookup"><span data-stu-id="5bb51-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="5bb51-140">Sie können dies in einer Funktion wie abstrahieren `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="5bb51-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="5bb51-141">Auch wenn Sie dimensionierte Werte an Funktionen, die dimensionslose Gleitkommazahlen erwarten übergeben, müssen Sie die Einheiten oder umgewandelt `float` mithilfe der `float` Operator.</span><span class="sxs-lookup"><span data-stu-id="5bb51-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="5bb51-142">In diesem Beispiel Teilen Sie Sie durch `1.0<degC>` für die Argumente `printf` da `printf` dimensionslose Größen erwartet.</span><span class="sxs-lookup"><span data-stu-id="5bb51-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="5bb51-143">Die folgende beispielsitzung wird gezeigt, die von Eingaben und Ausgaben für diesen Code.</span><span class="sxs-lookup"><span data-stu-id="5bb51-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="5bb51-144">Verwenden von generischen Einheiten</span><span class="sxs-lookup"><span data-stu-id="5bb51-144">Using Generic Units</span></span>

<span data-ttu-id="5bb51-145">Sie können generische Funktionen, die ausgeführt werden Daten schreiben, die über eine zugeordnete Maßeinheit verfügt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="5bb51-146">Sie dazu einen Typ zusammen mit einer generischen Einheit angeben, wie ein Typparameter, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="5bb51-147">Erstellen von Aggregattypen mit generischen Einheiten</span><span class="sxs-lookup"><span data-stu-id="5bb51-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="5bb51-148">Der folgende Code zeigt, wie Sie einen aggregierten Typ erstellen, der von einzelnen Gleitkommawerte Einheiten besteht, die generisch sind.</span><span class="sxs-lookup"><span data-stu-id="5bb51-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="5bb51-149">Dadurch wird einen einzelnen Typ erstellt werden, der mit einer Vielzahl von Einheiten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5bb51-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="5bb51-150">Darüber hinaus beibehalten generische Einheiten typsicherheit, indem Sie sicherstellen, dass ein generischer Typ, der einen Satz von Einheiten hat einen anderen Typ als den gleichen generischen Typ mit einem anderen Satz von Einheiten ist.</span><span class="sxs-lookup"><span data-stu-id="5bb51-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="5bb51-151">Diese Technik basiert auf, die die `Measure` Attribut kann auf den Typparameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bb51-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="5bb51-152">Einheiten zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5bb51-152">Units at Runtime</span></span>

<span data-ttu-id="5bb51-153">Maßeinheiten werden für die Überprüfung des statischen Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bb51-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="5bb51-154">Wenn Gleitkommawerte kompiliert werden, werden die Einheiten entfernt, damit die Einheiten, die zur Laufzeit nicht mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5bb51-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="5bb51-155">Jeder Versuch, die Funktionalität zu implementieren, der Überprüfung der Einheiten zur Laufzeit abhängig ist daher nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="5bb51-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="5bb51-156">Beispielsweise implementiert ein `ToString` Funktion zum Ausgeben der Einheiten ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="5bb51-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="5bb51-157">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="5bb51-157">Conversions</span></span>

<span data-ttu-id="5bb51-158">Zum Konvertieren eines Typs, die Einheiten (z. B. `float<'u>`) auf einen Typ, der nicht Einheiten verfügt, können Sie die standardkonvertierung-Funktion.</span><span class="sxs-lookup"><span data-stu-id="5bb51-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="5bb51-159">Beispielsweise können Sie `float` zum Konvertieren einer `float` Wert, der nicht-Einheiten, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="5bb51-160">Um einen Wert ohne Einheiten auf einen Wert zu konvertieren, die Einheiten hat, können Sie multiplizieren mit Wert 1 oder 1,0, der mit Anmerkungen versehen wird mit den entsprechenden Einheiten.</span><span class="sxs-lookup"><span data-stu-id="5bb51-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="5bb51-161">Für das Schreiben von Ebenen der Interoperabilität, gibt es jedoch auch einige explizite-Funktionen, die Sie verwenden können, ohne Einheiten Werte in Werte mit Einheiten zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="5bb51-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="5bb51-162">Diese sind in der [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) Modul.</span><span class="sxs-lookup"><span data-stu-id="5bb51-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="5bb51-163">Beispielsweise, um ohne Einheiten in `float` auf eine `float<cm>`, verwenden Sie [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bb51-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="5bb51-164">Maßeinheiten in der F#-Kernbibliothek</span><span class="sxs-lookup"><span data-stu-id="5bb51-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="5bb51-165">Eine Einheitenbibliothek finden Sie in der `FSharp.Data.UnitSystems.SI` Namespace.</span><span class="sxs-lookup"><span data-stu-id="5bb51-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="5bb51-166">Er enthält sowohl die Symbol-Form SI-Einheiten (wie `m` für Verbrauchseinheit) in der `UnitSymbols` Sub-Namespace und der vollständige Name (wie `meter` für Verbrauchseinheit) in der `UnitNames` Sub-Namespace.</span><span class="sxs-lookup"><span data-stu-id="5bb51-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bb51-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bb51-167">See also</span></span>

- [<span data-ttu-id="5bb51-168">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="5bb51-168">F# Language Reference</span></span>](index.md)
