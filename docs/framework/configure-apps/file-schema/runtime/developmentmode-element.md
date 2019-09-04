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
ms.openlocfilehash: 0253c3ced52b575097fe5d18abb8ce188c0164fb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252698"
---
# <a name="developmentmode-element"></a><span data-ttu-id="e1751-102">\<DevelopmentMode-> Element</span><span class="sxs-lookup"><span data-stu-id="e1751-102">\<developmentMode> Element</span></span>
<span data-ttu-id="e1751-103">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1751-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="e1751-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1751-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1751-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1751-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e1751-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<DevelopmentMode->**</span><span class="sxs-lookup"><span data-stu-id="e1751-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1751-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1751-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1751-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1751-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e1751-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1751-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1751-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1751-110">Attributes</span></span>  
  
|<span data-ttu-id="e1751-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e1751-111">Attribute</span></span>|<span data-ttu-id="e1751-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1751-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1751-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="e1751-113">**developerInstallation**</span></span>|<span data-ttu-id="e1751-114">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1751-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="e1751-115">DeveloperInstallation-Attribut</span><span class="sxs-lookup"><span data-stu-id="e1751-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="e1751-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e1751-116">Value</span></span>|<span data-ttu-id="e1751-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1751-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1751-118">**true**</span><span class="sxs-lookup"><span data-stu-id="e1751-118">**true**</span></span>|<span data-ttu-id="e1751-119">Sucht Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1751-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="e1751-120">**false**</span><span class="sxs-lookup"><span data-stu-id="e1751-120">**false**</span></span>|<span data-ttu-id="e1751-121">Sucht nicht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1751-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="e1751-122">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e1751-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1751-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1751-123">Child Elements</span></span>  
 <span data-ttu-id="e1751-124">Keine</span><span class="sxs-lookup"><span data-stu-id="e1751-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1751-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1751-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e1751-126">Element</span><span class="sxs-lookup"><span data-stu-id="e1751-126">Element</span></span>|<span data-ttu-id="e1751-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1751-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1751-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e1751-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e1751-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e1751-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1751-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1751-130">Remarks</span></span>  
 <span data-ttu-id="e1751-131">Verwenden Sie diese Einstellung nur zur Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="e1751-131">Use this setting only at development time.</span></span> <span data-ttu-id="e1751-132">Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="e1751-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="e1751-133">Es wird einfach die erste gefundene Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1751-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1751-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1751-134">Example</span></span>  
 <span data-ttu-id="e1751-135">Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1751-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1751-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1751-136">See also</span></span>

- [<span data-ttu-id="e1751-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e1751-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e1751-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e1751-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e1751-139">Vorgehensweise: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="e1751-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
