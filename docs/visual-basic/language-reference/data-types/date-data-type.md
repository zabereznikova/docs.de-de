---
title: Date-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 972df72874753a0f1213f3a4942468c59e3913ce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344025"
---
# <a name="date-data-type-visual-basic"></a><span data-ttu-id="90d4b-102">Date-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90d4b-102">Date Data Type (Visual Basic)</span></span>

<span data-ttu-id="90d4b-103">Enthält IEEE-64-Bit(8-Byte)-Werte, die Datumsangaben im Bereich vom 1. Januar des Jahres 0001 bis zum 31. Dezember des Jahres 9999 und Uhrzeiten von 00:00:00 Uhr (Mitternacht) bis 23:59:59.9999999 Uhr darstellen.</span><span class="sxs-lookup"><span data-stu-id="90d4b-103">Holds IEEE 64-bit (8-byte) values that represent dates ranging from January 1 of the year 0001 through December 31 of the year 9999, and times from 12:00:00 AM (midnight) through 11:59:59.9999999 PM.</span></span> <span data-ttu-id="90d4b-104">Jedes Inkrement stellt 100 Nanosekunden verstrichener Zeit seit Beginn des 1. Januar des Jahres 1 im gregorianischen Kalender dar.</span><span class="sxs-lookup"><span data-stu-id="90d4b-104">Each increment represents 100 nanoseconds of elapsed time since the beginning of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="90d4b-105">Der maximale Wert stellt 100 Nanosekunden vor Beginn des 1. Januar des Jahres 10000 dar.</span><span class="sxs-lookup"><span data-stu-id="90d4b-105">The maximum value represents 100 nanoseconds before the beginning of January 1 of the year 10000.</span></span>

## <a name="remarks"></a><span data-ttu-id="90d4b-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90d4b-106">Remarks</span></span>

<span data-ttu-id="90d4b-107">Verwenden Sie den `Date`-Datentyp, um Datumswerte, Uhrzeitwerte oder Datums-und Uhrzeitwerte einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="90d4b-107">Use the `Date` data type to contain date values, time values, or date and time values.</span></span>

<span data-ttu-id="90d4b-108">Der Standardwert von `Date` ist 0:00:00 (Mitternacht) am 1. Januar 0001.</span><span class="sxs-lookup"><span data-stu-id="90d4b-108">The default value of `Date` is 0:00:00 (midnight) on January 1, 0001.</span></span>

<span data-ttu-id="90d4b-109">Sie erhalten das aktuelle Datum und die aktuelle Uhrzeit aus der <xref:Microsoft.VisualBasic.DateAndTime>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="90d4b-109">You can get the current date and time from the <xref:Microsoft.VisualBasic.DateAndTime> class.</span></span>

## <a name="format-requirements"></a><span data-ttu-id="90d4b-110">Formatanforderungen</span><span class="sxs-lookup"><span data-stu-id="90d4b-110">Format Requirements</span></span>

<span data-ttu-id="90d4b-111">Sie müssen einen `Date`-Literal zwischen Nummernzeichen (`# #`) einschließen.</span><span class="sxs-lookup"><span data-stu-id="90d4b-111">You must enclose a `Date` literal within number signs (`# #`).</span></span> <span data-ttu-id="90d4b-112">Sie müssen den Datumswert im Format M/T/JJJJ angeben, z. B. `#5/31/1993#`, oder JJJJ-MM-TT, z. B. `#1993-5-31#`.</span><span class="sxs-lookup"><span data-stu-id="90d4b-112">You must specify the date value in the format M/d/yyyy, for example `#5/31/1993#`, or yyyy-MM-dd, for example `#1993-5-31#`.</span></span> <span data-ttu-id="90d4b-113">Wenn Sie das Jahr zuerst angeben, können Sie Schrägstriche verwenden.</span><span class="sxs-lookup"><span data-stu-id="90d4b-113">You can use slashes when specifying the year first.</span></span>  <span data-ttu-id="90d4b-114">Dies gilt unabhängig vom Gebietsschema und den Formateinstellungen für Datum und Uhrzeit Ihres Computers.</span><span class="sxs-lookup"><span data-stu-id="90d4b-114">This requirement is independent of your locale and your computer's date and time format settings.</span></span>

