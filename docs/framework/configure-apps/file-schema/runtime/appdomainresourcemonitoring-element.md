---
title: '&lt;AppDomainResourceMonitoring&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58caa7458d96ca7bb9088b607a83b2d6be667cae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainresourcemonitoringgt-element"></a><span data-ttu-id="2f1d7-102">&lt;AppDomainResourceMonitoring&gt; Element</span><span class="sxs-lookup"><span data-stu-id="2f1d7-102">&lt;appDomainResourceMonitoring&gt; Element</span></span>
<span data-ttu-id="2f1d7-103">Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="2f1d7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2f1d7-104">\<configuration></span></span>  
<span data-ttu-id="2f1d7-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="2f1d7-105">\<runtime></span></span>  
<span data-ttu-id="2f1d7-106">\<AppDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="2f1d7-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f1d7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f1d7-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f1d7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f1d7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2f1d7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f1d7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f1d7-110">Attributes</span></span>  
  
|<span data-ttu-id="2f1d7-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="2f1d7-111">Attribute</span></span>|<span data-ttu-id="2f1d7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f1d7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2f1d7-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2f1d7-114">Gibt an, ob die Common Language Runtime Statistiken für die ressourcenüberwachung der Anwendungsdomäne erfasst.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2f1d7-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="2f1d7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2f1d7-116">Wert</span><span class="sxs-lookup"><span data-stu-id="2f1d7-116">Value</span></span>|<span data-ttu-id="2f1d7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f1d7-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="2f1d7-118">Statistiken für die ressourcenüberwachung der Anwendungsdomäne werden gesammelt.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="2f1d7-119">Statistiken für die ressourcenüberwachung der Anwendungsdomäne werden nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f1d7-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f1d7-120">Child Elements</span></span>  
 <span data-ttu-id="2f1d7-121">Keine</span><span class="sxs-lookup"><span data-stu-id="2f1d7-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f1d7-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f1d7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2f1d7-123">Element</span><span class="sxs-lookup"><span data-stu-id="2f1d7-123">Element</span></span>|<span data-ttu-id="2f1d7-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f1d7-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2f1d7-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2f1d7-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f1d7-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f1d7-127">Remarks</span></span>  
 <span data-ttu-id="2f1d7-128">Ressourcenüberwachung der Anwendungsdomäne ist verfügbar, über die verwaltete Anwendung Domänenklasse, das hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) Schnittstelle und ereignisablaufverfolgung für Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="2f1d7-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="2f1d7-129">Wenn die Überwachung aktiviert ist, werden Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses gesammelt.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="2f1d7-130">Verwenden Sie zum Aktivieren der Überwachung von verwaltetem Code die <xref:System.AppDomain.MonitoringIsEnabled%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="2f1d7-131">Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f1d7-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f1d7-132">Example</span></span>  
 <span data-ttu-id="2f1d7-133">Im folgende Beispiel wird gezeigt, wie die ressourcenüberwachung der Anwendungsdomäne aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f1d7-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f1d7-134">See Also</span></span>  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2f1d7-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2f1d7-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="2f1d7-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2f1d7-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
