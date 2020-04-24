---
title: Festlegen des Speicherortes einer Assembly
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646034"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="bb23f-102">Festlegen des Speicherortes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="bb23f-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="bb23f-103">Es gibt zwei Möglichkeiten, den Speicherort einer Assembly anzugeben:</span><span class="sxs-lookup"><span data-stu-id="bb23f-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="bb23f-104">Verwenden des [ \<codeBase>-Elements.](./file-schema/runtime/codebase-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb23f-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="bb23f-105">Verwenden [ \<](./file-schema/runtime/probing-element.md) des>Elements.</span><span class="sxs-lookup"><span data-stu-id="bb23f-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="bb23f-106">Sie können auch das [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) verwenden, um Assemblyspeicherorte anzugeben oder Speicherorte für die Common Language Runtime anzugeben, die für Assemblys untersucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb23f-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="bb23f-107">Verwenden \<des codeBase>-Elements</span><span class="sxs-lookup"><span data-stu-id="bb23f-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="bb23f-108">Sie können das \*\* \<codeBase>-Element\*\* nur in Computerkonfigurations- oder Herausgeberrichtliniendateien verwenden, die auch die Assemblyversion umleiten.</span><span class="sxs-lookup"><span data-stu-id="bb23f-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="bb23f-109">Wenn die Laufzeit bestimmt, welche Assemblyversion verwendet werden soll, wendet sie die Codebasiseinstellung aus der Datei an, die die Version bestimmt.</span><span class="sxs-lookup"><span data-stu-id="bb23f-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="bb23f-110">Wenn keine Codebasis angegeben ist, werden die Laufzeittests für die Assembly auf die normale Weise angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb23f-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="bb23f-111">Weitere Informationen finden Sie unter [So findet die Laufzeit Assemblys](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="bb23f-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="bb23f-112">Das folgende Beispiel zeigt, wie der Speicherort einer Assembly angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bb23f-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="bb23f-113">Das **Versionsattribut** ist für alle Assemblys mit starkem Namen erforderlich, sollte jedoch für Assemblys weggelassen werden, die keinen starken Namen haben.</span><span class="sxs-lookup"><span data-stu-id="bb23f-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="bb23f-114">Das \*\* \<codeBase>-Element\*\* erfordert das **href-Attribut.**</span><span class="sxs-lookup"><span data-stu-id="bb23f-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="bb23f-115">Sie können keine Versionsbereiche im \*\* \<codeBase>-Element\*\* angeben.</span><span class="sxs-lookup"><span data-stu-id="bb23f-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb23f-116">Wenn Sie einen Codebasishinweis für eine Assembly angeben, die keinen starken Namen hat, muss der Hinweis auf die Anwendungsbasis oder ein Unterverzeichnis des Anwendungsbasisverzeichnisses verweisen.</span><span class="sxs-lookup"><span data-stu-id="bb23f-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="bb23f-117">Verwenden \<des> Elements</span><span class="sxs-lookup"><span data-stu-id="bb23f-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="bb23f-118">Die Laufzeit sucht Assemblys, die keine Codebasis haben, indem sie untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="bb23f-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="bb23f-119">Weitere Informationen zum Thema Sondierung finden Sie unter [So findet die Laufzeit Assemblys](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="bb23f-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="bb23f-120">Sie können [ \<](./file-schema/runtime/probing-element.md) das>-Element in der Anwendungskonfigurationsdatei verwenden, um Unterverzeichnisse anzugeben, die die Laufzeit beim Suchen einer Assembly suchen soll.</span><span class="sxs-lookup"><span data-stu-id="bb23f-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="bb23f-121">Das folgende Beispiel zeigt, wie Verzeichnisse angegeben werden, die die Laufzeit durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="bb23f-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="bb23f-122">Das **privatePath-Attribut** enthält die Verzeichnisse, die die Laufzeit nach Assemblys durchsuchen soll.</span><span class="sxs-lookup"><span data-stu-id="bb23f-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="bb23f-123">Wenn sich die Anwendung unter C:-Programmdateien und MyApp befindet, sucht die Laufzeit nach Assemblys, die keine Codebasis in C:-Programmdateien, "MyApp"-Bin, "C:-Programmdateien" und """""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""</span><span class="sxs-lookup"><span data-stu-id="bb23f-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="bb23f-124">Bei den in **privatePath** angegebenen Verzeichnissen müssen es sich um Unterverzeichnisse des Anwendungsbasisverzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="bb23f-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb23f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb23f-125">See also</span></span>

- [<span data-ttu-id="bb23f-126">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="bb23f-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="bb23f-127">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="bb23f-127">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="bb23f-128">So sucht die Laufzeit Assemblys</span><span class="sxs-lookup"><span data-stu-id="bb23f-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="bb23f-129">Konfigurieren von Apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="bb23f-129">Configuring Apps by using Configuration Files</span></span>](index.md)
