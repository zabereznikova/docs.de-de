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
ms.openlocfilehash: 4a062da31740edb8f0c7a4f4db8b09800c687587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117630"
---
# <a name="developmentmode-element"></a><span data-ttu-id="c0119-102">\<DevelopmentMode >-Element</span><span class="sxs-lookup"><span data-stu-id="c0119-102">\<developmentMode> Element</span></span>
<span data-ttu-id="c0119-103">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0119-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="c0119-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0119-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0119-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="c0119-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c0119-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<DevelopmentMode >**</span><span class="sxs-lookup"><span data-stu-id="c0119-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0119-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0119-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0119-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c0119-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c0119-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0119-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0119-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c0119-110">Attributes</span></span>  
  
|<span data-ttu-id="c0119-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c0119-111">Attribute</span></span>|<span data-ttu-id="c0119-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0119-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0119-113">**DeveloperInstallation**</span><span class="sxs-lookup"><span data-stu-id="c0119-113">**developerInstallation**</span></span>|<span data-ttu-id="c0119-114">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0119-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="c0119-115">DeveloperInstallation-Attribut</span><span class="sxs-lookup"><span data-stu-id="c0119-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="c0119-116">Wert</span><span class="sxs-lookup"><span data-stu-id="c0119-116">Value</span></span>|<span data-ttu-id="c0119-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0119-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c0119-118">**true**</span><span class="sxs-lookup"><span data-stu-id="c0119-118">**true**</span></span>|<span data-ttu-id="c0119-119">Sucht Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0119-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="c0119-120">**false**</span><span class="sxs-lookup"><span data-stu-id="c0119-120">**false**</span></span>|<span data-ttu-id="c0119-121">Sucht nicht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0119-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="c0119-122">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="c0119-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0119-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c0119-123">Child Elements</span></span>  
 <span data-ttu-id="c0119-124">Keine</span><span class="sxs-lookup"><span data-stu-id="c0119-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0119-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c0119-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c0119-126">Element</span><span class="sxs-lookup"><span data-stu-id="c0119-126">Element</span></span>|<span data-ttu-id="c0119-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0119-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c0119-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c0119-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c0119-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c0119-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0119-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0119-130">Remarks</span></span>  
 <span data-ttu-id="c0119-131">Verwenden Sie diese Einstellung nur zur Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="c0119-131">Use this setting only at development time.</span></span> <span data-ttu-id="c0119-132">Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c0119-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="c0119-133">Es wird einfach die erste gefundene Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0119-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0119-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0119-134">Example</span></span>  
 <span data-ttu-id="c0119-135">Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0119-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0119-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0119-136">See also</span></span>

- [<span data-ttu-id="c0119-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c0119-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c0119-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c0119-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c0119-139">Gewusst wie: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="c0119-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
