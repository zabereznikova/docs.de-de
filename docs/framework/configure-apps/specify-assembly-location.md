---
title: Festlegen des Speicherortes einer Assembly
description: Weitere Informationen finden Sie unter Angeben des Speicher Orts einer Assembly in .net mit dem CodeBase-Element oder dem probingelement in einer XML-Konfigurationsdatei.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 3b24ff99eee9027d507ef89ca855162f221f826a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555119"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="94240-103">Festlegen des Speicherortes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="94240-103">Specifying an Assembly's Location</span></span>
<span data-ttu-id="94240-104">Es gibt zwei Möglichkeiten, den Speicherort einer Assembly anzugeben:</span><span class="sxs-lookup"><span data-stu-id="94240-104">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="94240-105">Verwenden des- [\<codeBase>](./file-schema/runtime/codebase-element.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="94240-105">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="94240-106">Verwenden des- [\<probing>](./file-schema/runtime/probing-element.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="94240-106">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="94240-107">Sie können auch das [.NET Framework-Konfigurations Tool (Mscorcfg. msc)](/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) verwenden, um Assemblyspeicher Orte anzugeben oder Speicherorte anzugeben, an denen die Common Language Runtime nach Assemblys suchen soll.</span><span class="sxs-lookup"><span data-stu-id="94240-107">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="94240-108">Verwenden des- \<codeBase> Elements</span><span class="sxs-lookup"><span data-stu-id="94240-108">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="94240-109">Sie können das- **\<codeBase>** Element nur in der Computerkonfiguration oder in Herausgeber Richtlinien Dateien verwenden, die auch die Assemblyversion umleiten</span><span class="sxs-lookup"><span data-stu-id="94240-109">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="94240-110">Wenn die Laufzeit bestimmt, welche Assemblyversion verwendet werden soll, wendet Sie die Codebasis Einstellung aus der Datei an, die die Version bestimmt.</span><span class="sxs-lookup"><span data-stu-id="94240-110">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="94240-111">Wenn keine Codebasis angegeben wird, testet die Runtime die Assembly auf die normale Weise.</span><span class="sxs-lookup"><span data-stu-id="94240-111">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="94240-112">Weitere Informationen finden Sie unter so sucht Common Language [Runtime](../deployment/how-the-runtime-locates-assemblies.md)nach Assemblys.</span><span class="sxs-lookup"><span data-stu-id="94240-112">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="94240-113">Im folgenden Beispiel wird gezeigt, wie der Speicherort einer Assembly angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="94240-113">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="94240-114">Das **Versions** Attribut ist für alle Assemblys mit starkem Namen erforderlich, sollte jedoch nicht für Assemblys mit starkem Namen ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="94240-114">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="94240-115">Das- **\<codeBase>** Element benötigt das **href** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="94240-115">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="94240-116">Sie können keine Versions Bereiche im- **\<codeBase>** Element angeben.</span><span class="sxs-lookup"><span data-stu-id="94240-116">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94240-117">Wenn Sie einen Code Basis Hinweis für eine Assembly bereitstellen, die nicht mit starkem Namen benannt ist, muss der Hinweis auf die Anwendungs Basis oder auf ein Unterverzeichnis des Anwendungs Basisverzeichnisses zeigen.</span><span class="sxs-lookup"><span data-stu-id="94240-117">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="94240-118">Verwenden des- \<probing> Elements</span><span class="sxs-lookup"><span data-stu-id="94240-118">Using the \<probing> Element</span></span>  
 <span data-ttu-id="94240-119">Die Common Language Runtime sucht Assemblys, für die keine Codebasis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="94240-119">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="94240-120">Weitere Informationen zur Überprüfung finden Sie unter [so](../deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.</span><span class="sxs-lookup"><span data-stu-id="94240-120">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="94240-121">Sie können das- [\<probing>](./file-schema/runtime/probing-element.md) Element in der Anwendungs Konfigurationsdatei verwenden, um Unterverzeichnisse anzugeben, die die Common Language Runtime beim Suchen einer Assembly durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="94240-121">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="94240-122">Im folgenden Beispiel wird gezeigt, wie Sie die Verzeichnisse angeben, die die Laufzeit durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="94240-122">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="94240-123">Das **privatePath** -Attribut enthält die Verzeichnisse, die von der Laufzeit nach Assemblys durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="94240-123">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="94240-124">Wenn sich die Anwendung unter c:\Programme\MyApp befindet, sucht die Runtime nach Assemblys, die keine Codebasis in c:\Programme\MyApp\Bin, c:\Programme\MyApp\Bin2\Subbin und c:\Programme\MyApp\Bin3. angeben.</span><span class="sxs-lookup"><span data-stu-id="94240-124">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="94240-125">Die in **privatePath** angegebenen Verzeichnisse müssen Unterverzeichnisse des Basisverzeichnisses der Anwendung sein.</span><span class="sxs-lookup"><span data-stu-id="94240-125">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94240-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94240-126">See also</span></span>

- [<span data-ttu-id="94240-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="94240-127">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="94240-128">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="94240-128">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="94240-129">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="94240-129">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="94240-130">Konfigurieren von Apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="94240-130">Configuring Apps by using Configuration Files</span></span>](index.md)
