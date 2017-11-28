---
title: Erstellen von Assemblys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5aa4b8fa5422ae126a6027c5fe3358925873782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-assemblies"></a><span data-ttu-id="94fa5-102">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="94fa5-102">Creating Assemblies</span></span>
<span data-ttu-id="94fa5-103">Sie können Einfach- oder Mehrfachdateiassemblys mit einer IDE entwickeln, wie z.B. [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], oder mit den von [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bereitgestellten Compilern und Tools.</span><span class="sxs-lookup"><span data-stu-id="94fa5-103">You can create single-file or multifile assemblies using an IDE, such as [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], or the compilers and tools provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span> <span data-ttu-id="94fa5-104">Die einfachste Assembly ist eine einzelne Datei mit einem einfachen Namen. Diese wird in eine einzige Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="94fa5-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="94fa5-105">Auf diese Assembly kann nicht von anderen Assemblys außerhalb des Anwendungsverzeichnisses verwiesen werden. Außerdem wird sie keiner Versionsüberprüfung unterzogen.</span><span class="sxs-lookup"><span data-stu-id="94fa5-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="94fa5-106">Um die Anwendung, die aus der Assembly besteht, zu deinstallieren, müssen Sie nur das Verzeichnis löschen, in dem sie sich befindet.</span><span class="sxs-lookup"><span data-stu-id="94fa5-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="94fa5-107">Viele Entwickler benötigen nur eine Assembly mit diesen Funktionen, um eine Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="94fa5-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>  
  
 <span data-ttu-id="94fa5-108">Sie können eine Mehrfachdateiassembly aus mehreren Codemodulen und Ressourcendateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="94fa5-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="94fa5-109">Außerdem können Sie eine Assembly erstellen, die von mehrere Anwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="94fa5-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="94fa5-110">Eine freigegebene Assembly muss einen starken Namen haben. Sie kann im globalen Assemblycache bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="94fa5-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="94fa5-111">Beim Gruppieren von Codemodulen und Ressourcen in Assemblys stehen Ihnen mehrere Optionen zur Verfügung. Diese hängen von folgenden Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="94fa5-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>  
  
-   <span data-ttu-id="94fa5-112">Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="94fa5-112">Versioning</span></span>  
  
     <span data-ttu-id="94fa5-113">Gruppieren von Modulen, die die gleichen Versionsinformationen haben sollten</span><span class="sxs-lookup"><span data-stu-id="94fa5-113">Group modules that should have the same version information.</span></span>  
  
-   <span data-ttu-id="94fa5-114">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="94fa5-114">Deployment</span></span>  
  
     <span data-ttu-id="94fa5-115">Gruppieren von Modulen und Ressourcen, die Ihr Bereitstellungsmodell unterstützen</span><span class="sxs-lookup"><span data-stu-id="94fa5-115">Group code modules and resources that support your model of deployment.</span></span>  
  
-   <span data-ttu-id="94fa5-116">Wiederverwendung</span><span class="sxs-lookup"><span data-stu-id="94fa5-116">Reuse</span></span>  
  
     <span data-ttu-id="94fa5-117">Gruppieren von Modulen, wenn diese logisch für bestimmte Zwecke zusammen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="94fa5-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="94fa5-118">Beispielsweise eine Assembly, die aus Typen und Klassen besteht, die unregelmäßig zur Wartung eines Programms verwendet werden, kann in die gleiche Assembly platziert werden.</span><span class="sxs-lookup"><span data-stu-id="94fa5-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="94fa5-119">Zusätzlich sollten Typen, die Sie für mehrere Anwendungen freigeben möchten, in einer Assembly gruppiert sein. Diese Assembly sollte mit einem starken Namen signiert werden.</span><span class="sxs-lookup"><span data-stu-id="94fa5-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>  
  
-   <span data-ttu-id="94fa5-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="94fa5-120">Security</span></span>  
  
     <span data-ttu-id="94fa5-121">Gruppieren von Modulen, die Typen enthalten, die die gleichen Sicherheitsberechtigungen erfordern</span><span class="sxs-lookup"><span data-stu-id="94fa5-121">Group modules containing types that require the same security permissions.</span></span>  
  
-   <span data-ttu-id="94fa5-122">Bewerten</span><span class="sxs-lookup"><span data-stu-id="94fa5-122">Scoping</span></span>  
  
     <span data-ttu-id="94fa5-123">Gruppieren von Modulen, die Typen enthalten, deren Sichtbarkeit auf die gleiche Assembly eingeschränkt sein soll</span><span class="sxs-lookup"><span data-stu-id="94fa5-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>  
  
 <span data-ttu-id="94fa5-124">Wenn Sie Assemblys der Common Language Runtime für nicht verwaltete COM-Anwendungen verfügbar machen, müssen Sie auf Besonderheiten achten.</span><span class="sxs-lookup"><span data-stu-id="94fa5-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="94fa5-125">Weitere Informationen zum Arbeiten mit nicht verwaltetem Code finden Sie unter [Exposing .NET Framework Components to COM (Verfügbarmachen von .NET Framework-Komponenten in COM)](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="94fa5-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fa5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94fa5-126">See Also</span></span>  
 [<span data-ttu-id="94fa5-127">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="94fa5-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="94fa5-128">Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="94fa5-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 [<span data-ttu-id="94fa5-129">Gewusst wie: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="94fa5-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 [<span data-ttu-id="94fa5-130">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="94fa5-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="94fa5-131">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="94fa5-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="94fa5-132">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="94fa5-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
