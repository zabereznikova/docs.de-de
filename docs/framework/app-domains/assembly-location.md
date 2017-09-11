---
title: Assemblyspeicherort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3bc0fc4e099540a87832b225aa0a3c262c54e9c3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="assembly-location"></a><span data-ttu-id="072d7-102">Assemblyspeicherort</span><span class="sxs-lookup"><span data-stu-id="072d7-102">Assembly Location</span></span>
<span data-ttu-id="072d7-103">Der Speicherort einer Assembly bestimmt, ob die Common Language Runtime diese finden kann, wenn auf sie verwiesen wird. Ebenso bestimmt er, ob die Assembly für andere Assemblys freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="072d7-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="072d7-104">Sie können eine Assembly in den folgenden Speicherorten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="072d7-104">You can deploy an assembly in the following locations:</span></span>  
  
-   <span data-ttu-id="072d7-105">Die Verzeichnisse und Unterverzeichnisse der Anwendung</span><span class="sxs-lookup"><span data-stu-id="072d7-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="072d7-106">Dies ist der häufigste Speicherort für das Bereitstellen einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="072d7-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="072d7-107">Das Unterverzeichnis des Stammverzeichnisses einer Anwendung kann auf der Sprache oder der Kultur basieren.</span><span class="sxs-lookup"><span data-stu-id="072d7-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="072d7-108">Wenn eine Assembly über Informationen im Kulturattribut verfügt, muss sie sich in einem Unterverzeichnis im Anwendungsverzeichnis mit dem Kulturnamen befinden.</span><span class="sxs-lookup"><span data-stu-id="072d7-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
-   <span data-ttu-id="072d7-109">Im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="072d7-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="072d7-110">Dabei handelt es sich um einen computerweiten Codecache, der überall dort installiert wird, wo auch die Common Language Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="072d7-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="072d7-111">Wenn Sie eine Assembly für mehrere Anwendungen freigeben möchten, sollten Sie die Assembly in den meisten Fällen im globalen Assemblycache bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="072d7-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="072d7-112">Auf einem HTTP-Server</span><span class="sxs-lookup"><span data-stu-id="072d7-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="072d7-113">Eine auf einem HTTP-Server bereitgestellte Assembly muss einen starken Namen haben. Sie zeigen im Codebasisabschnitt Ihrer Anwendungskonfigurationsdatei auf die Assembly.</span><span class="sxs-lookup"><span data-stu-id="072d7-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072d7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="072d7-114">See Also</span></span>  
 <span data-ttu-id="072d7-115">[Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="072d7-115">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="072d7-116">[Globaler Assemblycache](../../../docs/framework/app-domains/gac.md) </span><span class="sxs-lookup"><span data-stu-id="072d7-116">[Global Assembly Cache](../../../docs/framework/app-domains/gac.md) </span></span>  
 <span data-ttu-id="072d7-117">[So sucht die Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="072d7-117">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 [<span data-ttu-id="072d7-118">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="072d7-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

