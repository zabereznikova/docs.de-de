---
title: <EnableAmPmParseAdjustment>-Element
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f132ce0a114a6fc904d86ca3ce893c447366523f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252633"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="722e5-102">\<Enableampmparameseadjustment-> Element</span><span class="sxs-lookup"><span data-stu-id="722e5-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="722e5-103">Bestimmt, ob Datums-und Uhrzeit Analysemethoden einen angepassten Satz von Regeln zum Analysieren von Datums Zeichenfolgen verwenden, die einen Tag, einen Monat, eine Stunde und einen am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="722e5-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
<span data-ttu-id="722e5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="722e5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="722e5-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="722e5-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="722e5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Enableampmparameseanpassungs->**</span><span class="sxs-lookup"><span data-stu-id="722e5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="722e5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="722e5-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="722e5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="722e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="722e5-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="722e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="722e5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="722e5-110">Attributes</span></span>  
  
|<span data-ttu-id="722e5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="722e5-111">Attribute</span></span>|<span data-ttu-id="722e5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="722e5-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="722e5-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="722e5-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="722e5-114">Gibt an, ob Datums-und Uhrzeit Analysemethoden einen angepassten Satz von Regeln zum Analysieren von Datums Zeichenfolgen verwenden, die nur einen Tag, einen Monat, eine Stunde und einen am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="722e5-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="722e5-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="722e5-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="722e5-116">Wert</span><span class="sxs-lookup"><span data-stu-id="722e5-116">Value</span></span>|<span data-ttu-id="722e5-117">Description</span><span class="sxs-lookup"><span data-stu-id="722e5-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="722e5-118">0</span><span class="sxs-lookup"><span data-stu-id="722e5-118">0</span></span>|<span data-ttu-id="722e5-119">Datums-und Uhrzeit-Analyse-Methoden verwenden keine angepassten Regeln für das Parsen von Datums Zeichenfolgen, die nur einen Tag, einen Monat, eine Stunde und am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="722e5-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="722e5-120">1</span><span class="sxs-lookup"><span data-stu-id="722e5-120">1</span></span>|<span data-ttu-id="722e5-121">Datums-und Uhrzeit-Analyse-Methoden verwenden angepasste Regeln zum Parsen von Datums Zeichenfolgen, die nur einen Tag, einen Monat, eine Stunde und am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="722e5-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="722e5-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="722e5-122">Child Elements</span></span>  
 <span data-ttu-id="722e5-123">Keine</span><span class="sxs-lookup"><span data-stu-id="722e5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="722e5-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="722e5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="722e5-125">Element</span><span class="sxs-lookup"><span data-stu-id="722e5-125">Element</span></span>|<span data-ttu-id="722e5-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="722e5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="722e5-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="722e5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="722e5-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="722e5-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="722e5-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="722e5-129">Remarks</span></span>  
 <span data-ttu-id="722e5-130">Das `<EnableAmPmParseAdjustment>` -Element steuert, wie die folgenden Methoden eine Datums Zeichenfolge analysieren, die einen numerischen Tag und Monat gefolgt von einer Stunde und einem am/pm-Kenn Zeichner (z. b. "4/10 6 am") enthält:</span><span class="sxs-lookup"><span data-stu-id="722e5-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="722e5-131">Es sind keine anderen Muster betroffen.</span><span class="sxs-lookup"><span data-stu-id="722e5-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="722e5-132">Das `<EnableAmPmParseAdjustment>` -Element hat keine Auswirkung auf <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>die <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>Methoden <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>,, <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> und.</span><span class="sxs-lookup"><span data-stu-id="722e5-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="722e5-133">In .net Core und .net Native sind die angepassten am/pm-Analyse-Regeln standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="722e5-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="722e5-134">Wenn die Verarbeitungs Anpassungs Regel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge als Stunde der 12-Stunden-Uhrzeit interpretiert, und der Rest der Zeichenfolge außer dem am/pm-Kenn Zeichner wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="722e5-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="722e5-135">Das von der-Methode für die-Methode zurückgegebene Datum und die Uhrzeit bestehen aus dem aktuellen Datum und der Stunde des Tages, der aus der Datums Zeichenfolge extrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="722e5-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="722e5-136">Wenn die Regel für die Verarbeitung von Regeln aktiviert ist, interpretiert die-Methode für den Tag und den Monat so, dass Sie zum aktuellen Jahr gehört, und interpretiert die Uhrzeit als Stunde der 12-Stunden-Uhr.</span><span class="sxs-lookup"><span data-stu-id="722e5-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="722e5-137">In der folgenden Tabelle wird der Unterschied <xref:System.DateTime> im-Wert <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> veranschaulicht, wenn die-Methode verwendet wird, um die Zeichenfolge "" `<EnableAmPmParseAdjustment>` 4/10 6 am `enabled` zu analysieren, wobei die-Eigenschaft des Elements auf "0" oder "1" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="722e5-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="722e5-138">Dabei wird davon ausgegangen, dass das heutige Datum der 5. Januar 2017 ist, und zeigt das Datum so an, als ob es mit der Format Zeichenfolge "G" der angegebenen Kultur formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="722e5-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="722e5-139">Kulturname</span><span class="sxs-lookup"><span data-stu-id="722e5-139">Culture name</span></span>|<span data-ttu-id="722e5-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="722e5-140">enabled="0"</span></span>|<span data-ttu-id="722e5-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="722e5-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="722e5-142">en-US</span><span class="sxs-lookup"><span data-stu-id="722e5-142">en-US</span></span>|<span data-ttu-id="722e5-143">1/5/2017 4:00:00 UHR</span><span class="sxs-lookup"><span data-stu-id="722e5-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="722e5-144">4/10/2017 6:00:00 UHR</span><span class="sxs-lookup"><span data-stu-id="722e5-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="722e5-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="722e5-145">en-GB</span></span>|<span data-ttu-id="722e5-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="722e5-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="722e5-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="722e5-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="722e5-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="722e5-148">See also</span></span>

- [<span data-ttu-id="722e5-149">\<Runtime-> Element</span><span class="sxs-lookup"><span data-stu-id="722e5-149">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="722e5-150">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="722e5-150">\<configuration> Element</span></span>](../configuration-element.md)
