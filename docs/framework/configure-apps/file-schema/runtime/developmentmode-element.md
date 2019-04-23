---
title: <developmentMode>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf840035150f08c894c984213af9a0abe6e95af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192055"
---
# <a name="developmentmode-element"></a><span data-ttu-id="7d4e6-102">\<DevelopmentMode >-Element</span><span class="sxs-lookup"><span data-stu-id="7d4e6-102">\<developmentMode> Element</span></span>
<span data-ttu-id="7d4e6-103">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="7d4e6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d4e6-104">\<configuration></span></span>  
<span data-ttu-id="7d4e6-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7d4e6-105">\<runtime></span></span>  
<span data-ttu-id="7d4e6-106">\<developmentMode></span><span class="sxs-lookup"><span data-stu-id="7d4e6-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d4e6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d4e6-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d4e6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7d4e6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7d4e6-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d4e6-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d4e6-110">Attributes</span></span>  
  
|<span data-ttu-id="7d4e6-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7d4e6-111">Attribute</span></span>|<span data-ttu-id="7d4e6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d4e6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d4e6-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="7d4e6-113">**developerInstallation**</span></span>|<span data-ttu-id="7d4e6-114">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="7d4e6-115">developerInstallation-Attribut</span><span class="sxs-lookup"><span data-stu-id="7d4e6-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="7d4e6-116">Wert</span><span class="sxs-lookup"><span data-stu-id="7d4e6-116">Value</span></span>|<span data-ttu-id="7d4e6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d4e6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d4e6-118">**true**</span><span class="sxs-lookup"><span data-stu-id="7d4e6-118">**true**</span></span>|<span data-ttu-id="7d4e6-119">Sucht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="7d4e6-120">**false**</span><span class="sxs-lookup"><span data-stu-id="7d4e6-120">**false**</span></span>|<span data-ttu-id="7d4e6-121">Sucht nicht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="7d4e6-122">Dies ist der Standardwert</span><span class="sxs-lookup"><span data-stu-id="7d4e6-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d4e6-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d4e6-123">Child Elements</span></span>  
 <span data-ttu-id="7d4e6-124">Keine</span><span class="sxs-lookup"><span data-stu-id="7d4e6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d4e6-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d4e6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7d4e6-126">Element</span><span class="sxs-lookup"><span data-stu-id="7d4e6-126">Element</span></span>|<span data-ttu-id="7d4e6-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d4e6-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7d4e6-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7d4e6-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d4e6-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d4e6-130">Remarks</span></span>  
 <span data-ttu-id="7d4e6-131">Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-131">Use this setting only at development time.</span></span> <span data-ttu-id="7d4e6-132">Die Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen finden Sie in die DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="7d4e6-133">Sie verwendet einfach die erste Assembly gefundenen.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d4e6-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d4e6-134">Example</span></span>  
 <span data-ttu-id="7d4e6-135">Das folgende Beispiel zeigt, wie Sie dazu führen, dass die Runtime sucht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d4e6-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d4e6-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d4e6-136">See also</span></span>

- [<span data-ttu-id="7d4e6-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="7d4e6-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7d4e6-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="7d4e6-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7d4e6-139">Vorgehensweise: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="7d4e6-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