<span data-ttu-id="90d4b-115">Der Grund für diese Einschränkung ist, dass sich die Bedeutung des Codes nicht je nach dem Gebietsschema, in dem die Anwendung ausgeführt wird, ändern soll.</span><span class="sxs-lookup"><span data-stu-id="90d4b-115">The reason for this restriction is that the meaning of your code should never change depending on the locale in which your application is running.</span></span> <span data-ttu-id="90d4b-116">Angenommen, Sie möchten ein `Date`-Literal von `#3/4/1998#` als vordefinierten Code aufnehmen und die Bedeutung 4. März 1998 festlegen.</span><span class="sxs-lookup"><span data-stu-id="90d4b-116">Suppose you hard-code a `Date` literal of `#3/4/1998#` and intend it to mean March 4, 1998.</span></span> <span data-ttu-id="90d4b-117">In einem Gebietsschema, das MM/TT/JJJJ verwendet, wird 3/4/1998 wie gewünscht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="90d4b-117">In a locale that uses mm/dd/yyyy, 3/4/1998 compiles as you intend.</span></span> <span data-ttu-id="90d4b-118">But suppose you deploy your application in many countries/regions.</span><span class="sxs-lookup"><span data-stu-id="90d4b-118">But suppose you deploy your application in many countries/regions.</span></span> <span data-ttu-id="90d4b-119">In einem Gebietsschema, das TT/MM/JJJJ verwendet, würde das als vordefinierter Code aufgenommene Literal als 3. April 1998 kompiliert.</span><span class="sxs-lookup"><span data-stu-id="90d4b-119">In a locale that uses dd/mm/yyyy, your hard-coded literal would compile to April 3, 1998.</span></span> <span data-ttu-id="90d4b-120">In einem Gebietsschema, das JJJJ/MM/TT verwendet, wäre das Literal ungültig (1998. April 0003) und würde einen Compilerfehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="90d4b-120">In a locale that uses yyyy/mm/dd, the literal would be invalid (April 1998, 0003) and cause a compiler error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="90d4b-121">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="90d4b-121">Workarounds</span></span>

<span data-ttu-id="90d4b-122">Um ein `Date`-Literal in das Format Ihres Gebietsschemas oder in ein benutzerdefiniertes Format zu konvertieren, müssen Sie das Literal für die <xref:Microsoft.VisualBasic.Strings.Format%2A>-Funktion bereitstellen und entweder ein vordefiniertes oder ein benutzerdefiniertes Datumsformat angeben.</span><span class="sxs-lookup"><span data-stu-id="90d4b-122">To convert a `Date` literal to the format of your locale, or to a custom format, supply the literal to the <xref:Microsoft.VisualBasic.Strings.Format%2A> function, specifying either a predefined or user-defined date format.</span></span> <span data-ttu-id="90d4b-123">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="90d4b-123">The following example demonstrates this.</span></span>

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

<span data-ttu-id="90d4b-124">Alternativ können Sie einen der überladenen Konstruktoren der <xref:System.DateTime>-Struktur verwenden, um einen Datums- und Uhrzeitwert zu assemblieren.</span><span class="sxs-lookup"><span data-stu-id="90d4b-124">Alternatively, you can use one of the overloaded constructors of the <xref:System.DateTime> structure to assemble a date and time value.</span></span> <span data-ttu-id="90d4b-125">Im folgenden Beispiel wird ein Wert für den 31. Mai 1993 um 12:14 Uhr nachmittags erstellt.</span><span class="sxs-lookup"><span data-stu-id="90d4b-125">The following example creates a value to represent May 31, 1993 at 12:14 in the afternoon.</span></span>

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a><span data-ttu-id="90d4b-126">Stundenformat</span><span class="sxs-lookup"><span data-stu-id="90d4b-126">Hour Format</span></span>

<span data-ttu-id="90d4b-127">Sie können den Zeitwert im 12- oder 24-Stunden-Format angeben, z. B. `#1:15:30 PM#` oder `#13:15:30#`.</span><span class="sxs-lookup"><span data-stu-id="90d4b-127">You can specify the time value in either 12-hour or 24-hour format, for example `#1:15:30 PM#` or `#13:15:30#`.</span></span> <span data-ttu-id="90d4b-128">Wenn Sie allerdings weder Minuten noch Sekunden angeben, müssen Sie AM oder PM angeben.</span><span class="sxs-lookup"><span data-stu-id="90d4b-128">However, if you do not specify either the minutes or the seconds, you must specify AM or PM.</span></span>

## <a name="date-and-time-defaults"></a><span data-ttu-id="90d4b-129">Standardwerte für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="90d4b-129">Date and Time Defaults</span></span>

