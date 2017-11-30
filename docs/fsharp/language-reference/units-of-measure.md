---
title: "Maßeinheiten (F#)"
description: "Erfahren Sie, wie für Gleitkommawerte und Ganzzahl mit Vorzeichen Werte in f# können Einheiten, die in der Regel verwendet werden, um anzugeben, Länge, Volume und Massenspeichertreiber zugeordnet sein."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: cb2eb658-df6c-422e-afad-97422609c773
ms.openlocfilehash: 2d0683e864c5684a78c02e177c296d3067295723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="units-of-measure"></a><span data-ttu-id="ecda6-104">Maßeinheiten</span><span class="sxs-lookup"><span data-stu-id="ecda6-104">Units of Measure</span></span>

<span data-ttu-id="ecda6-105">Gleitkomma- und Werte für ganze Zahl mit Vorzeichen in f# kann Maßeinheiten, verknüpft haben die in der Regel, Länge, Volumen, um anzugeben, Masse usw. verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-105">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="ecda6-106">Mengen mit Einheiten verwenden, aktivieren Sie den Compiler an, überprüfen Sie, ob arithmetische Beziehungen die richtige Einheiten, die verhindert Programmierfehler.</span><span class="sxs-lookup"><span data-stu-id="ecda6-106">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>


## <a name="syntax"></a><span data-ttu-id="ecda6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecda6-107">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="ecda6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecda6-108">Remarks</span></span>
<span data-ttu-id="ecda6-109">Die vorherige Syntax definiert *Einheitenname* als eine Einheit.</span><span class="sxs-lookup"><span data-stu-id="ecda6-109">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="ecda6-110">Das optionale Teil wird verwendet, um ein neues Measure im Hinblick auf die zuvor definierte Einheiten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ecda6-110">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="ecda6-111">Die folgende Zeile definiert z. B. das Measure `cm` (Zentimeter).</span><span class="sxs-lookup"><span data-stu-id="ecda6-111">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="ecda6-112">Die folgende Zeile wird das Measure definiert `ml` (Milliliter) als eine kubische Zentimeter (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="ecda6-112">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="ecda6-113">In der vorherigen Syntax *Measure* ist eine Formel, die Einheiten.</span><span class="sxs-lookup"><span data-stu-id="ecda6-113">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="ecda6-114">In Formeln, die Einheiten einschließen, ganzzahlige Potenzen werden unterstützt (positive und negative), Leerzeichen zwischen Einheiten geben ein Produkt der beiden Einheiten `*` gibt ebenfalls ein Produkt von Einheiten, und `/` gibt einen Quotienten von Einheiten.</span><span class="sxs-lookup"><span data-stu-id="ecda6-114">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="ecda6-115">Für eine reziproke Unit, können Sie entweder eine negative ganze Zahl Potenz verwenden oder eine `/` , die eine Trennung zwischen der Zähler und Nenner eine Einheitenformel angibt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-115">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="ecda6-116">Mehrere Einheiten im Nenner müssen in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-116">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="ecda6-117">Einheiten getrennt durch Leerzeichen nach einer `/` werden als Teil der Nenner jedoch Einheiten nach interpretiert eine `*` als Teil der Zähler interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-117">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="ecda6-118">Sie können 1 Einheitenausdrücke, entweder allein, um eine reine Menge anzugeben oder zusammen mit anderen Einheiten, z. B. in der Zähler verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-118">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="ecda6-119">Beispielsweise würde die Einheiten für einen Satz geschrieben werden, als `1/s`, wobei `s` Sekunden angibt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-119">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="ecda6-120">In Einheitenformeln sind keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecda6-120">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="ecda6-121">Sie angeben keinen numerische Konvertierungskonstanten in der Einheitenformeln; Sie können jedoch Konvertierungskonstanten separat mit Einheiten definieren und in der Einheit geprüfte Berechnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-121">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="ecda6-122">Unit-Formeln, die der gleichen Bedeutung können auf verschiedene Weise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-122">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="ecda6-123">Daher konvertiert der Compiler Einheitenformeln in ein konsistentes Format, der negative Zehnerpotenzen Umkehrwerte, Gruppen Einheiten in einen einzelnen Zähler und Nenner konvertiert, und sortiert die Einheiten in der Zähler und Nenner alphabetisch.</span><span class="sxs-lookup"><span data-stu-id="ecda6-123">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="ecda6-124">Z. B. die Einheitenformeln `kg m s^-2` und `m /s s * kg` werden in konvertiert `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="ecda6-124">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="ecda6-125">Sie können die Maßeinheiten in floating Point-Ausdrücke verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-125">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="ecda6-126">Mit Gleitkommazahlen zusammen mit zugehörigen Einheiten Measure Fügt eine weitere Ebene von typsicherheit und hilft vermeiden, die Einheit Konflikt auftretende Fehler in Formeln können bei der Verwendung von schwach typisierten Gleitkommazahlen.</span><span class="sxs-lookup"><span data-stu-id="ecda6-126">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="ecda6-127">Wenn Sie einen Gleitkommawert schreiben Point-Ausdruck, der Einheiten verwendet, die Einheiten im Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ecda6-127">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="ecda6-128">Sie können Literale mit einer Einheitenformel in spitzen Klammern, mit Anmerkungen versehen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-128">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="ecda6-129">Sie nehmen kein Leerzeichen zwischen der Anzahl und der spitzen Klammer einfügen; Sie dürfen jedoch enthalten ein literales Suffix z. B. `f`, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ecda6-129">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="ecda6-130">Eine solche Anmerkung ändert den Typ des Literals von einem primitiven Typ (z. B. `float`) in einen dimensionierten Typ, z. B. `float<cm>` oder in diesem Fall `float<miles/hour>`.</span><span class="sxs-lookup"><span data-stu-id="ecda6-130">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="ecda6-131">Eine Einheit Anmerkung `<1>` gibt an, dass eine reine Menge und Typ der primitive Typ ohne Parameter Einheit entspricht.</span><span class="sxs-lookup"><span data-stu-id="ecda6-131">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="ecda6-132">Der Typ des eine Maßeinheit eines Gleitkommatyps ist oder zusammen mit einer zusätzlichen Einheit-Anmerkung, die in Klammern angegebenen ganzzahligen Typ mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="ecda6-132">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="ecda6-133">Daher wird beim Schreiben des Typs einer Konvertierung von `g` (g), `kg` (Kilogramm), beschreiben Sie die Typen, die wie folgt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-133">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="ecda6-134">Maßeinheiten werden zum Zeitpunkt der Kompilierung Einheit überprüft jedoch nicht in der Laufzeitumgebung beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-134">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="ecda6-135">Aus diesem Grund sie die Leistung nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-135">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="ecda6-136">Maßeinheiten können auf einen beliebigen Typ, der nicht nur die Gleitkommatypen angewendet werden. Allerdings signiert nur Gleitkommatypen, ganzzahlige Typen und Dezimaltypen Unterstützung dimensioniert Mengen.</span><span class="sxs-lookup"><span data-stu-id="ecda6-136">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="ecda6-137">Aus diesem Grund ist es nur sinnvoll, verwenden Maßeinheiten für primitiven Typen und Aggregate, die diese primitiven Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ecda6-137">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="ecda6-138">Das folgende Beispiel veranschaulicht die Verwendung von Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="ecda6-138">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
<span data-ttu-id="ecda6-139">Im folgenden Codebeispiel wird veranschaulicht, wie eine reine Gleitkommazahl in eine dimensionierten Gleitkommawert konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="ecda6-139">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="ecda6-140">Sie multiplizieren Sie einfach mit 1.0, die Dimensionen der 1.0 anwenden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-140">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="ecda6-141">Sie können dies in einer Funktion wie abstrakte `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="ecda6-141">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="ecda6-142">Auch wenn Sie dimensionierte Werte an Funktionen, die reine Gleitkommazahlen erwarten übergeben, müssen Sie die Einheiten oder umgewandelt `float` mithilfe der `float` Operator.</span><span class="sxs-lookup"><span data-stu-id="ecda6-142">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="ecda6-143">In diesem Beispiel Teilen Sie Sie durch `1.0<degC>` für die Argumente für `printf` da `printf` reine Mengen erwartet.</span><span class="sxs-lookup"><span data-stu-id="ecda6-143">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="ecda6-144">Das folgende Beispiel-Sitzung wird gezeigt, die über Eingaben und Ausgaben für diesen Code.</span><span class="sxs-lookup"><span data-stu-id="ecda6-144">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="ecda6-145">Verwenden von generischen Einheiten</span><span class="sxs-lookup"><span data-stu-id="ecda6-145">Using Generic Units</span></span>
<span data-ttu-id="ecda6-146">Sie können generische Funktionen, die ausgeführt werden für Daten schreiben, die über eine zugeordnete Maßeinheit verfügt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-146">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="ecda6-147">Sie dazu durch Angabe eines Typs zusammen mit einer generischen Einheit als ein Type-Parameter, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-147">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="ecda6-148">Erstellen von Aggregattypen mit generischen Einheiten</span><span class="sxs-lookup"><span data-stu-id="ecda6-148">Creating Aggregate Types with Generic Units</span></span>
<span data-ttu-id="ecda6-149">Der folgende Code zeigt, wie einen aggregierten Typ erstellt, aus der einzelne Gleitkommawerte besteht, die Zeiteinheiten darstellen, die generisch sind.</span><span class="sxs-lookup"><span data-stu-id="ecda6-149">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="ecda6-150">Dadurch wird einen einzelnen Typ erstellt werden, der mit einer Vielzahl von Einheiten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ecda6-150">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="ecda6-151">Darüber hinaus beibehalten generische Einheiten typsicherheit, indem Sie sicherstellen, dass ein generischer Typ, der eine Gruppe von Einheiten hat einen anderen Typ als den gleichen generischen Typ mit einem anderen Satz von Einheiten ist.</span><span class="sxs-lookup"><span data-stu-id="ecda6-151">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="ecda6-152">Die Grundlage für diese Technik ist, die die `Measure` Attribut kann an den Typparameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-152">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a><span data-ttu-id="ecda6-153">Einheiten zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ecda6-153">Units at Runtime</span></span>
<span data-ttu-id="ecda6-154">Maßeinheiten werden für die Überprüfung des statischen Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecda6-154">Units of measure are used for static type checking.</span></span> <span data-ttu-id="ecda6-155">Wenn Gleitkommawerte kompiliert werden, sind die Maßeinheiten entfernt, sodass die Einheiten, die zur Laufzeit nicht mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ecda6-155">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="ecda6-156">Jeder Versuch, die Funktionalität zu implementieren, die davon abhängen, überprüfen die Einheiten zur Laufzeit ist daher nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="ecda6-156">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="ecda6-157">Implementieren Sie z. B. eine `ToString` Funktion zum Ausgeben der Einheiten ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="ecda6-157">For example, implementing a `ToString` function to print out the units is not possible.</span></span>


