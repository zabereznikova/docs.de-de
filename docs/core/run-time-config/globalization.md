---
title: Globalisierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die Globalisierungsaspekte einer .NET Core-App konfigurieren, z. B. wie japanische Datumsangaben analysiert werden.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733452"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="783e6-103">Laufzeitkonfigurationsoptionen für die Globalisierung</span><span class="sxs-lookup"><span data-stu-id="783e6-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="783e6-104">Invarianter Modus</span><span class="sxs-lookup"><span data-stu-id="783e6-104">Invariant mode</span></span>

- <span data-ttu-id="783e6-105">Bestimmt, ob eine .NET Core-App im invarianten Globalisierungsmodus ausgeführt wird, ohne Zugriff auf kulturspezifischen Daten und Verhalten zu haben, oder ob sie Zugriff auf kulturelle Daten hat</span><span class="sxs-lookup"><span data-stu-id="783e6-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="783e6-106">Standard: Die App wird mit Zugriff auf kulturelle Daten ausgeführt (`false`).</span><span class="sxs-lookup"><span data-stu-id="783e6-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="783e6-107">Weitere Informationen finden sie unter [invarianter Globalisierungsmodus in .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="783e6-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="783e6-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="783e6-108">Setting name</span></span> | <span data-ttu-id="783e6-109">Werte</span><span class="sxs-lookup"><span data-stu-id="783e6-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="783e6-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="783e6-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="783e6-111">`false` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="783e6-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="783e6-112">`true` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="783e6-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="783e6-113">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="783e6-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="783e6-114">`false` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="783e6-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="783e6-115">`true` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="783e6-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="783e6-116">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="783e6-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="783e6-117">`0` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="783e6-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="783e6-118">`1` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="783e6-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="783e6-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="783e6-119">Examples</span></span>

<span data-ttu-id="783e6-120">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="783e6-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="783e6-121">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="783e6-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="783e6-122">Jahreszeitraumbereiche</span><span class="sxs-lookup"><span data-stu-id="783e6-122">Era year ranges</span></span>

- <span data-ttu-id="783e6-123">Legt fest, ob Bereichsüberprüfungen für Kalender, die mehrere Zeiträume unterstützen, locker sind, oder ob Daten, die den Datumsbereich eines Zeitraums überschreiten, eine <xref:System.ArgumentOutOfRangeException>-Klasse auslösen.</span><span class="sxs-lookup"><span data-stu-id="783e6-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="783e6-124">Standard: Bereichsüberprüfungen werden gelockert (`false`).</span><span class="sxs-lookup"><span data-stu-id="783e6-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="783e6-125">Weitere Informationen finden Sie unter [Kalender, Zeiträume und Datumsbereiche: Gelockerte Bereichsüberprüfungen](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="783e6-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="783e6-126">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="783e6-126">Setting name</span></span> | <span data-ttu-id="783e6-127">Werte</span><span class="sxs-lookup"><span data-stu-id="783e6-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="783e6-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="783e6-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="783e6-129">`false` – gelockerte Bereichsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="783e6-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="783e6-130">`true` – Überschreitungen verursachen eine Ausnahme</span><span class="sxs-lookup"><span data-stu-id="783e6-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="783e6-131">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="783e6-131">**Environment variable**</span></span> | <span data-ttu-id="783e6-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="783e6-132">N/A</span></span> | <span data-ttu-id="783e6-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="783e6-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="783e6-134">Japanische Datumsanalyse</span><span class="sxs-lookup"><span data-stu-id="783e6-134">Japanese date parsing</span></span>

- <span data-ttu-id="783e6-135">Bestimmt, ob eine Zeichenfolge, die entweder „1“ oder „Gannen“ als Jahresangabe enthält, erfolgreich analysiert wird, oder ob nur „1“ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="783e6-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="783e6-136">Standard: Zeichenfolgen, die entweder „1“ oder „Gannen“ als Jahresangabe enthalten, werden analysiert (`false`).</span><span class="sxs-lookup"><span data-stu-id="783e6-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="783e6-137">Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="783e6-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="783e6-138">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="783e6-138">Setting name</span></span> | <span data-ttu-id="783e6-139">Werte</span><span class="sxs-lookup"><span data-stu-id="783e6-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="783e6-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="783e6-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="783e6-141">`false` – „Gannen“ oder „1“ wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="783e6-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="783e6-142">`true` – nur „1“ wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="783e6-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="783e6-143">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="783e6-143">**Environment variable**</span></span> | <span data-ttu-id="783e6-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="783e6-144">N/A</span></span> | <span data-ttu-id="783e6-145">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="783e6-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="783e6-146">Japanisches Jahresformat</span><span class="sxs-lookup"><span data-stu-id="783e6-146">Japanese year format</span></span>

- <span data-ttu-id="783e6-147">Bestimmt, ob das erste Jahr eines japanischen Kalenderzeitraums als „Gannen“ oder als Zahl formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="783e6-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="783e6-148">Standard: Das erste Jahr wird als „Gannen“ formatiert (`false`).</span><span class="sxs-lookup"><span data-stu-id="783e6-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="783e6-149">Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="783e6-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="783e6-150">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="783e6-150">Setting name</span></span> | <span data-ttu-id="783e6-151">Werte</span><span class="sxs-lookup"><span data-stu-id="783e6-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="783e6-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="783e6-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="783e6-153">`false` – Formatierung als „Gannen“</span><span class="sxs-lookup"><span data-stu-id="783e6-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="783e6-154">`true` – Formatierung als Zahl</span><span class="sxs-lookup"><span data-stu-id="783e6-154">`true` - format as number</span></span> |
| <span data-ttu-id="783e6-155">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="783e6-155">**Environment variable**</span></span> | <span data-ttu-id="783e6-156">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="783e6-156">N/A</span></span> | <span data-ttu-id="783e6-157">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="783e6-157">N/A</span></span> |
