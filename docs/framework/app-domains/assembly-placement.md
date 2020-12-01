---
title: Assemblypositionierung
description: Lesen Sie sich den Leitfaden zur .NET-Assemblypositionierung innerhalb von Verzeichnissen durch (z. B. im globalen Assemblycache oder im Verzeichnis oder Unterverzeichnis der Anwendung).
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
ms.openlocfilehash: 15ff6edf5887062b0cce918b39beef6c9b618ca2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271551"
---
# <a name="assembly-placement"></a><span data-ttu-id="12892-103">Assemblypositionierung</span><span class="sxs-lookup"><span data-stu-id="12892-103">Assembly Placement</span></span>

<span data-ttu-id="12892-104">Bei den meisten .NET Framework-Anwendungen werden die Assemblys, aus denen eine Anwendung besteht, im Anwendungsverzeichnis, in einem Unterverzeichnis des Anwendungsverzeichnisses oder im globalen Assemblycache (sofern die Assembly freigegeben ist) gesucht.</span><span class="sxs-lookup"><span data-stu-id="12892-104">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="12892-105">Sie können den Speicherort überschreiben, in dem die Common Language Runtime nach einer Assembly sucht, indem Sie das [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) in einer Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="12892-105">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="12892-106">Wenn die Assembly keinen starken Namen aufweist, kann mit dem [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) nur das Anwendungsverzeichnis oder ein Unterverzeichnis als Speicherort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="12892-106">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="12892-107">Wenn die Assembly einen starken Namen aufweist, kann mit dem [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) ein beliebiger Speicherort auf dem Computer oder in einem Netzwerk angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="12892-107">If the assembly has a strong name, the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="12892-108">Ähnliche Regeln gelten für das Suchen von Assemblys, wenn nicht verwalteter Code oder COM-Interop-Anwendungen verwendet werden. Wenn die Assembly für mehrere Anwendungen freigegeben werden soll, muss sie im globalen Assemblycache installiert werden.</span><span class="sxs-lookup"><span data-stu-id="12892-108">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="12892-109">Assemblys, die mit nicht verwaltetem Code verwendet werden, müssen als Typbibliothek exportiert und registriert werden.</span><span class="sxs-lookup"><span data-stu-id="12892-109">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="12892-110">Assemblys, die von COM-Interop verwendet werden, müssen im Katalog registriert werden. In einigen Fällen erfolgt diese Registrierung automatisch.</span><span class="sxs-lookup"><span data-stu-id="12892-110">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12892-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12892-111">See also</span></span>

- [<span data-ttu-id="12892-112">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="12892-112">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="12892-113">Konfigurieren von Apps</span><span class="sxs-lookup"><span data-stu-id="12892-113">Configuring Apps</span></span>](../configure-apps/index.md)
- [<span data-ttu-id="12892-114">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="12892-114">Interoperating with unmanaged code</span></span>](../interop/index.md)
- [<span data-ttu-id="12892-115">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="12892-115">Assemblies in .NET</span></span>](index.md)
