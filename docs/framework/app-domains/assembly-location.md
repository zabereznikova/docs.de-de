---
title: Assemblyspeicherort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e069c1636004896bfb193fd70a352195ba045865
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-location"></a><span data-ttu-id="ee2a6-102">Assemblyspeicherort</span><span class="sxs-lookup"><span data-stu-id="ee2a6-102">Assembly Location</span></span>
<span data-ttu-id="ee2a6-103">Der Speicherort einer Assembly bestimmt, ob die Common Language Runtime diese finden kann, wenn auf sie verwiesen wird. Ebenso bestimmt er, ob die Assembly für andere Assemblys freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="ee2a6-104">Sie können eine Assembly in den folgenden Speicherorten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="ee2a6-104">You can deploy an assembly in the following locations:</span></span>  
  
-   <span data-ttu-id="ee2a6-105">Die Verzeichnisse und Unterverzeichnisse der Anwendung</span><span class="sxs-lookup"><span data-stu-id="ee2a6-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="ee2a6-106">Dies ist der häufigste Speicherort für das Bereitstellen einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="ee2a6-107">Das Unterverzeichnis des Stammverzeichnisses einer Anwendung kann auf der Sprache oder der Kultur basieren.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="ee2a6-108">Wenn eine Assembly über Informationen im Kulturattribut verfügt, muss sie sich in einem Unterverzeichnis im Anwendungsverzeichnis mit dem Kulturnamen befinden.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
-   <span data-ttu-id="ee2a6-109">Im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="ee2a6-110">Dabei handelt es sich um einen computerweiten Codecache, der überall dort installiert wird, wo auch die Common Language Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="ee2a6-111">Wenn Sie eine Assembly für mehrere Anwendungen freigeben möchten, sollten Sie die Assembly in den meisten Fällen im globalen Assemblycache bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="ee2a6-112">Auf einem HTTP-Server</span><span class="sxs-lookup"><span data-stu-id="ee2a6-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="ee2a6-113">Eine auf einem HTTP-Server bereitgestellte Assembly muss einen starken Namen haben. Sie zeigen im Codebasisabschnitt Ihrer Anwendungskonfigurationsdatei auf die Assembly.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2a6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee2a6-114">See Also</span></span>  
 [<span data-ttu-id="ee2a6-115">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="ee2a6-115">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="ee2a6-116">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="ee2a6-116">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="ee2a6-117">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="ee2a6-117">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="ee2a6-118">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="ee2a6-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
