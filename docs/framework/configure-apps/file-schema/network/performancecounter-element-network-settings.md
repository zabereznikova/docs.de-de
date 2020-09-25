---
title: <performanceCounter>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 4859f3a9e6de4f1bf8a56212bfe01f94d66f5650
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190240"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="4d3be-102">\<performanceCounter>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4d3be-102">\<performanceCounter> Element (Network Settings)</span></span>

<span data-ttu-id="4d3be-103">Aktiviert oder deaktiviert Netzwerk Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="4d3be-103">Enables or disables networking performance counters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

## <a name="syntax"></a><span data-ttu-id="4d3be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d3be-104">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d3be-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4d3be-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4d3be-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d3be-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d3be-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4d3be-107">Attributes</span></span>  
  
|<span data-ttu-id="4d3be-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4d3be-108">Attribute</span></span>|<span data-ttu-id="4d3be-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d3be-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4d3be-110">Gibt an, ob die Netzwerk Leistungsindikatoren aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4d3be-110">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="4d3be-111">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="4d3be-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d3be-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d3be-112">Child Elements</span></span>  

 <span data-ttu-id="4d3be-113">Keine</span><span class="sxs-lookup"><span data-stu-id="4d3be-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d3be-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d3be-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4d3be-115">Element</span><span class="sxs-lookup"><span data-stu-id="4d3be-115">Element</span></span>|<span data-ttu-id="4d3be-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d3be-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d3be-117">settings</span><span class="sxs-lookup"><span data-stu-id="4d3be-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4d3be-118">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="4d3be-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d3be-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4d3be-119">Remarks</span></span>  

 <span data-ttu-id="4d3be-120">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d3be-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="4d3be-121">Netzwerkleistungsindikatoren müssen in der zu verwendenden Konfigurationsdatei aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="4d3be-121">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="4d3be-122">Alle Netzwerkleistungsindikatoren werden mit einer einzelnen Einstellung in der Konfigurationsdatei aktiviert bzw. deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4d3be-122">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="4d3be-123">Einzelne Netzwerkleistungsindikatoren können nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4d3be-123">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="4d3be-124">Weitere Informationen zu den spezifischen Netzwerk Leistungsindikatoren finden Sie unter [Netzwerk Leistungsindikatoren](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span><span class="sxs-lookup"><span data-stu-id="4d3be-124">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="4d3be-125">Der Standardwert ist, dass Netzwerk Leistungsindikatoren deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4d3be-125">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="4d3be-126">Die- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des **aktivierten** Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4d3be-126">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d3be-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d3be-127">Example</span></span>  

 <span data-ttu-id="4d3be-128">Im folgenden Beispiel wird gezeigt, wie die verknüpften <xref:System.Net> Namespaces und zum Aktivieren von Netzwerk Leistungsindikatoren konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4d3be-128">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d3be-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d3be-129">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4d3be-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4d3be-130">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4d3be-131">Netzwerk Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="4d3be-131">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
