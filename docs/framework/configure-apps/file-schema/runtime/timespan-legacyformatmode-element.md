---
title: '&lt;TimeSpan_LegacyFormatMode&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2724b3811e9cc28888a9beac0c1ed77092302c3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttimespanlegacyformatmodegt-element"></a><span data-ttu-id="1e8c0-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span><span class="sxs-lookup"><span data-stu-id="1e8c0-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span></span>
<span data-ttu-id="1e8c0-103">Bestimmt, ob die Runtime Legacyverhalten bei Formatierungsvorgängen mit behält <xref:System.TimeSpan?displayProperty=nameWithType> Werte.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="1e8c0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1e8c0-104">\<configuration></span></span>  
<span data-ttu-id="1e8c0-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="1e8c0-105">\<runtime></span></span>  
<span data-ttu-id="1e8c0-106">< TimeSpan_LegacyFormatMode ></span><span class="sxs-lookup"><span data-stu-id="1e8c0-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e8c0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e8c0-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e8c0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1e8c0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1e8c0-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e8c0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e8c0-110">Attributes</span></span>  
  
|<span data-ttu-id="1e8c0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="1e8c0-111">Attribute</span></span>|<span data-ttu-id="1e8c0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e8c0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1e8c0-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1e8c0-114">Gibt an, ob die Common Language Runtime mit älteren Formatierungsverhalten verwendet <xref:System.TimeSpan?displayProperty=nameWithType> Werte.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1e8c0-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="1e8c0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1e8c0-116">Wert</span><span class="sxs-lookup"><span data-stu-id="1e8c0-116">Value</span></span>|<span data-ttu-id="1e8c0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e8c0-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1e8c0-118">Die Common Language Runtime Legacyverhalten Formatierung nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="1e8c0-119">Die Common Language Runtime stellt Formatierung Legacyverhalten wieder her.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e8c0-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e8c0-120">Child Elements</span></span>  
 <span data-ttu-id="1e8c0-121">Keine</span><span class="sxs-lookup"><span data-stu-id="1e8c0-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e8c0-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e8c0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1e8c0-123">Element</span><span class="sxs-lookup"><span data-stu-id="1e8c0-123">Element</span></span>|<span data-ttu-id="1e8c0-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e8c0-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1e8c0-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1e8c0-126">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e8c0-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e8c0-127">Remarks</span></span>  
 <span data-ttu-id="1e8c0-128">Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> Struktur implementiert die <xref:System.IFormattable> Schnittstelle und Formatierungsvorgängen mit standardmäßigen und benutzerdefinierten Formatzeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="1e8c0-129">Wenn eine Analysemethode eine nicht unterstützte Formatbezeichner oder Formatzeichenfolge gefunden wird, löst sie eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="1e8c0-130">In früheren Versionen von .NET Framework die <xref:System.TimeSpan> Struktur wurde nicht implementiert <xref:System.IFormattable> und hat keine Formatzeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="1e8c0-131">Jedoch viele Entwickler fälschlicherweise davon ausgegangen, dass <xref:System.TimeSpan> hat einen Satz von Formatzeichenfolgen unterstützt, und verwendet diese in [zur kombinierten Formatierung Vorgänge](../../../../../docs/standard/base-types/composite-formatting.md) mit Methoden wie z. B. <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1e8c0-132">In der Regel, wenn ein Typ implementiert <xref:System.IFormattable> und Formatzeichenfolgen unterstützt, Aufrufe von Formatierungsmethoden mit nicht unterstützten Format Zeichenfolgen in der Regel löst eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="1e8c0-133">Aber da <xref:System.TimeSpan> wurde nicht implementiert <xref:System.IFormattable>, die Laufzeit die Formatzeichenfolge ignoriert und stattdessen aufgerufen die <xref:System.TimeSpan.ToString?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1e8c0-134">Dies bedeutet, dass, obwohl die Formatzeichenfolgen keine Auswirkungen auf den Formatierungsvorgang hatte, deren Vorhandensein nicht ergeben hat eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="1e8c0-135">Für Fälle, in dem legacy-Code übergibt eine zur kombinierten Formatierung, Methode und eine ungültige Formatzeichenfolge und diesen Code nicht neu kompiliert werden, können Sie die `<TimeSpan_LegacyFormatMode>` Element zum Wiederherstellen der Vorgängerversion <xref:System.TimeSpan> Verhalten.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="1e8c0-136">Beim Festlegen der `enabled` Attribut dieses Elements in `true`, die zur kombinierten Formatierung Methodenergebnisse in einem Aufruf von <xref:System.TimeSpan.ToString?displayProperty=nameWithType> statt <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, und ein <xref:System.FormatException> wird nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e8c0-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e8c0-137">Example</span></span>  
 <span data-ttu-id="1e8c0-138">Das folgende Beispiel instanziiert einen <xref:System.TimeSpan> -Objekt und formatieren Sie ihn mit dem Versuch, die <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> -Methode mithilfe einer nicht unterstützten Standardformatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e8c0-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="1e8c0-139">Wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] oder eine frühere Version zeigt es die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1e8c0-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="1e8c0-140">Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder höher:</span><span class="sxs-lookup"><span data-stu-id="1e8c0-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="1e8c0-141">Wenn Sie das Beispiel die folgende Konfigurationsdatei hinzufügen jedoch dem Verzeichnis des, und führen Sie das Beispiel auf die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder höher, die Ausgabe ist identisch mit der bei der Ausführung auf [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e8c0-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e8c0-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e8c0-142">See Also</span></span>  
 [<span data-ttu-id="1e8c0-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="1e8c0-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="1e8c0-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="1e8c0-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
