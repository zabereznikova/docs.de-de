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
ms.openlocfilehash: 3fe6b19d0055aafad859b55960800d9786d7fa08
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698004"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="c3f69-102">\<performancecounter >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c3f69-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="c3f69-103">Aktiviert oder deaktiviert Netzwerk Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="c3f69-103">Enables or disables networking performance counters.</span></span>  
  
[<span data-ttu-id="c3f69-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c3f69-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c3f69-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c3f69-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="c3f69-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c3f69-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="c3f69-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<performancecounters >**</span><span class="sxs-lookup"><span data-stu-id="c3f69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3f69-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3f69-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3f69-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3f69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c3f69-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3f69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3f69-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3f69-111">Attributes</span></span>  
  
|<span data-ttu-id="c3f69-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c3f69-112">Attribute</span></span>|<span data-ttu-id="c3f69-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3f69-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c3f69-114">Gibt an, ob die Netzwerk Leistungsindikatoren aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c3f69-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="c3f69-115">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="c3f69-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3f69-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3f69-116">Child Elements</span></span>  
 <span data-ttu-id="c3f69-117">Keine</span><span class="sxs-lookup"><span data-stu-id="c3f69-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3f69-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3f69-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c3f69-119">Element</span><span class="sxs-lookup"><span data-stu-id="c3f69-119">Element</span></span>|<span data-ttu-id="c3f69-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3f69-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3f69-121">settings</span><span class="sxs-lookup"><span data-stu-id="c3f69-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="c3f69-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="c3f69-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3f69-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3f69-123">Remarks</span></span>  
 <span data-ttu-id="c3f69-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3f69-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="c3f69-125">Netzwerkleistungsindikatoren müssen in der zu verwendenden Konfigurationsdatei aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c3f69-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="c3f69-126">Alle Netzwerkleistungsindikatoren werden mit einer einzelnen Einstellung in der Konfigurationsdatei aktiviert bzw. deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c3f69-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="c3f69-127">Einzelne Netzwerkleistungsindikatoren können nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c3f69-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="c3f69-128">Weitere Informationen zu den spezifischen Netzwerk Leistungsindikatoren finden Sie unter [Netzwerk Leistungsindikatoren](../../../debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="c3f69-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="c3f69-129">Der Standardwert ist, dass Netzwerk Leistungsindikatoren deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c3f69-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="c3f69-130">Die <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des **aktivierten** Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c3f69-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3f69-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3f69-131">Example</span></span>  
 <span data-ttu-id="c3f69-132">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Net> und verwandte Namespaces konfigurieren, um Netzwerk Leistungsindikatoren zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c3f69-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c3f69-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3f69-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c3f69-134">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c3f69-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c3f69-135">Netzwerk Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="c3f69-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking)
