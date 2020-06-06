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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115861"
---
# <a name="probing-element"></a><span data-ttu-id="2cabf-102">\<probing>-Element</span><span class="sxs-lookup"><span data-stu-id="2cabf-102">\<probing> Element</span></span>
<span data-ttu-id="2cabf-103">Gibt Anwendungs Basis Verzeichnisse für das Common Language Runtime an, das beim Laden von Assemblys gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cabf-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="2cabf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cabf-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cabf-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cabf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2cabf-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cabf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cabf-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cabf-107">Attributes</span></span>  
  
|<span data-ttu-id="2cabf-108">attribute</span><span class="sxs-lookup"><span data-stu-id="2cabf-108">Attribute</span></span>|<span data-ttu-id="2cabf-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2cabf-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="2cabf-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2cabf-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="2cabf-111">Gibt die Unterverzeichnisse des Basisverzeichnisses der Anwendung an, die Assemblys enthalten können.</span><span class="sxs-lookup"><span data-stu-id="2cabf-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="2cabf-112">Trennen Sie jedes Unterverzeichnis mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="2cabf-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cabf-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cabf-113">Child Elements</span></span>  

<span data-ttu-id="2cabf-114">Keine</span><span class="sxs-lookup"><span data-stu-id="2cabf-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2cabf-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cabf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2cabf-116">Element</span><span class="sxs-lookup"><span data-stu-id="2cabf-116">Element</span></span>|<span data-ttu-id="2cabf-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cabf-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="2cabf-118">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="2cabf-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="2cabf-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2cabf-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2cabf-120">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2cabf-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2cabf-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cabf-121">Example</span></span>  
 <span data-ttu-id="2cabf-122">Im folgenden Beispiel wird gezeigt, wie Sie Anwendungs Basis Verzeichnisse angeben, die die Laufzeit nach Assemblys durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="2cabf-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cabf-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cabf-123">See also</span></span>

- [<span data-ttu-id="2cabf-124">Lauf Zeit Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="2cabf-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="2cabf-125">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2cabf-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="2cabf-126">Speicherort einer Assembly angeben</span><span class="sxs-lookup"><span data-stu-id="2cabf-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="2cabf-127">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="2cabf-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
