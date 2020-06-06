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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117630"
---
# <a name="developmentmode-element"></a><span data-ttu-id="37e20-102">\<developmentMode>-Element</span><span class="sxs-lookup"><span data-stu-id="37e20-102">\<developmentMode> Element</span></span>
<span data-ttu-id="37e20-103">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="37e20-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="37e20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37e20-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37e20-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="37e20-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37e20-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="37e20-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37e20-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="37e20-107">Attributes</span></span>  
  
|<span data-ttu-id="37e20-108">attribute</span><span class="sxs-lookup"><span data-stu-id="37e20-108">Attribute</span></span>|<span data-ttu-id="37e20-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37e20-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37e20-110">**DeveloperInstallation**</span><span class="sxs-lookup"><span data-stu-id="37e20-110">**developerInstallation**</span></span>|<span data-ttu-id="37e20-111">Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="37e20-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="37e20-112">DeveloperInstallation-Attribut</span><span class="sxs-lookup"><span data-stu-id="37e20-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="37e20-113">Wert</span><span class="sxs-lookup"><span data-stu-id="37e20-113">Value</span></span>|<span data-ttu-id="37e20-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37e20-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37e20-115">**true**</span><span class="sxs-lookup"><span data-stu-id="37e20-115">**true**</span></span>|<span data-ttu-id="37e20-116">Sucht Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="37e20-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="37e20-117">**false**</span><span class="sxs-lookup"><span data-stu-id="37e20-117">**false**</span></span>|<span data-ttu-id="37e20-118">Sucht nicht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="37e20-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="37e20-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="37e20-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37e20-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37e20-120">Child Elements</span></span>  
 <span data-ttu-id="37e20-121">Keine</span><span class="sxs-lookup"><span data-stu-id="37e20-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37e20-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37e20-122">Parent Elements</span></span>  
  
|<span data-ttu-id="37e20-123">Element</span><span class="sxs-lookup"><span data-stu-id="37e20-123">Element</span></span>|<span data-ttu-id="37e20-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37e20-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="37e20-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="37e20-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="37e20-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="37e20-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37e20-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="37e20-127">Remarks</span></span>  
 <span data-ttu-id="37e20-128">Verwenden Sie diese Einstellung nur zur Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="37e20-128">Use this setting only at development time.</span></span> <span data-ttu-id="37e20-129">Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="37e20-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="37e20-130">Es wird einfach die erste gefundene Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="37e20-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37e20-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37e20-131">Example</span></span>  
 <span data-ttu-id="37e20-132">Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="37e20-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37e20-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37e20-133">See also</span></span>

- [<span data-ttu-id="37e20-134">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="37e20-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="37e20-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="37e20-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="37e20-136">Vorgehensweise: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="37e20-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