<span data-ttu-id="90d4b-130">Wenn Sie in einem Datum-/Uhrzeit-Literal kein Datum angeben, legt Visual Basic den Datumsteil des Werts auf den 1. Januar 0001 fest.</span><span class="sxs-lookup"><span data-stu-id="90d4b-130">If you do not include a date in a date/time literal, Visual Basic sets the date part of the value to January 1, 0001.</span></span> <span data-ttu-id="90d4b-131">Wenn Sie in einem Datum-/Uhrzeit-Literal keine Uhrzeit angeben, legt Visual Basic den Uhrzeitteil des Werts auf den Beginn des Tages, d. h. Mitternacht (0:00:00) fest.</span><span class="sxs-lookup"><span data-stu-id="90d4b-131">If you do not include a time in a date/time literal, Visual Basic sets the time part of the value to the start of the day, that is, midnight (0:00:00).</span></span>

## <a name="type-conversions"></a><span data-ttu-id="90d4b-132">Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="90d4b-132">Type Conversions</span></span>

<span data-ttu-id="90d4b-133">Beim Konvertieren eines `Date`-Werts in den `String`-Typ, gibt Visual Basic das Datum gemäß dem kurzen Datumsformat wieder, das vom Laufzeitgebietsschema angegeben wird, und die Uhrzeit gemäß dem Zeitformat (entweder 12- oder 24-Stunden-Format), das vom Laufzeitgebietsschema angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="90d4b-133">If you convert a `Date` value to the `String` type, Visual Basic renders the date according to the short date format specified by the run-time locale, and it renders the time according to the time format (either 12-hour or 24-hour) specified by the run-time locale.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="90d4b-134">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="90d4b-134">Programming Tips</span></span>

- <span data-ttu-id="90d4b-135">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="90d4b-135">**Interop Considerations.**</span></span> <span data-ttu-id="90d4b-136">Wenn Sie Komponenten anbinden, die nicht für .NET Framework geschrieben wurden (z. B. Automatisierungs- oder COM-Objekte), müssen Sie beachten, dass Datums-/Uhrzeittypen in anderen Umgebungen nicht zum `Date`-Typ von Visual Basic kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="90d4b-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that date/time types in other environments are not compatible with the Visual Basic `Date` type.</span></span> <span data-ttu-id="90d4b-137">Wenn Sie ein Datums-/Uhrzeitargument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic-Code als `Double` und nicht als `Date`, und verwenden Sie die Konvertierungsmethoden <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> und <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90d4b-137">If you are passing a date/time argument to such a component, declare it as `Double` instead of `Date` in your new Visual Basic code, and use the conversion methods <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="90d4b-138">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="90d4b-138">**Type Characters.**</span></span> <span data-ttu-id="90d4b-139">`Date` has no literal type character or identifier type character.</span><span class="sxs-lookup"><span data-stu-id="90d4b-139">`Date` has no literal type character or identifier type character.</span></span> <span data-ttu-id="90d4b-140">Der Compiler behandelt jedoch Literale, die in Nummernzeichen (`# #`) eingeschlossen sind, als `Date`.</span><span class="sxs-lookup"><span data-stu-id="90d4b-140">However, the compiler treats literals enclosed within number signs (`# #`) as `Date`.</span></span>

- <span data-ttu-id="90d4b-141">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="90d4b-141">**Framework Type.**</span></span> <span data-ttu-id="90d4b-142">Der entsprechende Typ in .NET Framework ist die <xref:System.DateTime?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="90d4b-142">The corresponding type in the .NET Framework is the <xref:System.DateTime?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="90d4b-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90d4b-143">Example</span></span>

<span data-ttu-id="90d4b-144">Eine Variable oder Konstante des `Date`-Datentyps enthält das Datum und die Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="90d4b-144">A variable or constant of the `Date` data type holds both the date and the time.</span></span> <span data-ttu-id="90d4b-145">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="90d4b-145">The following example illustrates this.</span></span>

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a><span data-ttu-id="90d4b-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90d4b-146">See also</span></span>

- <xref:System.DateTime?displayProperty=nameWithType>
- [<span data-ttu-id="90d4b-147">Datentypen</span><span class="sxs-lookup"><span data-stu-id="90d4b-147">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="90d4b-148">Standardformatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="90d4b-148">Standard Date and Time Format Strings</span></span>](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [<span data-ttu-id="90d4b-149">Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="90d4b-149">Custom Date and Time Format Strings</span></span>](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [<span data-ttu-id="90d4b-150">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="90d4b-150">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="90d4b-151">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="90d4b-151">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="90d4b-152">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="90d4b-152">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
