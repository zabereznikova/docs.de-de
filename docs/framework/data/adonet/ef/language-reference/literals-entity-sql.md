---
title: Literale (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
ms.openlocfilehash: 4402f4c6ee38432a0f606e39dd4a18639076ce04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161775"
---
# <a name="literals-entity-sql"></a><span data-ttu-id="efae3-102">Literale (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="efae3-102">Literals (Entity SQL)</span></span>

<span data-ttu-id="efae3-103">In diesem Thema wird die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Unterstützung für Literale beschrieben.</span><span class="sxs-lookup"><span data-stu-id="efae3-103">This topic describes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] support for literals.</span></span>  
  
## <a name="null"></a><span data-ttu-id="efae3-104">Null</span><span class="sxs-lookup"><span data-stu-id="efae3-104">Null</span></span>  

 <span data-ttu-id="efae3-105">Das NULL-Literal wird verwendet, um für einen beliebigen Typ den Wert Null darzustellen.</span><span class="sxs-lookup"><span data-stu-id="efae3-105">The null literal is used to represent the value null for any type.</span></span> <span data-ttu-id="efae3-106">Das NULL-Literal ist mit jedem Typ kompatibel.</span><span class="sxs-lookup"><span data-stu-id="efae3-106">A null literal is compatible with any type.</span></span>  
  
 <span data-ttu-id="efae3-107">Typisierte Nullen können durch Umwandlung eines NULL-Literals erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="efae3-107">Typed nulls can be created by a cast over a null literal.</span></span> <span data-ttu-id="efae3-108">Weitere Informationen finden Sie unter [Cast](cast-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="efae3-108">For more information, see [CAST](cast-entity-sql.md).</span></span>  
  
 <span data-ttu-id="efae3-109">Regeln für die Verwendung von freien Gleit Komma-null-literalen finden Sie unter [NULL-Literale und Typrückschluss](null-literals-and-type-inference-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="efae3-109">For rules about where free floating null literals can be used, see [Null Literals and Type Inference](null-literals-and-type-inference-entity-sql.md).</span></span>  
  
## <a name="boolean"></a><span data-ttu-id="efae3-110">Boolean</span><span class="sxs-lookup"><span data-stu-id="efae3-110">Boolean</span></span>  

 <span data-ttu-id="efae3-111">Boolesche Literale werden durch die Schlüsselwörter `true` und `false` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="efae3-111">Boolean literals are represented by the keywords `true` and `false`.</span></span>  
  
## <a name="integer"></a><span data-ttu-id="efae3-112">Integer</span><span class="sxs-lookup"><span data-stu-id="efae3-112">Integer</span></span>  

 <span data-ttu-id="efae3-113">Ganzzahlliterale können vom Typ <xref:System.Int32> oder <xref:System.Int64> sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-113">Integer literals can be of type <xref:System.Int32> or <xref:System.Int64>.</span></span> <span data-ttu-id="efae3-114">Ein <xref:System.Int32>-Literal ist eine Folge numerischer Zeichen.</span><span class="sxs-lookup"><span data-stu-id="efae3-114">An <xref:System.Int32> literal is a series of numeric characters.</span></span> <span data-ttu-id="efae3-115">Ein <xref:System.Int64>-Literal ist eine Folge numerischer Zeichen, auf die der Großbuchstabe "L" folgt.</span><span class="sxs-lookup"><span data-stu-id="efae3-115">An <xref:System.Int64> literal is series of numeric characters followed by an uppercase L.</span></span>  
  
## <a name="decimal"></a><span data-ttu-id="efae3-116">Decimal</span><span class="sxs-lookup"><span data-stu-id="efae3-116">Decimal</span></span>  

 <span data-ttu-id="efae3-117">Eine Festkommazahl (dezimal) besteht aus einer Reihe von numerischen Zeichen, einem Punkt (.) und einer weiteren Folge numerischer Zeichen, auf die der Großbuchstabe "M" folgt.</span><span class="sxs-lookup"><span data-stu-id="efae3-117">A fixed-point number (decimal) is a series of numeric characters, a dot (.) and another series of numeric characters followed by an uppercase "M".</span></span>  
  
## <a name="float-double"></a><span data-ttu-id="efae3-118">Float, Double</span><span class="sxs-lookup"><span data-stu-id="efae3-118">Float, Double</span></span>  

 <span data-ttu-id="efae3-119">Eine Gleitkommazahl mit doppelter Genauigkeit ist eine Reihe von numerischen Zeichen, einem Punkt (.) und einer weiteren Folge numerischer Zeichen, auf die ein Exponent folgen kann.</span><span class="sxs-lookup"><span data-stu-id="efae3-119">A double-precision floating point number is a series of numeric characters, a dot (.) and another series of numeric characters possibly followed by an exponent.</span></span> <span data-ttu-id="efae3-120">Eine Gleitkommazahl mit einfacher Genauigkeit (oder "Float") besteht aus einer Gleitkommazahlensyntax mit doppelter Genauigkeit, auf die der Kleinbuchstabe "f" folgt.</span><span class="sxs-lookup"><span data-stu-id="efae3-120">A single-precisions floating point number (or float) is a double-precision floating point number syntax followed by the lowercase f.</span></span>  
  
## <a name="string"></a><span data-ttu-id="efae3-121">String</span><span class="sxs-lookup"><span data-stu-id="efae3-121">String</span></span>  

 <span data-ttu-id="efae3-122">Ein String ist eine in Anführungszeichen eingeschlossene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="efae3-122">A string is a series of characters enclosed in quote marks.</span></span> <span data-ttu-id="efae3-123">Die Zeichenfolge kann entweder in einfache (`'`) oder doppelte (") Anführungszeichen eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-123">Quotes can be either both single-quotes (`'`) or both double-quotes (").</span></span> <span data-ttu-id="efae3-124">Zeichenfolgenliterale sind entweder Unicode oder Nicht-Unicode.</span><span class="sxs-lookup"><span data-stu-id="efae3-124">Character string literals can be either Unicode or non-Unicode.</span></span> <span data-ttu-id="efae3-125">Stellen Sie dem Literal ein groß geschriebenes "N" voran, um ein Zeichenfolgeliteral als Unicode zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="efae3-125">To declare a character string literal as Unicode, prefix the literal with an uppercase "N".</span></span> <span data-ttu-id="efae3-126">Standardmäßig werden Nicht-Unicode-Zeichenfolgenliterale verwendet.</span><span class="sxs-lookup"><span data-stu-id="efae3-126">The default is non-Unicode character string literals.</span></span> <span data-ttu-id="efae3-127">Zwischen "N" und dem Inhalt des Zeichenfolgenliterals dürfen keine Leerzeichen stehen, und "N" muss ein Großbuchstabe sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-127">There can be no spaces between the N and the string literal payload, and the N must be uppercase.</span></span>  
  
```sql  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a><span data-ttu-id="efae3-128">Datetime</span><span class="sxs-lookup"><span data-stu-id="efae3-128">DateTime</span></span>  

 <span data-ttu-id="efae3-129">Ein datetime-Literal ist unabhängig vom Gebietsschema und besteht aus einem Datums- und einem Uhrzeitteil.</span><span class="sxs-lookup"><span data-stu-id="efae3-129">A datetime literal is independent of locale and is composed of a date part and a time part.</span></span> <span data-ttu-id="efae3-130">Datums- und einem Uhrzeitteile sind obligatorisch, und es gibt keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="efae3-130">Both date and time parts are mandatory and there are no default values.</span></span>  
  
 <span data-ttu-id="efae3-131">Der Datums Teil muss folgendes Format aufweisen: `YYYY` - `MM` - `DD` , wobei `YYYY` ein vierstelliger Jahreswert zwischen 0001 und 9999 ist, `MM` der Monat zwischen 1 und 12 ist und `DD` der Wert für den Tag ist, der für den angegebenen Monat gültig ist `MM` .</span><span class="sxs-lookup"><span data-stu-id="efae3-131">The date part must have the format: `YYYY`-`MM`-`DD`, where `YYYY` is a four digit year value between 0001 and 9999, `MM` is the month between 1 and 12 and `DD` is the day value that is valid for the given month `MM`.</span></span>  
  
 <span data-ttu-id="efae3-132">Der Zeitteil muss folgendes Format aufweisen: `HH`:`MM`[:`SS`[.fffffff]], wobei `HH` ein Stundenwert zwischen 0 und 23, `MM` ein Minutenwert zwischen 0 und einschließlich 59, `SS` ein Sekundenwert zwischen 0 und einschließlich 59 und fffffff der Wert für die Sekundenbruchteile zwischen 0 und 9999999 ist.</span><span class="sxs-lookup"><span data-stu-id="efae3-132">The time part must have the format: `HH`:`MM`[:`SS`[.fffffff]], where `HH` is the hour value between 0 and 23, `MM` is the minute value between 0 and 59, `SS` is the second value between 0 and 59 and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="efae3-133">Alle Wertbereiche sind inklusive.</span><span class="sxs-lookup"><span data-stu-id="efae3-133">All value ranges are inclusive.</span></span> <span data-ttu-id="efae3-134">Der Wert für die Sekundenbruchteile ist optional.</span><span class="sxs-lookup"><span data-stu-id="efae3-134">Fractional seconds are optional.</span></span> <span data-ttu-id="efae3-135">Der Wert für die Sekunden ist optional, außer wenn Sekundenbruchteile angegeben werden. In diesem Fall ist der Sekundenwert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="efae3-135">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="efae3-136">Werden keine Werte für Sekunden oder Sekundenbruchteile angegeben, wird als Standardwert 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="efae3-136">When seconds or fractional seconds are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="efae3-137">Zwischen dem DATETIME-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-137">There can be any number of spaces between the DATETIME symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a><span data-ttu-id="efae3-138">Time</span><span class="sxs-lookup"><span data-stu-id="efae3-138">Time</span></span>  

 <span data-ttu-id="efae3-139">Das time-Literal ist unabhängig vom Gebietsschema und besteht ausschließlich aus einem Uhrzeitteil.</span><span class="sxs-lookup"><span data-stu-id="efae3-139">A time literal is independent of locale and composed of a time part only.</span></span> <span data-ttu-id="efae3-140">Der Uhrzeitteil ist zwingend erforderlich, und hierfür ist kein Standardwert vorhanden.</span><span class="sxs-lookup"><span data-stu-id="efae3-140">The time part is mandatory and there is no default value.</span></span> <span data-ttu-id="efae3-141">Der Uhrzeitteil muss folgendes Format aufweisen: HH:MM[:SS[.fffffff]], wobei "HH" ein Stundenwert zwischen 0 und 23, "MM" ein Minutenwert zwischen 0 und 59, "SS" ein Sekundenwert zwischen 0 und einschließlich 59 und "fffffff" der Wert für die Sekundenbruchteile zwischen 0 und 9999999 ist.</span><span class="sxs-lookup"><span data-stu-id="efae3-141">It must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the second fraction value between 0 and 9999999.</span></span> <span data-ttu-id="efae3-142">Alle Wertbereiche sind inklusive.</span><span class="sxs-lookup"><span data-stu-id="efae3-142">All value ranges are inclusive.</span></span> <span data-ttu-id="efae3-143">Der Wert für die Sekundenbruchteile ist optional.</span><span class="sxs-lookup"><span data-stu-id="efae3-143">Fractional seconds are optional.</span></span> <span data-ttu-id="efae3-144">Der Wert für die Sekunden ist optional, außer wenn Sekundenbruchteile angegeben werden. In diesem Fall ist der Sekundenwert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="efae3-144">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="efae3-145">Werden keine Werte für Sekunden oder Sekundenbruchteile angegeben, wird als Standardwert 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="efae3-145">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="efae3-146">Zwischen dem TIME-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-146">There can be any number of spaces between the TIME symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a><span data-ttu-id="efae3-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="efae3-147">DateTimeOffset</span></span>  

 <span data-ttu-id="efae3-148">Ein datetimeoffset-Literal ist unabhängig vom Gebietsschema und besteht aus einem Datums-, einem Uhrzeit- und einem Offsetteil.</span><span class="sxs-lookup"><span data-stu-id="efae3-148">A datetimeoffset literal is independent of locale and composed of a date part, a time part, and an offset part.</span></span> <span data-ttu-id="efae3-149">Alle Datums-, Uhrzeit- und Offsetteile sind obligatorisch, und es gibt keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="efae3-149">All date, time, and offset parts are mandatory and there are no default values.</span></span> <span data-ttu-id="efae3-150">Der Datumsteil muss folgendes Format aufweisen: JJJJ-MM-TT, wobei "JJJJ" eine Jahresangabe mit vier Ziffern zwischen 0001 und 9999, "MM" der Wert für den Monat zwischen 1 und 12 und "DD" der Wert für den Tag ist, der für den gegebenen Monat gültig ist.</span><span class="sxs-lookup"><span data-stu-id="efae3-150">The date part must have the format YYYY-MM-DD, where YYYY is a four digit year value between 0001 and 9999, MM is the month between 1 and 12, and DD is the day value that is valid for the given month.</span></span> <span data-ttu-id="efae3-151">Der Uhrzeitteil muss folgendes Format aufweisen: HH:MM[:SS[.fffffff]], wobei "HH" ein Stundenwert zwischen 0 und 23, "MM" ein Minutenwert zwischen 0 und 59, "SS" ein Sekundenwert zwischen 0 und 59 und "fffffff" ein Wert für die Sekundenbruchteile zwischen 0 und 9999999 ist.</span><span class="sxs-lookup"><span data-stu-id="efae3-151">The time part must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="efae3-152">Alle Wertbereiche sind inklusive.</span><span class="sxs-lookup"><span data-stu-id="efae3-152">All value ranges are inclusive.</span></span> <span data-ttu-id="efae3-153">Der Wert für die Sekundenbruchteile ist optional.</span><span class="sxs-lookup"><span data-stu-id="efae3-153">Fractional seconds are optional.</span></span> <span data-ttu-id="efae3-154">Der Wert für die Sekunden ist optional, außer wenn Sekundenbruchteile angegeben werden. In diesem Fall ist der Sekundenwert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="efae3-154">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="efae3-155">Werden keine Werte für Sekunden oder Sekundenbruchteile angegeben, wird als Standardwert 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="efae3-155">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span> <span data-ttu-id="efae3-156">Der Offset Teil muss das Format {+&#124;-} hh: mm aufweisen, wobei HH und mm die gleiche Bedeutung wie im Zeit Teil haben.</span><span class="sxs-lookup"><span data-stu-id="efae3-156">The offset part must have the format {+&#124;-}HH:MM, where HH and MM have the same meaning as in the time part.</span></span> <span data-ttu-id="efae3-157">Der Wert für den Offsetbereich muss jedoch zwischen -14:00 und +14:00 liegen.</span><span class="sxs-lookup"><span data-stu-id="efae3-157">The range of the offset, however, must be between -14:00 and + 14:00</span></span>  
  
 <span data-ttu-id="efae3-158">Zwischen dem DATETIMEOFFSET-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-158">There can be any number of spaces between the DATETIMEOFFSET symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
> <span data-ttu-id="efae3-159">Ein gültiger Entity SQL-Literalwert kann aus den unterstützten Bereichen für CLR oder die Datenquelle herausfallen.</span><span class="sxs-lookup"><span data-stu-id="efae3-159">A valid Entity SQL literal value can fall outside the supported ranges for CLR or the data source.</span></span> <span data-ttu-id="efae3-160">Dies könnte zu einer Ausnahme führen.</span><span class="sxs-lookup"><span data-stu-id="efae3-160">This might result in an exception</span></span>  
  
## <a name="binary"></a><span data-ttu-id="efae3-161">Binary</span><span class="sxs-lookup"><span data-stu-id="efae3-161">Binary</span></span>  

 <span data-ttu-id="efae3-162">Ein binäres Zeichenfolgenliteral ist eine in einfache Anführungszeichen eingeschlossene Folge von Hexadezimalziffern, die auf das Binary-Schlüsselwort oder das Symbol `X` oder `x` folgt.</span><span class="sxs-lookup"><span data-stu-id="efae3-162">A binary string literal is a sequence of hexadecimal digits delimited by single quotes following the keyword binary or the shortcut symbol `X` or `x`.</span></span> <span data-ttu-id="efae3-163">Beim Symbol `X`wird die Groß- und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="efae3-163">The shortcut symbol `X` is case insensitive.</span></span> <span data-ttu-id="efae3-164">Zwischen dem `binary`-Schlüsselwort und dem binären Zeichenfolgenwert können null oder mehr Leerzeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="efae3-164">A zero or more spaces are allowed between the keyword `binary` and the binary string value.</span></span>  
  
 <span data-ttu-id="efae3-165">Bei den Hexadezimalzeichen wird außerdem die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="efae3-165">Hexadecimal characters are also case insensitive.</span></span> <span data-ttu-id="efae3-166">Wenn das Literal aus einer ungeraden Anzahl von Hexadezimalziffern zusammengesetzt ist, wird das Literal zu einer geraden Anzahl von Hexadezimalziffern aufgefüllt, indem dem Literal die Hexadezimalziffer 0 vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="efae3-166">If the literal is composed of an odd number of hexadecimal digits, the literal will be aligned to the next even hexadecimal digit by prefixing the literal with a hexadecimal zero digit.</span></span> <span data-ttu-id="efae3-167">Für die Größe von binären Zeichenfolgen gibt es keine formale Beschränkung.</span><span class="sxs-lookup"><span data-stu-id="efae3-167">There is no formal limit on the size of the binary string.</span></span>  
  
```sql  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a><span data-ttu-id="efae3-168">Guid</span><span class="sxs-lookup"><span data-stu-id="efae3-168">Guid</span></span>  

 <span data-ttu-id="efae3-169">Ein `GUID`-Literal stellt einen global eindeutigen Bezeichner dar.</span><span class="sxs-lookup"><span data-stu-id="efae3-169">A `GUID` literal represents a globally unique identifier.</span></span> <span data-ttu-id="efae3-170">Dabei handelt es sich um eine Sequenz, die durch das-Schlüsselwort, `GUID` gefolgt von hexadezimalen Ziffern in der 8-4-4-4-12 Form, die in einfachen Anführungszeichen eingeschlossen ist. *registry*</span><span class="sxs-lookup"><span data-stu-id="efae3-170">It is a sequence formed by the keyword `GUID` followed by hexadecimal digits in the form known as *registry* format: 8-4-4-4-12 enclosed in single quotes.</span></span> <span data-ttu-id="efae3-171">Bei den Hexadezimalzeichen wird die Groß/- Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="efae3-171">Hexadecimal digits are case insensitive.</span></span>  
  
 <span data-ttu-id="efae3-172">Zwischen dem GUID-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="efae3-172">There can be any number of spaces between the GUID symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a><span data-ttu-id="efae3-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efae3-173">See also</span></span>

- [<span data-ttu-id="efae3-174">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="efae3-174">Entity SQL Overview</span></span>](entity-sql-overview.md)
