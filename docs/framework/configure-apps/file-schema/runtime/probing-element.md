---
title: <probing>-Element
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
ms.openlocfilehash: ae789e99a1306102c67f2252760e215989132406
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971628"
---
# <a name="probing-element"></a><span data-ttu-id="8751d-102">\<Überprüfung > Elements</span><span class="sxs-lookup"><span data-stu-id="8751d-102">\<probing> Element</span></span>
<span data-ttu-id="8751d-103">Gibt Anwendungs Basis Verzeichnisse für das Common Language Runtime an, das beim Laden von Assemblys gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8751d-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="8751d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8751d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8751d-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="8751d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8751d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="8751d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="8751d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<probing>**</span><span class="sxs-lookup"><span data-stu-id="8751d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8751d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8751d-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8751d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8751d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8751d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8751d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8751d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8751d-111">Attributes</span></span>  
  
|<span data-ttu-id="8751d-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="8751d-112">Attribute</span></span>|<span data-ttu-id="8751d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8751d-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="8751d-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8751d-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="8751d-115">Gibt die Unterverzeichnisse des Basisverzeichnisses der Anwendung an, die Assemblys enthalten können.</span><span class="sxs-lookup"><span data-stu-id="8751d-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="8751d-116">Trennen Sie jedes Unterverzeichnis mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="8751d-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8751d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8751d-117">Child Elements</span></span>  

<span data-ttu-id="8751d-118">Keine</span><span class="sxs-lookup"><span data-stu-id="8751d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8751d-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8751d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8751d-120">Element</span><span class="sxs-lookup"><span data-stu-id="8751d-120">Element</span></span>|<span data-ttu-id="8751d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8751d-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="8751d-122">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="8751d-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="8751d-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8751d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8751d-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8751d-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8751d-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8751d-125">Example</span></span>  
 <span data-ttu-id="8751d-126">Im folgenden Beispiel wird gezeigt, wie Sie Anwendungs Basis Verzeichnisse angeben, die die Laufzeit nach Assemblys durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="8751d-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8751d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8751d-127">See also</span></span>

- [<span data-ttu-id="8751d-128">Lauf Zeit Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="8751d-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="8751d-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="8751d-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="8751d-130">Speicherort einer Assembly angeben</span><span class="sxs-lookup"><span data-stu-id="8751d-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="8751d-131">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="8751d-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
