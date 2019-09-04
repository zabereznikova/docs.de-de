---
title: <appDomainResourceMonitoring>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1395ee64d94e33693344b678c7a949665f994079
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252824"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="7de7d-102">\<appdomainresourcemonitoring-> Element</span><span class="sxs-lookup"><span data-stu-id="7de7d-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="7de7d-103">Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="7de7d-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="7de7d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7de7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7de7d-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="7de7d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="7de7d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainResourceMonitoring>**</span><span class="sxs-lookup"><span data-stu-id="7de7d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de7d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7de7d-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7de7d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7de7d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7de7d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7de7d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7de7d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7de7d-110">Attributes</span></span>  
  
|<span data-ttu-id="7de7d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7de7d-111">Attribute</span></span>|<span data-ttu-id="7de7d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7de7d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7de7d-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7de7d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7de7d-114">Gibt an, ob die Laufzeit Statistiken für die Überwachung der Anwendungs Domänen Ressourcen sammelt.</span><span class="sxs-lookup"><span data-stu-id="7de7d-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7de7d-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="7de7d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7de7d-116">Wert</span><span class="sxs-lookup"><span data-stu-id="7de7d-116">Value</span></span>|<span data-ttu-id="7de7d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7de7d-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="7de7d-118">Statistiken für die Überwachung von Anwendungs Domänen Ressourcen werden gesammelt.</span><span class="sxs-lookup"><span data-stu-id="7de7d-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="7de7d-119">Statistiken für die Überwachung von Anwendungs Domänen Ressourcen werden nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="7de7d-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7de7d-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7de7d-120">Child Elements</span></span>  
 <span data-ttu-id="7de7d-121">Keine</span><span class="sxs-lookup"><span data-stu-id="7de7d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7de7d-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7de7d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7de7d-123">Element</span><span class="sxs-lookup"><span data-stu-id="7de7d-123">Element</span></span>|<span data-ttu-id="7de7d-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7de7d-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7de7d-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7de7d-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7de7d-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7de7d-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7de7d-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7de7d-127">Remarks</span></span>  
 <span data-ttu-id="7de7d-128">Die Ressourcenüberwachung für die Anwendungsdomäne ist über die verwaltete Anwendungs Domänen Klasse, die hostende [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) -Schnittstelle und die Ereignis Ablauf Verfolgung für Windows (ETW) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7de7d-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="7de7d-129">Wenn die Überwachung aktiviert ist, werden Statistiken für alle Anwendungs Domänen im Prozess für die Lebensdauer des Prozesses erfasst.</span><span class="sxs-lookup"><span data-stu-id="7de7d-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="7de7d-130">Um die Überwachung aus verwaltetem Code zu aktivieren <xref:System.AppDomain.MonitoringIsEnabled%2A> , verwenden Sie die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7de7d-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="7de7d-131">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7de7d-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7de7d-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7de7d-132">Example</span></span>  
 <span data-ttu-id="7de7d-133">Im folgenden Beispiel wird gezeigt, wie Sie die Überwachung von Anwendungs Domänen Ressourcen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7de7d-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7de7d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7de7d-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7de7d-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="7de7d-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7de7d-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="7de7d-136">Configuration File Schema</span></span>](../index.md)
