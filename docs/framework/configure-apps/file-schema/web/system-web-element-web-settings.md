---
title: <system.web>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152840"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="0a1bd-102">\<system.web>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0a1bd-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="0a1bd-103">Enthält Informationen dazu, wie die ASP.net-hostingschicht Prozess weites Verhalten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="0a1bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a1bd-104">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a1bd-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a1bd-105">Attributes and Elements</span></span>  

<span data-ttu-id="0a1bd-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a1bd-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a1bd-107">Attributes</span></span>  

<span data-ttu-id="0a1bd-108">Keine</span><span class="sxs-lookup"><span data-stu-id="0a1bd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a1bd-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a1bd-109">Child Elements</span></span>  
  
|<span data-ttu-id="0a1bd-110">Element</span><span class="sxs-lookup"><span data-stu-id="0a1bd-110">Element</span></span>|<span data-ttu-id="0a1bd-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a1bd-111">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="0a1bd-112">Gibt Konfigurationseinstellungen für IIS-Anwendungs Pools in einer ASPNET. config-Datei an.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-112">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a1bd-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a1bd-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0a1bd-114">Element</span><span class="sxs-lookup"><span data-stu-id="0a1bd-114">Element</span></span>|<span data-ttu-id="0a1bd-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a1bd-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="0a1bd-116">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a1bd-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0a1bd-117">Remarks</span></span>  

<span data-ttu-id="0a1bd-118">Das `system.web` -Element und das zugehörige `applicationPool` untergeordnete Element wurden der .NET Framework ab .NET Framework 3,5 SP1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-118">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="0a1bd-119">Wenn Sie IIS 7,0 oder höhere Versionen im integrierten Modus ausführen, können Sie mit dieser Element Kombination konfigurieren, wie ASP.NET Threads verwaltet und wie Anforderungen in die Warteschlange eingereiht werden, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-119">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="0a1bd-120">Wenn Sie IIS 7,0 oder höhere Versionen im klassischen oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-120">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a1bd-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a1bd-121">Example</span></span>  

<span data-ttu-id="0a1bd-122">Das folgende Beispiel zeigt, wie Sie das Prozess weite Verhalten von ASP.net in der Datei Aspnet. config konfigurieren, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-122">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="0a1bd-123">Im Beispiel wird davon ausgegangen, dass IIS im integrierten Modus ausgeführt wird und die Anwendung den .NET Framework 3,5 SP1 oder eine höhere Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-123">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="0a1bd-124">Dieses Verhalten tritt nicht in früheren Versionen .NET Framework von als der .NET Framework 3,5 SP1 auf.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-124">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="0a1bd-125">Bei den Werten im Beispiel handelt es sich um die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="0a1bd-125">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="0a1bd-126">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="0a1bd-126">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a1bd-127">Namespace</span><span class="sxs-lookup"><span data-stu-id="0a1bd-127">Namespace</span></span>||  
|<span data-ttu-id="0a1bd-128">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="0a1bd-128">Schema Name</span></span>||  
|<span data-ttu-id="0a1bd-129">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0a1bd-129">Validation File</span></span>||  
|<span data-ttu-id="0a1bd-130">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="0a1bd-130">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="0a1bd-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a1bd-131">See also</span></span>

- [<span data-ttu-id="0a1bd-132">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0a1bd-132">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
