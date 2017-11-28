---
title: Verwenden von Serviced Components mit dem globalen Assemblycache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45fd02c4f87d33766741e6fd023f9b40b9964d63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="69b1b-102">Verwenden von Serviced Components mit dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="69b1b-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="69b1b-103">Die Serviced Components (COM+-Komponenten mit verwaltetem Code) sollten im globalen Assemblycache abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="69b1b-103">Serviced components (managed code COM+ components) should be put in the global assembly cache.</span></span> <span data-ttu-id="69b1b-104">Nur in bestimmten Szenarien können die Common Language Runtime und die COM+-Dienste mit Serviced Components umgehen, die sich nicht im globalen Assemblycache befinden.</span><span class="sxs-lookup"><span data-stu-id="69b1b-104">In some scenarios, the common language runtime and COM+ Services can handle serviced components that are not in the global assembly cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="69b1b-105">Folgende Beispielszenarien verdeutlichen dies:</span><span class="sxs-lookup"><span data-stu-id="69b1b-105">The following scenarios illustrate this:</span></span>  
  
-   <span data-ttu-id="69b1b-106">Für Serviced Components in einer COM+-Serveranwendung muss sich die Assembly, die die Komponenten enthält, im globalen Assemblycache befinden. Der Grund dafür ist, dass „Dllhost.exe“ nicht im Verzeichnis ausgeführt werden kann, das die Serviced Components enthält.</span><span class="sxs-lookup"><span data-stu-id="69b1b-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the global assembly cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
-   <span data-ttu-id="69b1b-107">Bei Serviced Components in einer COM+-Bibliotheksanwendung können die Common Language Runtime und die COM+-Dienste durch Durchsuchen des aktuellen Verzeichnisses den Verweis auf die Assembly auflösen.</span><span class="sxs-lookup"><span data-stu-id="69b1b-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="69b1b-108">Demzufolge muss sich in diesem Fall die Assembly nicht unbedingt im globalen Assemblycache befinden.</span><span class="sxs-lookup"><span data-stu-id="69b1b-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="69b1b-109">Bei Serviced Components in einer ASP.NET-Anwendung stellt sich die Situation anders dar.</span><span class="sxs-lookup"><span data-stu-id="69b1b-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="69b1b-110">Wenn Sie die Assembly, die Serviced Components enthält, im Verzeichnis „bin“ des Anwendungsstamms ablegen und bedarfsabhängige Registrierung verwenden, wird die Assembly mittels Spiegelung in den Downloadcache kopiert, da ASP.NET die Spiegelungsfunktionen der Common Language Runtime verwendet.</span><span class="sxs-lookup"><span data-stu-id="69b1b-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b1b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69b1b-111">See Also</span></span>  
 [<span data-ttu-id="69b1b-112">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="69b1b-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="69b1b-113">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="69b1b-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
