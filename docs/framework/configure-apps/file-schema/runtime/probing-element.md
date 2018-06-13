---
title: '&lt;Probing&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cab16e83466b5954bfebac07dd79c9a8b5e4594
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745002"
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="db735-102">&lt;Probing&gt; Element</span><span class="sxs-lookup"><span data-stu-id="db735-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="db735-103">Gibt Unterverzeichnisse der Anwendungsbasis für die common Language Runtime beim Laden von Assemblys für die Suche an.</span><span class="sxs-lookup"><span data-stu-id="db735-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="db735-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="db735-104">\<configuration></span></span>  
<span data-ttu-id="db735-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="db735-105">\<runtime></span></span>  
<span data-ttu-id="db735-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="db735-106">\<assemblyBinding></span></span>  
<span data-ttu-id="db735-107">\<Probing ></span><span class="sxs-lookup"><span data-stu-id="db735-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db735-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="db735-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db735-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="db735-109">Attributes and Elements</span></span>  
 <span data-ttu-id="db735-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db735-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db735-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="db735-111">Attributes</span></span>  
  
|<span data-ttu-id="db735-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="db735-112">Attribute</span></span>|<span data-ttu-id="db735-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db735-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="db735-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="db735-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="db735-115">Gibt die Unterverzeichnisse des Basisverzeichnisses der Anwendung, die Assemblys enthalten können.</span><span class="sxs-lookup"><span data-stu-id="db735-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="db735-116">Begrenzen Sie die einzelnen Unterverzeichnissen mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="db735-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db735-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db735-117">Child Elements</span></span>  
 <span data-ttu-id="db735-118">Keine</span><span class="sxs-lookup"><span data-stu-id="db735-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db735-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db735-119">Parent Elements</span></span>  
  
|<span data-ttu-id="db735-120">Element</span><span class="sxs-lookup"><span data-stu-id="db735-120">Element</span></span>|<span data-ttu-id="db735-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db735-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="db735-122">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="db735-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="db735-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="db735-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="db735-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="db735-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="db735-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db735-125">Example</span></span>  
 <span data-ttu-id="db735-126">Das folgende Beispiel zeigt, wie Unterverzeichnisse der Anwendungsbasis angeben, die die Common Language Runtime nach Assemblys suchen soll.</span><span class="sxs-lookup"><span data-stu-id="db735-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db735-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db735-127">See Also</span></span>  
 [<span data-ttu-id="db735-128">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="db735-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="db735-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="db735-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="db735-130">Festlegen des Speicherortes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="db735-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="db735-131">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="db735-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
