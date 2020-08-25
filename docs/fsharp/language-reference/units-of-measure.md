---
title: Maßeinheiten
description: 'Erfahren Sie, wie Gleit Komma-und ganzzahlige Werte mit Vorzeichen in F # mit zugeordneten Maßeinheiten verknüpft werden können, die normalerweise verwendet werden, um Länge, Volume und Masse anzugeben.'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811573"
---
# <a name="units-of-measure"></a><span data-ttu-id="75dda-103">Maßeinheiten</span><span class="sxs-lookup"><span data-stu-id="75dda-103">Units of Measure</span></span>

<span data-ttu-id="75dda-104">Gleit Komma-und ganzzahlige Werte mit Vorzeichen in F # können über zugeordnete Maßeinheiten verfügen, die normalerweise verwendet werden, um Länge, Volume, Masse usw. anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75dda-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="75dda-105">Durch die Verwendung von Mengen mit Einheiten ermöglichen Sie es dem Compiler, zu überprüfen, ob arithmetische Beziehungen über die richtigen Einheiten verfügen, sodass Programmierfehler vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="75dda-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="75dda-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="75dda-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="75dda-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75dda-107">Remarks</span></span>

<span data-ttu-id="75dda-108">Die vorherige Syntax definiert *Unit-Name* als Maßeinheit.</span><span class="sxs-lookup"><span data-stu-id="75dda-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="75dda-109">Der optionale Teil wird verwendet, um ein neues Measure in Bezug auf zuvor definierte Einheiten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="75dda-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="75dda-110">Die folgende Zeile definiert z. b. das Measure `cm` (Zentimeter).</span><span class="sxs-lookup"><span data-stu-id="75dda-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="75dda-111">Die folgende Zeile definiert das Measure `ml` (Milliliter) als kubischen Zentimeter ( `cm^3` ).</span><span class="sxs-lookup"><span data-stu-id="75dda-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="75dda-112">In der vorherigen Syntax ist *Measure* eine Formel, die Einheiten umfasst.</span><span class="sxs-lookup"><span data-stu-id="75dda-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="75dda-113">In Formeln, die Einheiten einschließen, werden ganzzahlige Kräfte unterstützt (positiv und negativ), Leerzeichen zwischen Einheiten geben ein Produkt der beiden Einheiten an, geben `*` auch ein Produkt von Einheiten an und geben `/` einen Quotienten von Einheiten an.</span><span class="sxs-lookup"><span data-stu-id="75dda-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="75dda-114">Für eine wechselseitige Einheit können Sie entweder eine negative ganzzahlige Potenz oder eine verwenden `/` , die eine Trennung zwischen dem Zähler und dem Nenner einer Einheitsformel angibt.</span><span class="sxs-lookup"><span data-stu-id="75dda-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="75dda-115">Mehrere Einheiten im Nenner müssen in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="75dda-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="75dda-116">Einheiten, die nach einem durch Leerzeichen getrennt `/` sind, werden als Teil des Nenners interpretiert, aber alle nach einem folgenden Einheiten `*` werden als Teil des zähators interpretiert.</span><span class="sxs-lookup"><span data-stu-id="75dda-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="75dda-117">Sie können 1 in Einheiten Ausdrücken verwenden, und zwar entweder allein zum Angeben einer dimensionierten Menge oder in Verbindung mit anderen Einheiten, wie z. b. im Zähler.</span><span class="sxs-lookup"><span data-stu-id="75dda-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="75dda-118">Beispielsweise werden die Einheiten für eine Rate als geschrieben `1/s` , wobei die `s` Sekunden angibt.</span><span class="sxs-lookup"><span data-stu-id="75dda-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="75dda-119">In Einheits Formeln werden keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="75dda-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="75dda-120">Sie geben keine numerischen Konvertierungs Konstanten in den Einheits Formeln an; Allerdings können Sie Konvertierungs Konstanten mit Einheiten separat definieren und in Berechnungen mit Einheiten Prüfung verwenden.</span><span class="sxs-lookup"><span data-stu-id="75dda-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="75dda-121">Einheits Formeln, die das gleiche bedeuten, können auf verschiedene Weise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="75dda-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="75dda-122">Daher konvertiert der Compiler Einheits Formeln in ein konsistentes Formular, das negative Kräfte in Rückstände konvertiert, Einheiten in einen einzelnen Zähler und einen Nenner gruppiert und die Einheiten im Zähler und Nenner alphabetisch sortiert.</span><span class="sxs-lookup"><span data-stu-id="75dda-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="75dda-123">Beispielsweise werden die Einheiten Formeln `kg m s^-2` und `m /s s * kg` in konvertiert `kg m/s^2` .</span><span class="sxs-lookup"><span data-stu-id="75dda-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="75dda-124">In Gleit Komma Ausdrücken verwenden Sie Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="75dda-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="75dda-125">Die Verwendung von Gleit Komma Zahlen zusammen mit zugeordneten Maßeinheiten fügt eine weitere Ebene der Typsicherheit hinzu und hilft dabei, die Fehler bei der Einheiten Übereinstimmung zu vermeiden, die bei der Verwendung von schwach typisierten Gleit Komma Zahlen in Formeln auftreten können.</span><span class="sxs-lookup"><span data-stu-id="75dda-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="75dda-126">Wenn Sie einen Gleit Komma Ausdruck schreiben, der Einheiten verwendet, müssen die Einheiten im Ausdruck Stimmen.</span><span class="sxs-lookup"><span data-stu-id="75dda-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="75dda-127">Literale können mit einer Einheitsformel in spitzen Klammern kommentiert werden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75dda-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="75dda-128">Zwischen der Zahl und der Spitze Klammer wird kein Leerzeichen eingefügt. Sie können jedoch ein literales Suffix wie `f` im folgenden Beispiel einschließen.</span><span class="sxs-lookup"><span data-stu-id="75dda-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="75dda-129">Eine solche Anmerkung ändert den Typ des Literals vom primitiven Typ (z. b `float` .) in einen dimensionierten Typ, wie z `float<cm>` . b. oder, in diesem Fall `float<miles/hour>` .</span><span class="sxs-lookup"><span data-stu-id="75dda-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="75dda-130">Eine Einheits Anmerkung von `<1>` gibt eine dimensionlose Menge an, und ihr Typ entspricht dem primitiven Typ ohne einen Unit-Parameter.</span><span class="sxs-lookup"><span data-stu-id="75dda-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="75dda-131">Der Typ einer Maßeinheit ist ein Gleit Komma Wert oder ein ganzzahliger ganzzahliger Typ mit einer zusätzlichen Einheiten Anmerkung, der in eckigen Klammern angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="75dda-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="75dda-132">Wenn Sie also den Typ einer Konvertierung von `g` (grams) in `kg` (Kilogramm) schreiben, beschreiben Sie die Typen wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75dda-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="75dda-133">Maßeinheiten werden für die Kompilierzeit-Einheiten Überprüfung verwendet, aber nicht in der Laufzeitumgebung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="75dda-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="75dda-134">Daher wirken Sie sich nicht auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="75dda-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="75dda-135">Maßeinheiten können auf jeden beliebigen Typ angewendet werden, nicht nur auf Gleit Komma Typen. Allerdings unterstützen nur Gleit Komma Typen, ganzzahlige ganzzahlige Typen und dezimale Typen dimensionierte Mengen.</span><span class="sxs-lookup"><span data-stu-id="75dda-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="75dda-136">Daher ist es nur sinnvoll, Maßeinheiten für die primitiven Typen und für Aggregate zu verwenden, die diese primitiven Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="75dda-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="75dda-137">Das folgende Beispiel veranschaulicht die Verwendung von Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="75dda-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="75dda-138">Im folgenden Codebeispiel wird veranschaulicht, wie Sie von einer dimensionlosen Gleit Komma Zahl in einen Wert mit einem Wert mit Dimensionswert konvertieren.</span><span class="sxs-lookup"><span data-stu-id="75dda-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="75dda-139">Sie multiplizieren einfach um 1,0 und wenden die Dimensionen auf 1,0 an.</span><span class="sxs-lookup"><span data-stu-id="75dda-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="75dda-140">Sie können dies in eine Funktion wie abstrahieren `degreesFahrenheit` .</span><span class="sxs-lookup"><span data-stu-id="75dda-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="75dda-141">Wenn Sie dimensionierte Werte an Funktionen übergeben, die wenig Gleit Komma Zahlen erwarten, müssen Sie außerdem die Einheiten abbrechen oder `float` mithilfe des-Operators in umwandeln `float` .</span><span class="sxs-lookup"><span data-stu-id="75dda-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="75dda-142">In diesem Beispiel Dividieren Sie durch `1.0<degC>` für die Argumente von, `printf` da eine `printf` dimensionlose Menge erwartet.</span><span class="sxs-lookup"><span data-stu-id="75dda-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="75dda-143">Die folgende Beispielsitzung zeigt die Ausgaben von und Eingaben für diesen Code.</span><span class="sxs-lookup"><span data-stu-id="75dda-143">The following example session shows the outputs from and inputs to this code.</span></span>

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="75dda-144">Verwenden generischer Einheiten</span><span class="sxs-lookup"><span data-stu-id="75dda-144">Using Generic Units</span></span>

