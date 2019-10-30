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
ms.openlocfilehash: e9e48ea97e1b70fef7fcc78a113e18c5fec23b7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115861"
---
# <a name="probing-element"></a><span data-ttu-id="9b17e-102">\<> Element</span><span class="sxs-lookup"><span data-stu-id="9b17e-102">\<probing> Element</span></span>
<span data-ttu-id="9b17e-103">Gibt Anwendungs Basis Verzeichnisse für das Common Language Runtime an, das beim Laden von Assemblys gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b17e-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="9b17e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b17e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b17e-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="9b17e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9b17e-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > </span><span class="sxs-lookup"><span data-stu-id="9b17e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="9b17e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<durchsuchen **>**</span><span class="sxs-lookup"><span data-stu-id="9b17e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b17e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b17e-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b17e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b17e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b17e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b17e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b17e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b17e-111">Attributes</span></span>  
  
|<span data-ttu-id="9b17e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9b17e-112">Attribute</span></span>|<span data-ttu-id="9b17e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b17e-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="9b17e-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9b17e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b17e-115">Gibt die Unterverzeichnisse des Basisverzeichnisses der Anwendung an, die Assemblys enthalten können.</span><span class="sxs-lookup"><span data-stu-id="9b17e-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="9b17e-116">Trennen Sie jedes Unterverzeichnis mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="9b17e-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b17e-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b17e-117">Child Elements</span></span>  

<span data-ttu-id="9b17e-118">Keine</span><span class="sxs-lookup"><span data-stu-id="9b17e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b17e-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b17e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9b17e-120">Element</span><span class="sxs-lookup"><span data-stu-id="9b17e-120">Element</span></span>|<span data-ttu-id="9b17e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b17e-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="9b17e-122">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="9b17e-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="9b17e-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9b17e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b17e-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9b17e-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b17e-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b17e-125">Example</span></span>  
 <span data-ttu-id="9b17e-126">Im folgenden Beispiel wird gezeigt, wie Sie Anwendungs Basis Verzeichnisse angeben, die die Laufzeit nach Assemblys durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="9b17e-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b17e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b17e-127">See also</span></span>

- [<span data-ttu-id="9b17e-128">Lauf Zeit Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="9b17e-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="9b17e-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="9b17e-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="9b17e-130">Speicherort einer Assembly angeben</span><span class="sxs-lookup"><span data-stu-id="9b17e-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="9b17e-131">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="9b17e-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
