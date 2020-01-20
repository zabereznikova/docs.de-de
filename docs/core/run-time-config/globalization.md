---
title: Globalisierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die Globalisierungsaspekte einer .NET Core-App konfigurieren, z. B. wie japanische Datumsangaben analysiert werden.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 76cd4a0a0f93f4df3ff243c6024b952576e8e6cb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740538"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="7abbe-103">Laufzeitkonfigurationsoptionen für die Globalisierung</span><span class="sxs-lookup"><span data-stu-id="7abbe-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="7abbe-104">Invarianter Modus</span><span class="sxs-lookup"><span data-stu-id="7abbe-104">Invariant mode</span></span>

- <span data-ttu-id="7abbe-105">Bestimmt, ob eine .NET Core-App im invarianten Globalisierungsmodus ausgeführt wird, ohne Zugriff auf kulturspezifischen Daten und Verhalten zu haben, oder ob sie Zugriff auf kulturelle Daten hat</span><span class="sxs-lookup"><span data-stu-id="7abbe-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="7abbe-106">Standard: Die App wird mit Zugriff auf kulturelle Daten ausgeführt (`false`).</span><span class="sxs-lookup"><span data-stu-id="7abbe-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="7abbe-107">Weitere Informationen finden sie unter [invarianter Globalisierungsmodus in .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="7abbe-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="7abbe-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="7abbe-108">Setting name</span></span> | <span data-ttu-id="7abbe-109">Werte</span><span class="sxs-lookup"><span data-stu-id="7abbe-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7abbe-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7abbe-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="7abbe-111">`false` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="7abbe-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="7abbe-112">`true` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="7abbe-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="7abbe-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="7abbe-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="7abbe-114">`0` – Zugriff auf kulturelle Daten</span><span class="sxs-lookup"><span data-stu-id="7abbe-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="7abbe-115">`1` – Ausführung im invarianten Modus</span><span class="sxs-lookup"><span data-stu-id="7abbe-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="7abbe-116">Jahreszeitraumbereiche</span><span class="sxs-lookup"><span data-stu-id="7abbe-116">Era year ranges</span></span>

- <span data-ttu-id="7abbe-117">Legt fest, ob Bereichsüberprüfungen für Kalender, die mehrere Zeiträume unterstützen, locker sind, oder ob Daten, die den Datumsbereich eines Zeitraums überschreiten, eine <xref:System.ArgumentOutOfRangeException>-Klasse auslösen.</span><span class="sxs-lookup"><span data-stu-id="7abbe-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="7abbe-118">Standard: Bereichsüberprüfungen werden gelockert (`false`).</span><span class="sxs-lookup"><span data-stu-id="7abbe-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="7abbe-119">Weitere Informationen finden Sie unter [Kalender, Zeiträume und Datumsbereiche: Gelockerte Bereichsüberprüfungen](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="7abbe-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="7abbe-120">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="7abbe-120">Setting name</span></span> | <span data-ttu-id="7abbe-121">Werte</span><span class="sxs-lookup"><span data-stu-id="7abbe-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7abbe-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7abbe-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="7abbe-123">`false` – gelockerte Bereichsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="7abbe-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="7abbe-124">`true` – Überschreitungen verursachen eine Ausnahme</span><span class="sxs-lookup"><span data-stu-id="7abbe-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="7abbe-125">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="7abbe-125">**Environment variable**</span></span> | <span data-ttu-id="7abbe-126">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7abbe-126">N/A</span></span> | <span data-ttu-id="7abbe-127">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7abbe-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="7abbe-128">Japanische Datumsanalyse</span><span class="sxs-lookup"><span data-stu-id="7abbe-128">Japanese date parsing</span></span>

- <span data-ttu-id="7abbe-129">Bestimmt, ob eine Zeichenfolge, die entweder „1“ oder „Gannen“ als Jahresangabe enthält, erfolgreich analysiert wird, oder ob nur „1“ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7abbe-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="7abbe-130">Standard: Zeichenfolgen, die entweder „1“ oder „Gannen“ als Jahresangabe enthalten, werden analysiert (`false`).</span><span class="sxs-lookup"><span data-stu-id="7abbe-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="7abbe-131">Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="7abbe-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="7abbe-132">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="7abbe-132">Setting name</span></span> | <span data-ttu-id="7abbe-133">Werte</span><span class="sxs-lookup"><span data-stu-id="7abbe-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7abbe-134">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7abbe-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="7abbe-135">`false` – „Gannen“ oder „1“ wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="7abbe-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="7abbe-136">`true` – nur „1“ wird unterstützt</span><span class="sxs-lookup"><span data-stu-id="7abbe-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="7abbe-137">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="7abbe-137">**Environment variable**</span></span> | <span data-ttu-id="7abbe-138">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7abbe-138">N/A</span></span> | <span data-ttu-id="7abbe-139">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7abbe-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="7abbe-140">Japanisches Jahresformat</span><span class="sxs-lookup"><span data-stu-id="7abbe-140">Japanese year format</span></span>

- <span data-ttu-id="7abbe-141">Bestimmt, ob das erste Jahr eines japanischen Kalenderzeitraums als „Gannen“ oder als Zahl formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="7abbe-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="7abbe-142">Standard: Das erste Jahr wird als „Gannen“ formatiert (`false`).</span><span class="sxs-lookup"><span data-stu-id="7abbe-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="7abbe-143">Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="7abbe-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="7abbe-144">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="7abbe-144">Setting name</span></span> | <span data-ttu-id="7abbe-145">Werte</span><span class="sxs-lookup"><span data-stu-id="7abbe-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7abbe-146">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7abbe-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="7abbe-147">`false` – Formatierung als „Gannen“</span><span class="sxs-lookup"><span data-stu-id="7abbe-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="7abbe-148">`true` – Formatierung als Zahl</span><span class="sxs-lookup"><span data-stu-id="7abbe-148">`true` - format as number</span></span> |
| <span data-ttu-id="7abbe-149">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="7abbe-149">**Environment variable**</span></span> | <span data-ttu-id="7abbe-150">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7abbe-150">N/A</span></span> | <span data-ttu-id="7abbe-151">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7abbe-151">N/A</span></span> |
