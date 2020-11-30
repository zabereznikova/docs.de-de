---
title: Globalisierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die Globalisierungsaspekte einer .NET Core-App konfigurieren, z. B. wie japanische Datumsangaben analysiert werden.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: fc98e965093c28b75b9b66e4f1c9f147abd4680e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721911"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="e8264-103">Laufzeitkonfigurationsoptionen für die Globalisierung</span><span class="sxs-lookup"><span data-stu-id="e8264-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="e8264-104">Invarianter Modus</span><span class="sxs-lookup"><span data-stu-id="e8264-104">Invariant mode</span></span>

- <span data-ttu-id="e8264-105">Bestimmt, ob eine .NET Core-App im invarianten Globalisierungsmodus ausgeführt wird, ohne Zugriff auf kulturspezifischen Daten und Verhalten zu haben.</span><span class="sxs-lookup"><span data-stu-id="e8264-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="e8264-106">Wenn Sie diese Einstellung weglassen, wird die App mit Zugriff auf die kulturellen Daten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8264-106">If you omit this setting, the app runs with access to cultural data.</span></span> <span data-ttu-id="e8264-107">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="e8264-107">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="e8264-108">Weitere Informationen finden sie unter [invarianter Globalisierungsmodus in .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e8264-108">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="e8264-109">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e8264-109">Setting name</span></span> | <span data-ttu-id="e8264-110">Werte</span><span class="sxs-lookup"><span data-stu-id="e8264-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e8264-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e8264-111">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="e8264-112">`false` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="e8264-112">`false` - access to cultural data</span></span><br/><span data-ttu-id="e8264-113">`true` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="e8264-113">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="e8264-114">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="e8264-114">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="e8264-115">`false` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="e8264-115">`false` - access to cultural data</span></span><br/><span data-ttu-id="e8264-116">`true` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="e8264-116">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="e8264-117">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e8264-117">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="e8264-118">`0` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="e8264-118">`0` - access to cultural data</span></span><br/><span data-ttu-id="e8264-119">`1` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="e8264-119">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="e8264-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e8264-120">Examples</span></span>

<span data-ttu-id="e8264-121">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="e8264-121">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="e8264-122">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="e8264-122">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="e8264-123">Jahreszeitraumbereiche</span><span class="sxs-lookup"><span data-stu-id="e8264-123">Era year ranges</span></span>

- <span data-ttu-id="e8264-124">Legt fest, ob Bereichsüberprüfungen für Kalender, die mehrere Zeiträume unterstützen, locker sind, oder ob Daten, die den Datumsbereich eines Zeitraums überschreiten, eine <xref:System.ArgumentOutOfRangeException>-Klasse auslösen.</span><span class="sxs-lookup"><span data-stu-id="e8264-124">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="e8264-125">Wenn Sie diese Einstellung weglassen, werden Bereichsüberprüfungen gelockert.</span><span class="sxs-lookup"><span data-stu-id="e8264-125">If you omit this setting, range checks are relaxed.</span></span> <span data-ttu-id="e8264-126">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="e8264-126">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="e8264-127">Weitere Informationen finden Sie unter [Kalender, Zeiträume und Datumsbereiche: Gelockerte Bereichsüberprüfungen](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="e8264-127">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="e8264-128">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e8264-128">Setting name</span></span> | <span data-ttu-id="e8264-129">Werte</span><span class="sxs-lookup"><span data-stu-id="e8264-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e8264-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e8264-130">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="e8264-131">`false` – gelockerte Bereichsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="e8264-131">`false` - relaxed range checks</span></span><br/><span data-ttu-id="e8264-132">`true` – Überschreitungen verursachen eine Ausnahme</span><span class="sxs-lookup"><span data-stu-id="e8264-132">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="e8264-133">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e8264-133">**Environment variable**</span></span> | <span data-ttu-id="e8264-134">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e8264-134">N/A</span></span> | <span data-ttu-id="e8264-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e8264-135">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="e8264-136">Japanische Datumsanalyse</span><span class="sxs-lookup"><span data-stu-id="e8264-136">Japanese date parsing</span></span>

- <span data-ttu-id="e8264-137">Bestimmt, ob eine Zeichenfolge, die entweder „1“ oder „Gannen“ als Jahresangabe enthält, erfolgreich analysiert wird, oder ob nur „1“ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e8264-137">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="e8264-138">Wenn Sie diese Einstellung weglassen, werden Zeichenfolgen, die entweder „1“ oder „Gannen“ als Jahresangabe enthalten, erfolgreich analysiert.</span><span class="sxs-lookup"><span data-stu-id="e8264-138">If you omit this setting, strings that contain either "1" or "Gannen" as the year parse successfully.</span></span> <span data-ttu-id="e8264-139">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="e8264-139">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="e8264-140">Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="e8264-140">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="e8264-141">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e8264-141">Setting name</span></span> | <span data-ttu-id="e8264-142">Werte</span><span class="sxs-lookup"><span data-stu-id="e8264-142">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e8264-143">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e8264-143">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="e8264-144">`false` – „Gannen“ oder „1“ wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="e8264-144">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="e8264-145">`true` – nur „1“ wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="e8264-145">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="e8264-146">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e8264-146">**Environment variable**</span></span> | <span data-ttu-id="e8264-147">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e8264-147">N/A</span></span> | <span data-ttu-id="e8264-148">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e8264-148">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="e8264-149">Japanisches Jahresformat</span><span class="sxs-lookup"><span data-stu-id="e8264-149">Japanese year format</span></span>

- <span data-ttu-id="e8264-150">Bestimmt, ob das erste Jahr eines japanischen Kalenderzeitraums als „Gannen“ oder als Zahl formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8264-150">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="e8264-151">Wenn Sie diese Einstellung weglassen, wird das erste Jahr als „Gannen“ formatiert.</span><span class="sxs-lookup"><span data-stu-id="e8264-151">If you omit this setting, the first year is formatted as "Gannen".</span></span> <span data-ttu-id="e8264-152">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="e8264-152">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="e8264-153">Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="e8264-153">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="e8264-154">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e8264-154">Setting name</span></span> | <span data-ttu-id="e8264-155">Werte</span><span class="sxs-lookup"><span data-stu-id="e8264-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e8264-156">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e8264-156">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="e8264-157">`false` – Formatierung als „Gannen“</span><span class="sxs-lookup"><span data-stu-id="e8264-157">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="e8264-158">`true` – Formatierung als Zahl</span><span class="sxs-lookup"><span data-stu-id="e8264-158">`true` - format as number</span></span> |
| <span data-ttu-id="e8264-159">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e8264-159">**Environment variable**</span></span> | <span data-ttu-id="e8264-160">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e8264-160">N/A</span></span> | <span data-ttu-id="e8264-161">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e8264-161">N/A</span></span> |

## <a name="nls"></a><span data-ttu-id="e8264-162">NLS</span><span class="sxs-lookup"><span data-stu-id="e8264-162">NLS</span></span>

- <span data-ttu-id="e8264-163">Bestimmt, ob .NET für Windows-Apps die NLS-Globalisierungs-APIs (National Language Support, Unterstützung der nationalen Sprache) oder ICU-Globalisierungs-APIs (International Components for Unicode, internationale Komponenten für Unicode) verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8264-163">Determines whether .NET uses National Language Support (NLS) or International Components for Unicode (ICU) globalization APIs for Windows apps.</span></span> <span data-ttu-id="e8264-164">.NET 5.0 und höhere Versionen verwenden ICU-Globalisierungs-APIs standardmäßig unter dem Windows 10-Update vom Mai 2019 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="e8264-164">.NET 5.0 and later versions use ICU globalization APIs by default on Windows 10 May 2019 Update and later versions.</span></span>
- <span data-ttu-id="e8264-165">Wenn Sie diese Einstellung weglassen, verwendet .NET standardmäßig ICU-Globalisierungs-APIs.</span><span class="sxs-lookup"><span data-stu-id="e8264-165">If you omit this setting, .NET uses ICU globalization APIs by default.</span></span> <span data-ttu-id="e8264-166">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="e8264-166">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="e8264-167">Weitere Informationen finden Sie unter [Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows](../compatibility/globalization/5.0/icu-globalization-api.md).</span><span class="sxs-lookup"><span data-stu-id="e8264-167">For more information, see [Globalization APIs use ICU libraries on Windows](../compatibility/globalization/5.0/icu-globalization-api.md).</span></span>

| | <span data-ttu-id="e8264-168">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e8264-168">Setting name</span></span> | <span data-ttu-id="e8264-169">Werte</span><span class="sxs-lookup"><span data-stu-id="e8264-169">Values</span></span> | <span data-ttu-id="e8264-170">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="e8264-170">Introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e8264-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e8264-171">**runtimeconfig.json**</span></span> | `System.Globalization.UseNls` | <span data-ttu-id="e8264-172">`false` – Verwenden von ICU-Globalisierungs-APIs</span><span class="sxs-lookup"><span data-stu-id="e8264-172">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="e8264-173">`true` – Verwenden von NLS-Globalisierungs-APIs</span><span class="sxs-lookup"><span data-stu-id="e8264-173">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="e8264-174">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e8264-174">.NET 5.0</span></span> |
| <span data-ttu-id="e8264-175">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e8264-175">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | <span data-ttu-id="e8264-176">`false` – Verwenden von ICU-Globalisierungs-APIs</span><span class="sxs-lookup"><span data-stu-id="e8264-176">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="e8264-177">`true` – Verwenden von NLS-Globalisierungs-APIs</span><span class="sxs-lookup"><span data-stu-id="e8264-177">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="e8264-178">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e8264-178">.NET 5.0</span></span> |