## <a name="conversions"></a><span data-ttu-id="ecda6-158">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ecda6-158">Conversions</span></span>
<span data-ttu-id="ecda6-159">Beim Konvertieren eines Typs, die Einheiten (z. B. `float<'u>`) in einen Typ, der nicht Einheiten verfügt, können Sie die standardkonvertierung-Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecda6-159">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="ecda6-160">Beispielsweise können Sie `float` konvertieren in eine `float` -Wert, der nicht Einheiten verfügt, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-160">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="ecda6-161">Um einen Wert ohne Einheiten auf einen Wert zu konvertieren, die Einheiten besitzt, können Sie multiplizieren mit Wert 1 oder 1.0, der kommentiert wird mit den entsprechenden Einheiten.</span><span class="sxs-lookup"><span data-stu-id="ecda6-161">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="ecda6-162">Zum Schreiben von Ebenen der Interoperabilität, gibt es jedoch auch einige explizite-Funktionen, die Sie verwenden können, ohne Einheiten Werte in Werte mit Einheiten zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ecda6-162">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="ecda6-163">Diese befinden sich die [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) Modul.</span><span class="sxs-lookup"><span data-stu-id="ecda6-163">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="ecda6-164">Beispielsweise, um ohne Einheiten in `float` auf eine `float<cm>`, verwenden Sie [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecda6-164">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a><span data-ttu-id="ecda6-165">Maßeinheiten im f# Power Pack</span><span class="sxs-lookup"><span data-stu-id="ecda6-165">Units of Measure in the F# Power Pack</span></span>
<span data-ttu-id="ecda6-166">Ist eine Einheitenbibliothek in F#-PowerPack verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecda6-166">A unit library is available in the F# PowerPack.</span></span> <span data-ttu-id="ecda6-167">Die Einheitenbibliothek enthält SI-Einheiten und physikalische Konstanten.</span><span class="sxs-lookup"><span data-stu-id="ecda6-167">The unit library includes SI units and physical constants.</span></span>


## <a name="see-also"></a><span data-ttu-id="ecda6-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecda6-168">See Also</span></span>
[<span data-ttu-id="ecda6-169">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ecda6-169">F# Language Reference</span></span>](index.md)
