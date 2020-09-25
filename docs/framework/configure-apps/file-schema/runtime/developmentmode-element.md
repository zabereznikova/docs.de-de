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
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205021"
---
# <a name="developmentmode-element"></a><span data-ttu-id="4b389-102">\<developmentMode>-Element</span><span class="sxs-lookup"><span data-stu-id="4b389-102">\<developmentMode> Element</span></span>

<span data-ttu-id="4b389-103">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b389-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="4b389-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b389-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b389-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b389-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4b389-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b389-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b389-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b389-107">Attributes</span></span>  
  
|<span data-ttu-id="4b389-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4b389-108">Attribute</span></span>|<span data-ttu-id="4b389-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b389-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b389-110">**DeveloperInstallation**</span><span class="sxs-lookup"><span data-stu-id="4b389-110">**developerInstallation**</span></span>|<span data-ttu-id="4b389-111">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b389-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="4b389-112">DeveloperInstallation-Attribut</span><span class="sxs-lookup"><span data-stu-id="4b389-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="4b389-113">Wert</span><span class="sxs-lookup"><span data-stu-id="4b389-113">Value</span></span>|<span data-ttu-id="4b389-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b389-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b389-115">**true**</span><span class="sxs-lookup"><span data-stu-id="4b389-115">**true**</span></span>|<span data-ttu-id="4b389-116">Sucht Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b389-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="4b389-117">**false**</span><span class="sxs-lookup"><span data-stu-id="4b389-117">**false**</span></span>|<span data-ttu-id="4b389-118">Sucht nicht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b389-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="4b389-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="4b389-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b389-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b389-120">Child Elements</span></span>  

 <span data-ttu-id="4b389-121">Keine</span><span class="sxs-lookup"><span data-stu-id="4b389-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b389-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b389-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4b389-123">Element</span><span class="sxs-lookup"><span data-stu-id="4b389-123">Element</span></span>|<span data-ttu-id="4b389-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b389-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b389-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4b389-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4b389-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4b389-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b389-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4b389-127">Remarks</span></span>  

 <span data-ttu-id="4b389-128">Verwenden Sie diese Einstellung nur zur Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="4b389-128">Use this setting only at development time.</span></span> <span data-ttu-id="4b389-129">Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="4b389-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="4b389-130">Es wird einfach die erste gefundene Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b389-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b389-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b389-131">Example</span></span>  

 <span data-ttu-id="4b389-132">Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b389-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b389-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b389-133">See also</span></span>

- [<span data-ttu-id="4b389-134">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4b389-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4b389-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="4b389-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4b389-136">Vorgehensweise: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="4b389-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
