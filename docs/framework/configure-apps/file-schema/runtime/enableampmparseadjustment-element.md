---
title: <EnableAmPmParseAdjustment>-Element
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bcde1bbb5419de2c363b422c327d55c2ce9eea1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607312"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="a4e11-102">\<EnableAmPmParseAdjustment >-Element</span><span class="sxs-lookup"><span data-stu-id="a4e11-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="a4e11-103">Bestimmt, ob Datum und Uhrzeit-Analysemethoden verwenden einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen, die ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4e11-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="a4e11-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a4e11-104">\<configuration></span></span>  
 <span data-ttu-id="a4e11-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a4e11-105">\<runtime></span></span>  
<span data-ttu-id="a4e11-106">\<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="a4e11-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4e11-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4e11-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4e11-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4e11-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a4e11-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4e11-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4e11-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4e11-110">Attributes</span></span>  
  
|<span data-ttu-id="a4e11-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a4e11-111">Attribute</span></span>|<span data-ttu-id="a4e11-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4e11-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a4e11-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a4e11-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a4e11-114">Gibt an, ob Datum und Uhrzeit-Analysemethoden verwenden einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4e11-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="a4e11-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a4e11-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a4e11-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a4e11-116">Value</span></span>|<span data-ttu-id="a4e11-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4e11-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4e11-118">0</span><span class="sxs-lookup"><span data-stu-id="a4e11-118">0</span></span>|<span data-ttu-id="a4e11-119">Datum und Uhrzeit-Analysemethoden verwenden nicht angepasste Regeln zum Analysieren von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4e11-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="a4e11-120">1</span><span class="sxs-lookup"><span data-stu-id="a4e11-120">1</span></span>|<span data-ttu-id="a4e11-121">Datum und Uhrzeit-Analysemethoden verwenden angepasste Regeln zum Analysieren von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4e11-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4e11-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4e11-122">Child Elements</span></span>  
 <span data-ttu-id="a4e11-123">Keine</span><span class="sxs-lookup"><span data-stu-id="a4e11-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4e11-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4e11-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a4e11-125">Element</span><span class="sxs-lookup"><span data-stu-id="a4e11-125">Element</span></span>|<span data-ttu-id="a4e11-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4e11-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a4e11-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a4e11-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a4e11-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="a4e11-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4e11-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4e11-129">Remarks</span></span>  
 <span data-ttu-id="a4e11-130">Die `<EnableAmPmParseAdjustment>` -Element steuert, wie die folgenden Methoden eine Datumszeichenfolge analysiert, die einen numerischen Tag und Monat, gefolgt von einer Stunde und einer AM/PM-Kennzeichner (z. B. "4/10 6 Uhr") enthält:</span><span class="sxs-lookup"><span data-stu-id="a4e11-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="a4e11-131">Es sind keine anderen Mustern betroffen.</span><span class="sxs-lookup"><span data-stu-id="a4e11-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="a4e11-132">Die `<EnableAmPmParseAdjustment>` Element hat keine Auswirkungen auf die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, und <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> Methoden.</span><span class="sxs-lookup"><span data-stu-id="a4e11-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4e11-133">In .NET Core und .NET Native sind die angepassten AM/PM-Analyseregeln standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4e11-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="a4e11-134">Wenn die Analyse Anpassungsregel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge wird als der Stunde im 12-Stunden-Format interpretiert, und der Rest der Zeichenfolge, mit Ausnahme der AM/PM-Kennzeichner wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a4e11-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="a4e11-135">Datum und Uhrzeit, die von der Methode zurückgegebenen besteht aus dem aktuellen Datum und die Stunde des Tages aus der Datumszeichenfolge extrahiert.</span><span class="sxs-lookup"><span data-stu-id="a4e11-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="a4e11-136">Wenn die Analyse Anpassungsregel aktiviert ist, Analysemethode Tag und Monat als das aktuelle Jahr gehörend zu interpretieren und die Zeit als die Stunde im 12-Stunden-Format zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="a4e11-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="a4e11-137">Die folgende Tabelle zeigt den Unterschied in der <xref:System.DateTime> Wert fest, wenn die <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> Methode wird verwendet, um die Zeichenfolge analysiert "" 4/10 6 Uhr"mit der `<EnableAmPmParseAdjustment>` des Elements `enabled` -Eigenschaft auf"0"oder"1"festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4e11-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="a4e11-138">Es wird davon ausgegangen, dass das heutige Datum ist 5. Januar 2017, und zeigt das Datum, als wäre es mit der angegebenen Kultur "G" Formatzeichenfolge formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="a4e11-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="a4e11-139">Kulturname</span><span class="sxs-lookup"><span data-stu-id="a4e11-139">Culture name</span></span>|<span data-ttu-id="a4e11-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="a4e11-140">enabled="0"</span></span>|<span data-ttu-id="a4e11-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="a4e11-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="a4e11-142">en-US</span><span class="sxs-lookup"><span data-stu-id="a4e11-142">en-US</span></span>|<span data-ttu-id="a4e11-143">1/5/2017 4:00:00 UHR</span><span class="sxs-lookup"><span data-stu-id="a4e11-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="a4e11-144">4/10/2017-06:00:00 UHR</span><span class="sxs-lookup"><span data-stu-id="a4e11-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="a4e11-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="a4e11-145">en-GB</span></span>|<span data-ttu-id="a4e11-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="a4e11-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="a4e11-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="a4e11-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4e11-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4e11-148">See also</span></span>

- [<span data-ttu-id="a4e11-149">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="a4e11-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="a4e11-150">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="a4e11-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