<span data-ttu-id="75dda-145">Sie können generische Funktionen schreiben, die auf Daten mit zugeordneten Maßeinheiten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="75dda-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="75dda-146">Hierzu geben Sie einen Typ und eine generische Einheit als Typparameter an, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75dda-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="75dda-147">Erstellen von Aggregat Typen mit generischen Einheiten</span><span class="sxs-lookup"><span data-stu-id="75dda-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="75dda-148">Der folgende Code zeigt, wie ein Aggregattyp erstellt wird, der aus einzelnen Gleit Komma Werten besteht, die generische Einheiten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="75dda-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="75dda-149">Dadurch kann ein einzelner Typ erstellt werden, der mit einer Vielzahl von Einheiten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="75dda-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="75dda-150">Außerdem behalten generische Einheiten die Typsicherheit bei, indem sichergestellt wird, dass ein generischer Typ mit einem Satz von Einheiten einen anderen Typ aufweist als derselbe generische Typ mit einem anderen Satz von Einheiten.</span><span class="sxs-lookup"><span data-stu-id="75dda-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="75dda-151">Die Basis dieser Technik ist, dass das- `Measure` Attribut auf den Typparameter angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="75dda-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="75dda-152">Einheiten zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="75dda-152">Units at Runtime</span></span>

