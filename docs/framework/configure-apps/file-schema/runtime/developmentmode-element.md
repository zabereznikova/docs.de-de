---
title: '&lt;DevelopmentMode&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a77f93a0dff198821509c2c26f67caa137073ced
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdevelopmentmodegt-element"></a><span data-ttu-id="f2cf8-102">&lt;DevelopmentMode&gt; Element</span><span class="sxs-lookup"><span data-stu-id="f2cf8-102">&lt;developmentMode&gt; Element</span></span>
<span data-ttu-id="f2cf8-103">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="f2cf8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f2cf8-104">\<configuration></span></span>  
<span data-ttu-id="f2cf8-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="f2cf8-105">\<runtime></span></span>  
<span data-ttu-id="f2cf8-106">\<DevelopmentMode ></span><span class="sxs-lookup"><span data-stu-id="f2cf8-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cf8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2cf8-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2cf8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f2cf8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f2cf8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2cf8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f2cf8-110">Attributes</span></span>  
  
|<span data-ttu-id="f2cf8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f2cf8-111">Attribute</span></span>|<span data-ttu-id="f2cf8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2cf8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2cf8-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="f2cf8-113">**developerInstallation**</span></span>|<span data-ttu-id="f2cf8-114">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="f2cf8-115">developerInstallation-Attribut</span><span class="sxs-lookup"><span data-stu-id="f2cf8-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="f2cf8-116">Wert</span><span class="sxs-lookup"><span data-stu-id="f2cf8-116">Value</span></span>|<span data-ttu-id="f2cf8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2cf8-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2cf8-118">**true**</span><span class="sxs-lookup"><span data-stu-id="f2cf8-118">**true**</span></span>|<span data-ttu-id="f2cf8-119">Sucht nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="f2cf8-120">**false**</span><span class="sxs-lookup"><span data-stu-id="f2cf8-120">**false**</span></span>|<span data-ttu-id="f2cf8-121">Sucht nicht nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="f2cf8-122">Dies ist die Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="f2cf8-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2cf8-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2cf8-123">Child Elements</span></span>  
 <span data-ttu-id="f2cf8-124">Keine</span><span class="sxs-lookup"><span data-stu-id="f2cf8-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2cf8-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2cf8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f2cf8-126">Element</span><span class="sxs-lookup"><span data-stu-id="f2cf8-126">Element</span></span>|<span data-ttu-id="f2cf8-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2cf8-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2cf8-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f2cf8-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2cf8-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2cf8-130">Remarks</span></span>  
 <span data-ttu-id="f2cf8-131">Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-131">Use this setting only at development time.</span></span> <span data-ttu-id="f2cf8-132">Die Common Language Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen in die DEVPATH gefunden.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="f2cf8-133">Sie verwendet einfach die erste Assembly gefundenen.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2cf8-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2cf8-134">Example</span></span>  
 <span data-ttu-id="f2cf8-135">Das folgende Beispiel veranschaulicht die dazu führen, dass die Common Language Runtime nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse suchen.</span><span class="sxs-lookup"><span data-stu-id="f2cf8-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2cf8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2cf8-136">See Also</span></span>  
 [<span data-ttu-id="f2cf8-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f2cf8-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="f2cf8-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f2cf8-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f2cf8-139">Gewusst wie: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="f2cf8-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
