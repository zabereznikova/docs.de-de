---
title: '&lt;PerformanceCounter&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5879614fd34fe645899f1b95f41e9b0675418292
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742636"
---
# <a name="ltperformancecountergt-element-network-settings"></a><span data-ttu-id="d32d1-102">&lt;PerformanceCounter&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d32d1-102">&lt;performanceCounter&gt; Element (Network Settings)</span></span>
<span data-ttu-id="d32d1-103">Aktiviert oder deaktiviert Netzwerkleistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="d32d1-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="d32d1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d32d1-104">\<configuration></span></span>  
<span data-ttu-id="d32d1-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d32d1-105">\<system.net></span></span>  
<span data-ttu-id="d32d1-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="d32d1-106">\<settings></span></span>  
<span data-ttu-id="d32d1-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="d32d1-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d32d1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d32d1-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d32d1-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d32d1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d32d1-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d32d1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d32d1-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d32d1-111">Attributes</span></span>  
  
|<span data-ttu-id="d32d1-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d32d1-112">Attribute</span></span>|<span data-ttu-id="d32d1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d32d1-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d32d1-114">Gibt an, ob die Netzwerkleistungsindikatoren aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d32d1-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="d32d1-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d32d1-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d32d1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d32d1-116">Child Elements</span></span>  
 <span data-ttu-id="d32d1-117">Keine</span><span class="sxs-lookup"><span data-stu-id="d32d1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d32d1-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d32d1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d32d1-119">Element</span><span class="sxs-lookup"><span data-stu-id="d32d1-119">Element</span></span>|<span data-ttu-id="d32d1-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d32d1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d32d1-121">settings</span><span class="sxs-lookup"><span data-stu-id="d32d1-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="d32d1-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="d32d1-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d32d1-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d32d1-123">Remarks</span></span>  
 <span data-ttu-id="d32d1-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d32d1-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="d32d1-125">Netzwerkleistungsindikatoren müssen in der zu verwendenden Konfigurationsdatei aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="d32d1-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="d32d1-126">Alle Netzwerkleistungsindikatoren werden mit einer einzelnen Einstellung in der Konfigurationsdatei aktiviert bzw. deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d32d1-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="d32d1-127">Einzelne Netzwerkleistungsindikatoren können nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d32d1-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="d32d1-128">Weitere Informationen zu bestimmten Netzwerkleistungsindikatoren finden Sie unter [Netzwerkleistungsindikatoren](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span><span class="sxs-lookup"><span data-stu-id="d32d1-128">For more information on the specific networking performance counters, see [Networking Performance Counters](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span></span>  
  
 <span data-ttu-id="d32d1-129">Der Standardwert ist, dass Netzwerkleistungsindikatoren Leistungsindikatoren deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d32d1-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="d32d1-130">Die <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der **aktiviert** Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="d32d1-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d32d1-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d32d1-131">Example</span></span>  
 <span data-ttu-id="d32d1-132">Das folgende Beispiel zeigt, wie Sie konfigurieren die <xref:System.Net> und in verwandten Namespaces Netzwerkleistungsindikatoren zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d32d1-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d32d1-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d32d1-133">See Also</span></span>  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d32d1-134">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d32d1-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="d32d1-135">Netzwerkleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="d32d1-135">Networking Performance Counters</span></span>](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