<span data-ttu-id="75dda-153">Maßeinheiten werden für die Überprüfung statischer Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="75dda-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="75dda-154">Wenn Gleit Komma Werte kompiliert werden, werden die Maßeinheiten beseitigt, sodass die Einheiten zur Laufzeit verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="75dda-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="75dda-155">Daher ist jeder Versuch, Funktionen zu implementieren, die von der Überprüfung der Einheiten zur Laufzeit abhängen, nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="75dda-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="75dda-156">Beispielsweise `ToString` ist die Implementierung einer Funktion zum Ausdrucken der Einheiten nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="75dda-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="75dda-157">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="75dda-157">Conversions</span></span>

<span data-ttu-id="75dda-158">Um einen Typ mit Einheiten (z. b. `float<'u>` ) in einen Typ zu konvertieren, der nicht über Einheiten verfügt, können Sie die Standard Konvertierungs Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="75dda-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="75dda-159">Beispielsweise können Sie verwenden, `float` um in einen-Wert zu konvertieren, `float` der keine-Einheiten enthält, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75dda-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="75dda-160">Um einen unitless-Wert in einen Wert mit Einheiten zu konvertieren, können Sie ihn mit einem Wert von 1 oder 1,0 multiplizieren, der mit den entsprechenden Einheiten kommentiert wird.</span><span class="sxs-lookup"><span data-stu-id="75dda-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="75dda-161">Zum Schreiben von Interoperabilitäts Ebenen gibt es jedoch auch einige explizite Funktionen, die Sie verwenden können, um unitlose Werte in Werte mit Einheiten zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="75dda-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="75dda-162">Diese befinden sich im Modul [FSharp. Core. LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) .</span><span class="sxs-lookup"><span data-stu-id="75dda-162">These are in the [FSharp.Core.LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) module.</span></span> <span data-ttu-id="75dda-163">Wenn Sie z. b. von einem-Paar `float` in einen konvertieren möchten `float<cm>` , verwenden Sie [floatwithmeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="75dda-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="75dda-164">Maßeinheiten in der F #-Kernbibliothek</span><span class="sxs-lookup"><span data-stu-id="75dda-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="75dda-165">Eine-Einheiten Bibliothek ist im- `FSharp.Data.UnitSystems.SI` Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75dda-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="75dda-166">Sie enthält SI-Einheiten in ihrer Symbol Form (z. b. `m` für die Verbrauchseinheit) im `UnitSymbols` untergeordneten Namespace und Ihren vollständigen Namen (z `meter` . b. für die Verbrauchseinheit) im `UnitNames` untergeordneten Namespace.</span><span class="sxs-lookup"><span data-stu-id="75dda-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="75dda-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75dda-167">See also</span></span>

- [<span data-ttu-id="75dda-168">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="75dda-168">F# Language Reference</span></span>](index.md)
