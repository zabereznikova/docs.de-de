---
title: Tabelle zur Formatierung numerischer Ergebnisse – C#-Referenz
ms.custom: seodec18
description: Erfahren Sie mehr über numerische Standardformatzeichenfolgen in C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 0f2b5bc54a0e9055d64a95dc229eaadf66687b43
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421971"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="2e20d-103">Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2e20d-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="2e20d-104">Die folgende Tabelle weist die unterstützten Formatbezeichner zum Formatieren von numerischen Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="2e20d-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="2e20d-105">Das formatierte Ergebnis in der letzten Spalte entspricht dem „en-US“ <xref:System.Globalization.CultureInfo>.</span><span class="sxs-lookup"><span data-stu-id="2e20d-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="2e20d-106">Formatbezeichner</span><span class="sxs-lookup"><span data-stu-id="2e20d-106">Format specifier</span></span>|<span data-ttu-id="2e20d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e20d-107">Description</span></span>|<span data-ttu-id="2e20d-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2e20d-108">Examples</span></span>|<span data-ttu-id="2e20d-109">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2e20d-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="2e20d-110">C oder c</span><span class="sxs-lookup"><span data-stu-id="2e20d-110">C or c</span></span>|<span data-ttu-id="2e20d-111">Währung</span><span class="sxs-lookup"><span data-stu-id="2e20d-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="2e20d-112">$2.50</span><span class="sxs-lookup"><span data-stu-id="2e20d-112">$2.50</span></span><br /><br /> <span data-ttu-id="2e20d-113">($2.50)</span><span class="sxs-lookup"><span data-stu-id="2e20d-113">($2.50)</span></span>|  
|<span data-ttu-id="2e20d-114">D oder d</span><span class="sxs-lookup"><span data-stu-id="2e20d-114">D or d</span></span>|<span data-ttu-id="2e20d-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="2e20d-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="2e20d-116">00025</span><span class="sxs-lookup"><span data-stu-id="2e20d-116">00025</span></span>|  
|<span data-ttu-id="2e20d-117">E oder e</span><span class="sxs-lookup"><span data-stu-id="2e20d-117">E or e</span></span>|<span data-ttu-id="2e20d-118">Exponentiell</span><span class="sxs-lookup"><span data-stu-id="2e20d-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="2e20d-119">2.50E + 005</span><span class="sxs-lookup"><span data-stu-id="2e20d-119">2.50E+005</span></span>|  
|<span data-ttu-id="2e20d-120">F oder f</span><span class="sxs-lookup"><span data-stu-id="2e20d-120">F or f</span></span>|<span data-ttu-id="2e20d-121">Festkomma</span><span class="sxs-lookup"><span data-stu-id="2e20d-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="2e20d-122">2.50</span><span class="sxs-lookup"><span data-stu-id="2e20d-122">2.50</span></span><br /><br /> <span data-ttu-id="2e20d-123">3</span><span class="sxs-lookup"><span data-stu-id="2e20d-123">3</span></span>|  
|<span data-ttu-id="2e20d-124">G oder g</span><span class="sxs-lookup"><span data-stu-id="2e20d-124">G or g</span></span>|<span data-ttu-id="2e20d-125">Allgemein</span><span class="sxs-lookup"><span data-stu-id="2e20d-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="2e20d-126">2.5</span><span class="sxs-lookup"><span data-stu-id="2e20d-126">2.5</span></span>|  
|<span data-ttu-id="2e20d-127">N oder n</span><span class="sxs-lookup"><span data-stu-id="2e20d-127">N or n</span></span>|<span data-ttu-id="2e20d-128">Numeric</span><span class="sxs-lookup"><span data-stu-id="2e20d-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="2e20d-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="2e20d-129">2,500,000.00</span></span>|  
|<span data-ttu-id="2e20d-130">P oder p</span><span class="sxs-lookup"><span data-stu-id="2e20d-130">P or p</span></span>|<span data-ttu-id="2e20d-131">Prozent</span><span class="sxs-lookup"><span data-stu-id="2e20d-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="2e20d-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="2e20d-132">25.00%</span></span>|  
|<span data-ttu-id="2e20d-133">R oder r</span><span class="sxs-lookup"><span data-stu-id="2e20d-133">R or r</span></span>|<span data-ttu-id="2e20d-134">Schleife</span><span class="sxs-lookup"><span data-stu-id="2e20d-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="2e20d-135">2.5</span><span class="sxs-lookup"><span data-stu-id="2e20d-135">2.5</span></span>|  
|<span data-ttu-id="2e20d-136">X oder x</span><span class="sxs-lookup"><span data-stu-id="2e20d-136">X or x</span></span>|<span data-ttu-id="2e20d-137">Hexadezimal</span><span class="sxs-lookup"><span data-stu-id="2e20d-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="2e20d-138">FA</span><span class="sxs-lookup"><span data-stu-id="2e20d-138">FA</span></span><br /><br /> <span data-ttu-id="2e20d-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="2e20d-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="2e20d-140">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="2e20d-140">Remarks</span></span>

<span data-ttu-id="2e20d-141">Ein Formatbezeichner wird zum Erstellen einer Formatzeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e20d-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="2e20d-142">Die Formatzeichenfolge weist die folgende Form auf: `Axx`, wobei</span><span class="sxs-lookup"><span data-stu-id="2e20d-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="2e20d-143">`A` der Formatbezeichner ist, der die Art der Formatierung steuert, die auf den numerischen Wert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e20d-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="2e20d-144">`xx` der Genauigkeitsbezeichner ist, der sich auf die Anzahl der Stellen in der formatierten Ausgabe auswirkt.</span><span class="sxs-lookup"><span data-stu-id="2e20d-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="2e20d-145">Der Wert der Genauigkeitsangabe liegt im Bereich 0–99.</span><span class="sxs-lookup"><span data-stu-id="2e20d-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="2e20d-146">Die Dezimal- („D“ oder „d“) und Hexadezimal- („X“ oder „x“) Formatbezeichner werden nur für integrale Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e20d-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="2e20d-147">Der Round-Trip-Formatbezeichner („R“ oder „r“) wird nur für die Typen <xref:System.Single>, <xref:System.Double> und <xref:System.Numerics.BigInteger> unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e20d-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="2e20d-148">Standardmäßige Zahlenformatzeichenfolgen werden von Folgendem unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2e20d-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="2e20d-149">Einigen Überladungen der `ToString`-Methode aller numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="2e20d-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="2e20d-150">Sie können z.B. eine numerische Formatzeichenfolge an die <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType>-Methode und <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="2e20d-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="2e20d-151">Beispielsweise das [zusammengesetzte Formatierungsfeature](../../../standard/base-types/composite-formatting.md) von .NET, das von der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2e20d-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="2e20d-152">[Interpolierte Zeichenfolgen](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="2e20d-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="2e20d-153">Weitere Informationen finden Sie unter [Numerische Standard-Formatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="2e20d-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e20d-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e20d-154">See also</span></span>

- [<span data-ttu-id="2e20d-155">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2e20d-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2e20d-156">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2e20d-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2e20d-157">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="2e20d-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="2e20d-158">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="2e20d-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="2e20d-159">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="2e20d-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="2e20d-160">string</span><span class="sxs-lookup"><span data-stu-id="2e20d-160">string</span></span>](string.md)
