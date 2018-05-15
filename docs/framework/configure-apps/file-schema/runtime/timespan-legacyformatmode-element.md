---
title: '&lt;TimeSpan_LegacyFormatMode&gt; Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0faf2876680ef5ec3fc7373cae9f81eb091f47a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lttimespanlegacyformatmodegt-element"></a><span data-ttu-id="50661-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span><span class="sxs-lookup"><span data-stu-id="50661-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span></span>
<span data-ttu-id="50661-103">Bestimmt, ob die Runtime Legacyverhalten bei Formatierungsvorgängen mit behält <xref:System.TimeSpan?displayProperty=nameWithType> Werte.</span><span class="sxs-lookup"><span data-stu-id="50661-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="50661-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="50661-104">\<configuration></span></span>  
<span data-ttu-id="50661-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="50661-105">\<runtime></span></span>  
<span data-ttu-id="50661-106">< TimeSpan_LegacyFormatMode ></span><span class="sxs-lookup"><span data-stu-id="50661-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50661-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="50661-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50661-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="50661-108">Attributes and Elements</span></span>  
 <span data-ttu-id="50661-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50661-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50661-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="50661-110">Attributes</span></span>  
  
|<span data-ttu-id="50661-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="50661-111">Attribute</span></span>|<span data-ttu-id="50661-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50661-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="50661-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="50661-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="50661-114">Gibt an, ob die Common Language Runtime mit älteren Formatierungsverhalten verwendet <xref:System.TimeSpan?displayProperty=nameWithType> Werte.</span><span class="sxs-lookup"><span data-stu-id="50661-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="50661-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="50661-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="50661-116">Wert</span><span class="sxs-lookup"><span data-stu-id="50661-116">Value</span></span>|<span data-ttu-id="50661-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50661-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="50661-118">Die Common Language Runtime Legacyverhalten Formatierung nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="50661-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="50661-119">Die Common Language Runtime stellt Formatierung Legacyverhalten wieder her.</span><span class="sxs-lookup"><span data-stu-id="50661-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50661-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50661-120">Child Elements</span></span>  
 <span data-ttu-id="50661-121">Keine</span><span class="sxs-lookup"><span data-stu-id="50661-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50661-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50661-122">Parent Elements</span></span>  
  
|<span data-ttu-id="50661-123">Element</span><span class="sxs-lookup"><span data-stu-id="50661-123">Element</span></span>|<span data-ttu-id="50661-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50661-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="50661-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="50661-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="50661-126">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="50661-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50661-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50661-127">Remarks</span></span>  
 <span data-ttu-id="50661-128">Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> Struktur implementiert die <xref:System.IFormattable> Schnittstelle und Formatierungsvorgängen mit standardmäßigen und benutzerdefinierten Formatzeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50661-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="50661-129">Wenn eine Analysemethode eine nicht unterstützte Formatbezeichner oder Formatzeichenfolge gefunden wird, löst sie eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="50661-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="50661-130">In früheren Versionen von .NET Framework die <xref:System.TimeSpan> Struktur wurde nicht implementiert <xref:System.IFormattable> und hat keine Formatzeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50661-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="50661-131">Jedoch viele Entwickler fälschlicherweise davon ausgegangen, dass <xref:System.TimeSpan> hat einen Satz von Formatzeichenfolgen unterstützt, und verwendet diese in [zur kombinierten Formatierung Vorgänge](../../../../../docs/standard/base-types/composite-formatting.md) mit Methoden wie z. B. <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50661-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50661-132">In der Regel, wenn ein Typ implementiert <xref:System.IFormattable> und Formatzeichenfolgen unterstützt, Aufrufe von Formatierungsmethoden mit nicht unterstützten Format Zeichenfolgen in der Regel löst eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="50661-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="50661-133">Aber da <xref:System.TimeSpan> wurde nicht implementiert <xref:System.IFormattable>, die Laufzeit die Formatzeichenfolge ignoriert und stattdessen aufgerufen die <xref:System.TimeSpan.ToString?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="50661-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="50661-134">Dies bedeutet, dass, obwohl die Formatzeichenfolgen keine Auswirkungen auf den Formatierungsvorgang hatte, deren Vorhandensein nicht ergeben hat eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="50661-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="50661-135">Für Fälle, in dem legacy-Code übergibt eine zur kombinierten Formatierung, Methode und eine ungültige Formatzeichenfolge und diesen Code nicht neu kompiliert werden, können Sie die `<TimeSpan_LegacyFormatMode>` Element zum Wiederherstellen der Vorgängerversion <xref:System.TimeSpan> Verhalten.</span><span class="sxs-lookup"><span data-stu-id="50661-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="50661-136">Beim Festlegen der `enabled` Attribut dieses Elements in `true`, die zur kombinierten Formatierung Methodenergebnisse in einem Aufruf von <xref:System.TimeSpan.ToString?displayProperty=nameWithType> statt <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, und ein <xref:System.FormatException> wird nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="50661-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50661-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50661-137">Example</span></span>  
 <span data-ttu-id="50661-138">Das folgende Beispiel instanziiert einen <xref:System.TimeSpan> -Objekt und formatieren Sie ihn mit dem Versuch, die <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> -Methode mithilfe einer nicht unterstützten Standardformatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="50661-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="50661-139">Wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] oder eine frühere Version zeigt es die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="50661-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="50661-140">Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder höher:</span><span class="sxs-lookup"><span data-stu-id="50661-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="50661-141">Wenn Sie das Beispiel die folgende Konfigurationsdatei hinzufügen jedoch dem Verzeichnis des, und führen Sie das Beispiel auf die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder höher, die Ausgabe ist identisch mit der bei der Ausführung auf [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50661-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50661-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50661-142">See Also</span></span>  
 [<span data-ttu-id="50661-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="50661-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="50661-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="50661-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
