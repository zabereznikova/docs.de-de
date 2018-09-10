---
title: Assemblypositionierung
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d42b73d1ec20e66d604f19bb836cb7e2778e62f0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505988"
---
# <a name="assembly-placement"></a><span data-ttu-id="abdc6-102">Assemblypositionierung</span><span class="sxs-lookup"><span data-stu-id="abdc6-102">Assembly Placement</span></span>
<span data-ttu-id="abdc6-103">Bei den meisten .NET Framework-Anwendungen werden die Assemblys, aus denen eine Anwendung besteht, im Anwendungsverzeichnis, in einem Unterverzeichnis des Anwendungsverzeichnisses oder im globalen Assemblycache (sofern die Assembly freigegeben ist) gesucht.</span><span class="sxs-lookup"><span data-stu-id="abdc6-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="abdc6-104">Sie können den Speicherort überschreiben, in dem die Common Language Runtime nach einer Assembly sucht, indem Sie das [\<codeBase>-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in einer Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="abdc6-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="abdc6-105">Wenn die Assembly keinen starken Namen hat, kann mit dem [\<codeBase>-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) nur das Anwendungsverzeichnis oder ein Unterverzeichnis als Speicherort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="abdc6-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="abdc6-106">Wenn die Assembly einen starken Namen aufweist, kann mit dem [\<codeBase>-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) ein beliebiger Speicherort auf dem Computer oder im Netzwerk angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="abdc6-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="abdc6-107">Ähnliche Regeln gelten für das Suchen von Assemblys, wenn nicht verwalteter Code oder COM-Interop-Anwendungen verwendet werden. Wenn die Assembly für mehrere Anwendungen freigegeben werden soll, muss sie im globalen Assemblycache installiert werden.</span><span class="sxs-lookup"><span data-stu-id="abdc6-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="abdc6-108">Assemblys, die mit nicht verwaltetem Code verwendet werden, müssen als Typbibliothek exportiert und registriert werden.</span><span class="sxs-lookup"><span data-stu-id="abdc6-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="abdc6-109">Assemblys, die von COM-Interop verwendet werden, müssen im Katalog registriert werden. In einigen Fällen erfolgt diese Registrierung automatisch.</span><span class="sxs-lookup"><span data-stu-id="abdc6-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abdc6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abdc6-110">See Also</span></span>  
 [<span data-ttu-id="abdc6-111">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="abdc6-111">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="abdc6-112">Konfigurieren von Apps</span><span class="sxs-lookup"><span data-stu-id="abdc6-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="abdc6-113">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="abdc6-113">Advanced COM Interoperability</span></span>](https://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="abdc6-114">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="abdc6-114">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
