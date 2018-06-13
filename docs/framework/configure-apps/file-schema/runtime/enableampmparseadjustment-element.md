---
title: '&lt;EnableAmPmParseAdjustment&gt; Element'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752818"
---
# <a name="ltenableampmparseadjustmentgt-element"></a><span data-ttu-id="28960-102">&lt;EnableAmPmParseAdjustment&gt; Element</span><span class="sxs-lookup"><span data-stu-id="28960-102">&lt;EnableAmPmParseAdjustment&gt; Element</span></span>
<span data-ttu-id="28960-103">Bestimmt, ob die Datums- und uhrzeitanalysemethoden verwenden einen angepassten Satz von Regeln analysiert Datumszeichenfolgen, die ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="28960-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="28960-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="28960-104">\<configuration></span></span>  
 <span data-ttu-id="28960-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="28960-105">\<runtime></span></span>  
<span data-ttu-id="28960-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="28960-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28960-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="28960-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28960-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="28960-108">Attributes and Elements</span></span>  
 <span data-ttu-id="28960-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28960-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28960-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="28960-110">Attributes</span></span>  
  
|<span data-ttu-id="28960-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="28960-111">Attribute</span></span>|<span data-ttu-id="28960-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28960-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="28960-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="28960-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="28960-114">Gibt an, ob Datums- und uhrzeitanalysemethoden einen angepassten Satz von Regeln analysiert Datumszeichenfolgen, die nur ein Tag, Monat, Stunde, und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="28960-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="28960-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="28960-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="28960-116">Wert</span><span class="sxs-lookup"><span data-stu-id="28960-116">Value</span></span>|<span data-ttu-id="28960-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28960-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28960-118">0</span><span class="sxs-lookup"><span data-stu-id="28960-118">0</span></span>|<span data-ttu-id="28960-119">Datums- und uhrzeitanalysemethoden verwenden nicht angepasste Regeln für die Analyse von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde, und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="28960-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="28960-120">1</span><span class="sxs-lookup"><span data-stu-id="28960-120">1</span></span>|<span data-ttu-id="28960-121">Verwenden Sie angepasste Regeln für die Analyse von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde, und AM/PM-Kennzeichner enthalten, Datums- und uhrzeitanalysemethoden.</span><span class="sxs-lookup"><span data-stu-id="28960-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28960-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28960-122">Child Elements</span></span>  
 <span data-ttu-id="28960-123">Keine</span><span class="sxs-lookup"><span data-stu-id="28960-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28960-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28960-124">Parent Elements</span></span>  
  
|<span data-ttu-id="28960-125">Element</span><span class="sxs-lookup"><span data-stu-id="28960-125">Element</span></span>|<span data-ttu-id="28960-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28960-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="28960-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="28960-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="28960-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="28960-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28960-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28960-129">Remarks</span></span>  
 <span data-ttu-id="28960-130">Die `<EnableAmPmParseAdjustment>` -Element steuert, wie die folgenden Methoden eine Datumszeichenfolge analysiert, die einen numerischen Tag und Monat gefolgt von einer Stunde und einer AM/PM-Kennzeichner (z. B. "4/10 6 Uhr") enthält:</span><span class="sxs-lookup"><span data-stu-id="28960-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="28960-131">Es sind keine anderen Mustern enthalten betroffen.</span><span class="sxs-lookup"><span data-stu-id="28960-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="28960-132">Die `<EnableAmPmParseAdjustment>` Element hat keinen Einfluss auf die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, und <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> Methoden.</span><span class="sxs-lookup"><span data-stu-id="28960-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="28960-133">Die angepassten AM/PM-Analyseregeln sind in .NET Core und .NET Native standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="28960-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="28960-134">Wenn die Analyse Anpassungsregel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge als der Stunde des 12-Stunden-Format interpretiert, und der Rest der Zeichenfolge mit Ausnahme der AM/PM-Kennzeichner wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="28960-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="28960-135">Das Datum und die Uhrzeit der Rückgabe durch die Analysemethode besteht aus dem aktuellen Datum und der Stunde des Tages die Datumszeichenfolge extrahiert.</span><span class="sxs-lookup"><span data-stu-id="28960-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="28960-136">Wenn die Analyse Anpassungsregel aktiviert ist, Analysemethode interpretieren Sie, den Tag und Monat des aktuellen Jahres angehören und Interpretieren Sie die Zeit als der Stunde des 12-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="28960-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="28960-137">Die folgende Tabelle zeigt den Unterschied in der <xref:System.DateTime> Wert der <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> Methode wird verwendet, um die Zeichenfolge analysiert "" 4/10 6 Uhr"mit der `<EnableAmPmParseAdjustment>` des Elements `enabled` -Eigenschaft auf"0"oder"1"festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28960-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="28960-138">Es wird davon ausgegangen, dass das heutige Datum ist 5 Januar 2017 und zeigt das Datum an, als wäre es mit der angegebenen Kultur "G" Formatzeichenfolge formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="28960-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="28960-139">Kulturname</span><span class="sxs-lookup"><span data-stu-id="28960-139">Culture name</span></span>|<span data-ttu-id="28960-140">aktiviert = "0"</span><span class="sxs-lookup"><span data-stu-id="28960-140">enabled="0"</span></span>|<span data-ttu-id="28960-141">aktiviert = "1"</span><span class="sxs-lookup"><span data-stu-id="28960-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="28960-142">en-US</span><span class="sxs-lookup"><span data-stu-id="28960-142">en-US</span></span>|<span data-ttu-id="28960-143">5/1/2017 4:00:00 UHR</span><span class="sxs-lookup"><span data-stu-id="28960-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="28960-144">4/10/2017 6:00:00 UHR</span><span class="sxs-lookup"><span data-stu-id="28960-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="28960-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="28960-145">en-GB</span></span>|<span data-ttu-id="28960-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="28960-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="28960-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="28960-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28960-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28960-148">See Also</span></span>  
 [<span data-ttu-id="28960-149">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="28960-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [<span data-ttu-id="28960-150">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="28960-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
