---
title: <appDomainResourceMonitoring>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154375"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="19bf2-102">\<appDomainResourceMonitoring> Element</span><span class="sxs-lookup"><span data-stu-id="19bf2-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="19bf2-103">Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="19bf2-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="19bf2-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19bf2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19bf2-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="19bf2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="19bf2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span><span class="sxs-lookup"><span data-stu-id="19bf2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19bf2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="19bf2-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19bf2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="19bf2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="19bf2-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="19bf2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19bf2-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="19bf2-110">Attributes</span></span>  
  
|<span data-ttu-id="19bf2-111">attribute</span><span class="sxs-lookup"><span data-stu-id="19bf2-111">Attribute</span></span>|<span data-ttu-id="19bf2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19bf2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="19bf2-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="19bf2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="19bf2-114">Gibt an, ob die Laufzeit Statistiken für die Überwachung von Anwendungsdomänenressourcen sammelt.</span><span class="sxs-lookup"><span data-stu-id="19bf2-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="19bf2-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="19bf2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="19bf2-116">value</span><span class="sxs-lookup"><span data-stu-id="19bf2-116">Value</span></span>|<span data-ttu-id="19bf2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19bf2-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="19bf2-118">Statistiken für die Überwachung von Anwendungsdomänenressourcen werden gesammelt.</span><span class="sxs-lookup"><span data-stu-id="19bf2-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="19bf2-119">Statistiken für die Überwachung von Anwendungsdomänenressourcen werden nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="19bf2-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19bf2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19bf2-120">Child Elements</span></span>  
 <span data-ttu-id="19bf2-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="19bf2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19bf2-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19bf2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="19bf2-123">Element</span><span class="sxs-lookup"><span data-stu-id="19bf2-123">Element</span></span>|<span data-ttu-id="19bf2-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19bf2-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="19bf2-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="19bf2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="19bf2-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="19bf2-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19bf2-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="19bf2-127">Remarks</span></span>  
 <span data-ttu-id="19bf2-128">Die Überwachung von Anwendungsdomänenressourcen ist über die Domänenklasse der verwalteten Anwendung, die [ICLRAppDomainResourceMonitor-Schnittstelle](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) und die Ereignisablaufverfolgung für Windows (ETW) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19bf2-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="19bf2-129">Wenn die Überwachung aktiviert ist, werden Statistiken für alle Anwendungsdomänen im Prozess für die Gesamteingang des Prozesses gesammelt.</span><span class="sxs-lookup"><span data-stu-id="19bf2-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="19bf2-130">Verwenden Sie die Eigenschaft, <xref:System.AppDomain.MonitoringIsEnabled%2A> um die Überwachung von verwaltetem Code zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="19bf2-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="19bf2-131">Dieses Konfigurationselement ist nur in .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19bf2-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19bf2-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19bf2-132">Example</span></span>  
 <span data-ttu-id="19bf2-133">Das folgende Beispiel zeigt, wie die Überwachung von Anwendungsdomänenressourcen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="19bf2-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19bf2-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19bf2-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="19bf2-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="19bf2-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="19bf2-136">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="19bf2-136">Configuration File Schema</span></span>](../index.md)
