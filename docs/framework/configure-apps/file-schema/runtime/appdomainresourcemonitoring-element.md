---
title: <appDomainResourceMonitoring>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154375"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="567e7-102">\<appDomainResourceMonitoring>-Element</span><span class="sxs-lookup"><span data-stu-id="567e7-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="567e7-103">Weist die Runtime zum Sammeln von Statistiken für alle Anwendungsdomänen im Prozess für die Lebensdauer des Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="567e7-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="567e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="567e7-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="567e7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="567e7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="567e7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="567e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="567e7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="567e7-107">Attributes</span></span>  
  
|<span data-ttu-id="567e7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="567e7-108">Attribute</span></span>|<span data-ttu-id="567e7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="567e7-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="567e7-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="567e7-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="567e7-111">Gibt an, ob die Laufzeit Statistiken für die Überwachung der Anwendungs Domänen Ressourcen sammelt.</span><span class="sxs-lookup"><span data-stu-id="567e7-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="567e7-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="567e7-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="567e7-113">Wert</span><span class="sxs-lookup"><span data-stu-id="567e7-113">Value</span></span>|<span data-ttu-id="567e7-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="567e7-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="567e7-115">Statistiken für die Überwachung von Anwendungs Domänen Ressourcen werden gesammelt.</span><span class="sxs-lookup"><span data-stu-id="567e7-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="567e7-116">Statistiken für die Überwachung von Anwendungs Domänen Ressourcen werden nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="567e7-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="567e7-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="567e7-117">Child Elements</span></span>  
 <span data-ttu-id="567e7-118">Keine</span><span class="sxs-lookup"><span data-stu-id="567e7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="567e7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="567e7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="567e7-120">Element</span><span class="sxs-lookup"><span data-stu-id="567e7-120">Element</span></span>|<span data-ttu-id="567e7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="567e7-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="567e7-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="567e7-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="567e7-123">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="567e7-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="567e7-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="567e7-124">Remarks</span></span>  
 <span data-ttu-id="567e7-125">Die Ressourcenüberwachung für die Anwendungsdomäne ist über die verwaltete Anwendungs Domänen Klasse, die hostende [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) -Schnittstelle und die Ereignis Ablauf Verfolgung für Windows (ETW) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="567e7-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="567e7-126">Wenn die Überwachung aktiviert ist, werden Statistiken für alle Anwendungs Domänen im Prozess für die Lebensdauer des Prozesses erfasst.</span><span class="sxs-lookup"><span data-stu-id="567e7-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="567e7-127">Um die Überwachung aus verwaltetem Code zu aktivieren, verwenden Sie die- <xref:System.AppDomain.MonitoringIsEnabled%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="567e7-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="567e7-128">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="567e7-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="567e7-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="567e7-129">Example</span></span>  
 <span data-ttu-id="567e7-130">Im folgenden Beispiel wird gezeigt, wie Sie die Überwachung von Anwendungs Domänen Ressourcen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="567e7-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="567e7-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="567e7-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="567e7-132">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="567e7-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="567e7-133">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="567e7-133">Configuration File Schema</span></span>](../index.md)
