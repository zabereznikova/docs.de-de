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
ms.openlocfilehash: 1435ee8ea887b5d7d3e785eef0f25ffed14b1b97
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195271"
---
# <a name="probing-element"></a><span data-ttu-id="b322a-102">\<probing>-Element</span><span class="sxs-lookup"><span data-stu-id="b322a-102">\<probing> Element</span></span>

<span data-ttu-id="b322a-103">Gibt Anwendungs Basis Verzeichnisse für das Common Language Runtime an, das beim Laden von Assemblys gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b322a-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="b322a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b322a-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b322a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b322a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b322a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b322a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b322a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b322a-107">Attributes</span></span>  
  
|<span data-ttu-id="b322a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b322a-108">Attribute</span></span>|<span data-ttu-id="b322a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b322a-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="b322a-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b322a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b322a-111">Gibt die Unterverzeichnisse des Basisverzeichnisses der Anwendung an, die Assemblys enthalten können.</span><span class="sxs-lookup"><span data-stu-id="b322a-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="b322a-112">Trennen Sie jedes Unterverzeichnis mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="b322a-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b322a-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b322a-113">Child Elements</span></span>  

<span data-ttu-id="b322a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="b322a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b322a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b322a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b322a-116">Element</span><span class="sxs-lookup"><span data-stu-id="b322a-116">Element</span></span>|<span data-ttu-id="b322a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b322a-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="b322a-118">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="b322a-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="b322a-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b322a-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b322a-120">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b322a-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b322a-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b322a-121">Example</span></span>  

 <span data-ttu-id="b322a-122">Im folgenden Beispiel wird gezeigt, wie Sie Anwendungs Basis Verzeichnisse angeben, die die Laufzeit nach Assemblys durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="b322a-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b322a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b322a-123">See also</span></span>

- [<span data-ttu-id="b322a-124">Lauf Zeit Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="b322a-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="b322a-125">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b322a-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="b322a-126">Speicherort einer Assembly angeben</span><span class="sxs-lookup"><span data-stu-id="b322a-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="b322a-127">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="b322a-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
