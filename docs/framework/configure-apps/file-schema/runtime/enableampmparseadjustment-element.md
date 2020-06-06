---
title: <EnableAmPmParseAdjustment>-Element
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 8920e51fcaaca5cb78b80a99ea321163c9b5240f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117369"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="8023f-102">\<EnableAmPmParseAdjustment>-Element</span><span class="sxs-lookup"><span data-stu-id="8023f-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="8023f-103">Bestimmt, ob Datums-und Uhrzeit Analysemethoden einen angepassten Satz von Regeln zum Analysieren von Datums Zeichenfolgen verwenden, die einen Tag, einen Monat, eine Stunde und einen am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="8023f-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="8023f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8023f-104">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8023f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8023f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8023f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8023f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8023f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="8023f-107">Attributes</span></span>  
  
|<span data-ttu-id="8023f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8023f-108">Attribute</span></span>|<span data-ttu-id="8023f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8023f-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8023f-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8023f-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="8023f-111">Gibt an, ob Datums-und Uhrzeit Analysemethoden einen angepassten Satz von Regeln zum Analysieren von Datums Zeichenfolgen verwenden, die nur einen Tag, einen Monat, eine Stunde und einen am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="8023f-111">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="8023f-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="8023f-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="8023f-113">Wert</span><span class="sxs-lookup"><span data-stu-id="8023f-113">Value</span></span>|<span data-ttu-id="8023f-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8023f-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8023f-115">0</span><span class="sxs-lookup"><span data-stu-id="8023f-115">0</span></span>|<span data-ttu-id="8023f-116">Datums-und Uhrzeit-Analyse-Methoden verwenden keine angepassten Regeln für das Parsen von Datums Zeichenfolgen, die nur einen Tag, einen Monat, eine Stunde und am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="8023f-116">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="8023f-117">1</span><span class="sxs-lookup"><span data-stu-id="8023f-117">1</span></span>|<span data-ttu-id="8023f-118">Datums-und Uhrzeit-Analyse-Methoden verwenden angepasste Regeln zum Parsen von Datums Zeichenfolgen, die nur einen Tag, einen Monat, eine Stunde und am/pm-Kenn Zeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="8023f-118">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8023f-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8023f-119">Child Elements</span></span>  
 <span data-ttu-id="8023f-120">Keine</span><span class="sxs-lookup"><span data-stu-id="8023f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8023f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8023f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8023f-122">Element</span><span class="sxs-lookup"><span data-stu-id="8023f-122">Element</span></span>|<span data-ttu-id="8023f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8023f-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8023f-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8023f-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8023f-125">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="8023f-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8023f-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8023f-126">Remarks</span></span>  
 <span data-ttu-id="8023f-127">Das- `<EnableAmPmParseAdjustment>` Element steuert, wie die folgenden Methoden eine Datums Zeichenfolge analysieren, die einen numerischen Tag und Monat gefolgt von einer Stunde und einem am/pm-Kenn Zeichner (z. b. "4/10 6 am") enthält:</span><span class="sxs-lookup"><span data-stu-id="8023f-127">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="8023f-128">Es sind keine anderen Muster betroffen.</span><span class="sxs-lookup"><span data-stu-id="8023f-128">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="8023f-129">Das `<EnableAmPmParseAdjustment>` -Element hat keine Auswirkung auf <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> die <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> Methoden,, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> und <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8023f-129">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8023f-130">In .net Core und .net Native sind die angepassten am/pm-Analyse-Regeln standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8023f-130">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="8023f-131">Wenn die Verarbeitungs Anpassungs Regel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge als Stunde der 12-Stunden-Uhrzeit interpretiert, und der Rest der Zeichenfolge außer dem am/pm-Kenn Zeichner wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8023f-131">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="8023f-132">Das von der-Methode für die-Methode zurückgegebene Datum und die Uhrzeit bestehen aus dem aktuellen Datum und der Stunde des Tages, der aus der Datums Zeichenfolge extrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="8023f-132">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="8023f-133">Wenn die Regel für die Verarbeitung von Regeln aktiviert ist, interpretiert die-Methode für den Tag und den Monat so, dass Sie zum aktuellen Jahr gehört, und interpretiert die Uhrzeit als Stunde der 12-Stunden-Uhr.</span><span class="sxs-lookup"><span data-stu-id="8023f-133">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="8023f-134">In der folgenden Tabelle wird der Unterschied im- <xref:System.DateTime> Wert veranschaulicht, wenn die <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> -Methode verwendet wird, um die Zeichenfolge "" 4/10 6 am zu analysieren, wobei die `<EnableAmPmParseAdjustment>` -Eigenschaft des Elements `enabled` auf "0" oder "1" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8023f-134">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="8023f-135">Dabei wird davon ausgegangen, dass das heutige Datum der 5. Januar 2017 ist, und zeigt das Datum so an, als ob es mit der Format Zeichenfolge "G" der angegebenen Kultur formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="8023f-135">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="8023f-136">Kulturname</span><span class="sxs-lookup"><span data-stu-id="8023f-136">Culture name</span></span>|<span data-ttu-id="8023f-137">aktiviert = "0"</span><span class="sxs-lookup"><span data-stu-id="8023f-137">enabled="0"</span></span>|<span data-ttu-id="8023f-138">aktiviert = "1"</span><span class="sxs-lookup"><span data-stu-id="8023f-138">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="8023f-139">de-DE</span><span class="sxs-lookup"><span data-stu-id="8023f-139">en-US</span></span>|<span data-ttu-id="8023f-140">1/5/2017 4:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="8023f-140">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="8023f-141">4/10/2017 6:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="8023f-141">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="8023f-142">en-GB</span><span class="sxs-lookup"><span data-stu-id="8023f-142">en-GB</span></span>|<span data-ttu-id="8023f-143">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="8023f-143">5/1/2017 6:00:00</span></span>|<span data-ttu-id="8023f-144">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="8023f-144">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8023f-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8023f-145">See also</span></span>

- [<span data-ttu-id="8023f-146">\<runtime>Gewisses</span><span class="sxs-lookup"><span data-stu-id="8023f-146">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="8023f-147">\<configuration>Gewisses</span><span class="sxs-lookup"><span data-stu-id="8023f-147">\<configuration> Element</span></span>](../configuration-element.md)
