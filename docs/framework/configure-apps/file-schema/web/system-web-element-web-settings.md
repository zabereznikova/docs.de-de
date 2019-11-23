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
ms.openlocfilehash: 5c5c857d4494b6d78b819e56bae4213abc5e2035
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699089"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="cba25-102">\<System. Web >-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="cba25-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="cba25-103">Enthält Informationen dazu, wie die ASP.net-hostingschicht Prozess weites Verhalten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="cba25-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="cba25-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="cba25-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cba25-105">&nbsp;&nbsp; **\<System. Web >**</span><span class="sxs-lookup"><span data-stu-id="cba25-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba25-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cba25-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cba25-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cba25-107">Attributes and Elements</span></span>  

<span data-ttu-id="cba25-108">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cba25-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cba25-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="cba25-109">Attributes</span></span>  

<span data-ttu-id="cba25-110">None.</span><span class="sxs-lookup"><span data-stu-id="cba25-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cba25-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cba25-111">Child Elements</span></span>  
  
|<span data-ttu-id="cba25-112">Element</span><span class="sxs-lookup"><span data-stu-id="cba25-112">Element</span></span>|<span data-ttu-id="cba25-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cba25-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cba25-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="cba25-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="cba25-115">Gibt Konfigurationseinstellungen für IIS-Anwendungs Pools in einer ASPNET. config-Datei an.</span><span class="sxs-lookup"><span data-stu-id="cba25-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cba25-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cba25-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cba25-117">Element</span><span class="sxs-lookup"><span data-stu-id="cba25-117">Element</span></span>|<span data-ttu-id="cba25-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cba25-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cba25-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cba25-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="cba25-120">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cba25-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cba25-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cba25-121">Remarks</span></span>  

<span data-ttu-id="cba25-122">Das `system.web`-Element und sein untergeordnetes `applicationPool` Element wurden dem .NET Framework ab .NET Framework 3,5 SP1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cba25-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="cba25-123">Wenn Sie IIS 7,0 oder höhere Versionen im integrierten Modus ausführen, können Sie mit dieser Element Kombination konfigurieren, wie ASP.NET Threads verwaltet und wie Anforderungen in die Warteschlange eingereiht werden, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cba25-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="cba25-124">Wenn Sie IIS 7,0 oder höhere Versionen im klassischen oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cba25-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cba25-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cba25-125">Example</span></span>  

<span data-ttu-id="cba25-126">Das folgende Beispiel zeigt, wie Sie das Prozess weite Verhalten von ASP.net in der Datei Aspnet. config konfigurieren, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cba25-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="cba25-127">Im Beispiel wird davon ausgegangen, dass IIS im integrierten Modus ausgeführt wird und die Anwendung den .NET Framework 3,5 SP1 oder eine höhere Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="cba25-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="cba25-128">Dieses Verhalten tritt nicht in früheren Versionen .NET Framework von als der .NET Framework 3,5 SP1 auf.</span><span class="sxs-lookup"><span data-stu-id="cba25-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="cba25-129">Bei den Werten im Beispiel handelt es sich um die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="cba25-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="cba25-130">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="cba25-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cba25-131">Namespace</span><span class="sxs-lookup"><span data-stu-id="cba25-131">Namespace</span></span>||  
|<span data-ttu-id="cba25-132">Schemaname</span><span class="sxs-lookup"><span data-stu-id="cba25-132">Schema Name</span></span>||  
|<span data-ttu-id="cba25-133">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cba25-133">Validation File</span></span>||  
|<span data-ttu-id="cba25-134">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="cba25-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="cba25-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cba25-135">See also</span></span>

- [<span data-ttu-id="cba25-136">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="cba25-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
