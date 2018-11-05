---
title: Erstellen von Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df8590b38ace0abcc370f94852a35569b95c4a2d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582449"
---
# <a name="creating-assemblies"></a><span data-ttu-id="152c6-102">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="152c6-102">Creating Assemblies</span></span>

<span data-ttu-id="152c6-103">Sie können Einfach- oder Mehrfachdateiassemblys mit einer IDE wie Visual Studio oder mit den vom [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bereitgestellten Compilern und Tools entwickeln.</span><span class="sxs-lookup"><span data-stu-id="152c6-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span> <span data-ttu-id="152c6-104">Die einfachste Assembly ist eine einzelne Datei mit einem einfachen Namen. Diese wird in eine einzige Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="152c6-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="152c6-105">Auf diese Assembly kann nicht von anderen Assemblys außerhalb des Anwendungsverzeichnisses verwiesen werden. Außerdem wird sie keiner Versionsüberprüfung unterzogen.</span><span class="sxs-lookup"><span data-stu-id="152c6-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="152c6-106">Um die Anwendung, die aus der Assembly besteht, zu deinstallieren, müssen Sie nur das Verzeichnis löschen, in dem sie sich befindet.</span><span class="sxs-lookup"><span data-stu-id="152c6-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="152c6-107">Viele Entwickler benötigen nur eine Assembly mit diesen Funktionen, um eine Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="152c6-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="152c6-108">Sie können eine Mehrfachdateiassembly aus mehreren Codemodulen und Ressourcendateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="152c6-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="152c6-109">Außerdem können Sie eine Assembly erstellen, die von mehrere Anwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="152c6-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="152c6-110">Eine freigegebene Assembly muss einen starken Namen haben. Sie kann im globalen Assemblycache bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="152c6-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="152c6-111">Beim Gruppieren von Codemodulen und Ressourcen in Assemblys stehen Ihnen mehrere Optionen zur Verfügung. Diese hängen von folgenden Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="152c6-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

-   <span data-ttu-id="152c6-112">Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="152c6-112">Versioning</span></span>

     <span data-ttu-id="152c6-113">Gruppieren von Modulen, die die gleichen Versionsinformationen haben sollten</span><span class="sxs-lookup"><span data-stu-id="152c6-113">Group modules that should have the same version information.</span></span>

-   <span data-ttu-id="152c6-114">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="152c6-114">Deployment</span></span>

     <span data-ttu-id="152c6-115">Gruppieren von Modulen und Ressourcen, die Ihr Bereitstellungsmodell unterstützen</span><span class="sxs-lookup"><span data-stu-id="152c6-115">Group code modules and resources that support your model of deployment.</span></span>

-   <span data-ttu-id="152c6-116">Wiederverwendung</span><span class="sxs-lookup"><span data-stu-id="152c6-116">Reuse</span></span>

     <span data-ttu-id="152c6-117">Gruppieren von Modulen, wenn diese logisch für bestimmte Zwecke zusammen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="152c6-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="152c6-118">Beispielsweise eine Assembly, die aus Typen und Klassen besteht, die unregelmäßig zur Wartung eines Programms verwendet werden, kann in die gleiche Assembly platziert werden.</span><span class="sxs-lookup"><span data-stu-id="152c6-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="152c6-119">Zusätzlich sollten Typen, die Sie für mehrere Anwendungen freigeben möchten, in einer Assembly gruppiert sein. Diese Assembly sollte mit einem starken Namen signiert werden.</span><span class="sxs-lookup"><span data-stu-id="152c6-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

-   <span data-ttu-id="152c6-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="152c6-120">Security</span></span>

     <span data-ttu-id="152c6-121">Gruppieren von Modulen, die Typen enthalten, die die gleichen Sicherheitsberechtigungen erfordern</span><span class="sxs-lookup"><span data-stu-id="152c6-121">Group modules containing types that require the same security permissions.</span></span>

-   <span data-ttu-id="152c6-122">Bewerten</span><span class="sxs-lookup"><span data-stu-id="152c6-122">Scoping</span></span>

     <span data-ttu-id="152c6-123">Gruppieren von Modulen, die Typen enthalten, deren Sichtbarkeit auf die gleiche Assembly eingeschränkt sein soll</span><span class="sxs-lookup"><span data-stu-id="152c6-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="152c6-124">Wenn Sie Assemblys der Common Language Runtime für nicht verwaltete COM-Anwendungen verfügbar machen, müssen Sie auf Besonderheiten achten.</span><span class="sxs-lookup"><span data-stu-id="152c6-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="152c6-125">Weitere Informationen zum Arbeiten mit nicht verwaltetem Code finden Sie unter [Exposing .NET Framework Components to COM (Verfügbarmachen von .NET Framework-Komponenten in COM)](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="152c6-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="152c6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="152c6-126">See Also</span></span>

- [<span data-ttu-id="152c6-127">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="152c6-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="152c6-128">Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="152c6-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)
- [<span data-ttu-id="152c6-129">Gewusst wie: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="152c6-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [<span data-ttu-id="152c6-130">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="152c6-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="152c6-131">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="152c6-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="152c6-132">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="152c6-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)