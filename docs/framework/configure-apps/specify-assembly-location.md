---
title: Angeben einer Assemblys&#39;s-Speicherort
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4a83f1e67377a5ce699301770ff0369f8f760884
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387327"
---
# <a name="specifying-an-assembly39s-location"></a><span data-ttu-id="305ca-102">Angeben einer Assemblys&#39;s-Speicherort</span><span class="sxs-lookup"><span data-stu-id="305ca-102">Specifying an Assembly&#39;s Location</span></span>
<span data-ttu-id="305ca-103">Es gibt zwei Möglichkeiten zum Angeben des Speicherortes einer Assembly:</span><span class="sxs-lookup"><span data-stu-id="305ca-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="305ca-104">Mithilfe der [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="305ca-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="305ca-105">Mithilfe der [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="305ca-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="305ca-106">Sie können auch die [.NET Framework-Konfigurationstool (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) Speicherorte von Assemblys oder Speicherorte für die common Language Runtime nach Assemblys suchen angeben.</span><span class="sxs-lookup"><span data-stu-id="305ca-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="305ca-107">Mithilfe der \<codeBase >-Element</span><span class="sxs-lookup"><span data-stu-id="305ca-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="305ca-108">Sie können die  **\<codeBase >** Element nur im Computer-Konfiguration oder Verleger Richtliniendateien, die auch die Version der Assembly umleiten.</span><span class="sxs-lookup"><span data-stu-id="305ca-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="305ca-109">Wenn die Runtime die zu verwendende Assemblyversion ermittelt wird, gilt es die CodeBase-Einstellung aus der Datei, die die Version bestimmt.</span><span class="sxs-lookup"><span data-stu-id="305ca-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="305ca-110">Wenn keine Codebasis angegeben ist, durchsucht die Runtime für die Assembly, auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="305ca-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="305ca-111">Weitere Informationen finden Sie unter [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="305ca-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="305ca-112">Das folgende Beispiel zeigt, wie Sie des Speicherortes einer Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="305ca-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="305ca-113">Die **Version** Attribut ist für alle Assemblys mit starkem Namen erforderlich, aber für Assemblys ohne starken Namen weggelassen werden soll.</span><span class="sxs-lookup"><span data-stu-id="305ca-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="305ca-114">Die  **\<codeBase >** Element ist erforderlich. die **Href** Attribut.</span><span class="sxs-lookup"><span data-stu-id="305ca-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="305ca-115">Kann nicht angegeben werden versionsbereichen in die  **\<codeBase >** Element.</span><span class="sxs-lookup"><span data-stu-id="305ca-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="305ca-116">Wenn Sie einen CodeBase-Hinweis für eine Assembly, die nicht mit starkem Namen handelt angeben, muss der Hinweis auf der Basis der Anwendung oder einem Unterverzeichnis des Basisverzeichnisses der Anwendung verweisen.</span><span class="sxs-lookup"><span data-stu-id="305ca-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="305ca-117">Mithilfe der \<probing >-Element</span><span class="sxs-lookup"><span data-stu-id="305ca-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="305ca-118">Die Laufzeit sucht Assemblys, die nicht über eine Codebasis von-Tests verfügen.</span><span class="sxs-lookup"><span data-stu-id="305ca-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="305ca-119">Weitere Informationen dazu finden Sie unter [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="305ca-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="305ca-120">Können Sie die [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) Element in der Konfigurationsdatei der Anwendung an Unterverzeichnisse, die Common Language Runtime durchsucht werden sollen, um die Assembly zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="305ca-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="305ca-121">Das folgende Beispiel zeigt, wie Sie die Verzeichnisse angeben, die die Common Language Runtime suchen soll.</span><span class="sxs-lookup"><span data-stu-id="305ca-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="305ca-122">Die **PrivatePath** Attribut enthält die Verzeichnisse, die die Common Language Runtime nach Assemblys suchen soll.</span><span class="sxs-lookup"><span data-stu-id="305ca-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="305ca-123">Wenn die Anwendung unter C:\Program Files\MyApp befindet, sucht die Runtime nach Assemblys, die keine Codebasis in c:\Programme\Microsoft Files\MyApp\Bin, c:\Programme\Microsoft Files\MyApp\Bin2\Subbin und c:\Programme\Microsoft Files\MyApp\Bin3 angeben.</span><span class="sxs-lookup"><span data-stu-id="305ca-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="305ca-124">Die Verzeichnisse im angegebenen **PrivatePath** müssen Unterverzeichnisse des Basisverzeichnisses der Anwendung sein.</span><span class="sxs-lookup"><span data-stu-id="305ca-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305ca-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="305ca-125">See Also</span></span>  
 [<span data-ttu-id="305ca-126">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="305ca-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="305ca-127">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="305ca-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="305ca-128">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="305ca-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="305ca-129">Konfigurieren von .NET Framework-Apps</span><span class="sxs-lookup"><span data-stu-id="305ca-129">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
