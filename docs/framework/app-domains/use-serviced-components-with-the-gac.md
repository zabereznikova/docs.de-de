---
title: Verwenden von Serviced Components mit dem globalen Assemblycache
description: Verwenden Sie verarbeitete Komponenten (COM+-Komponenten mit verwaltetem Code) mit dem globalen Assemblycache in .NET. Ermitteln Sie, ob die CLR- und COM+-Dienste Nicht-GAC-Komponenten verarbeiten können.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
ms.openlocfilehash: 6b7371865b7b1cedda0ee03b2cc28c74b5c3da0b
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104482"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="cadb0-104">Verwenden von Serviced Components mit dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="cadb0-104">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="cadb0-105">Serviced Components (COM+-Komponenten mit verwaltetem Code) sollten im globalen Assemblycache abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cadb0-105">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="cadb0-106">Nur in bestimmten Szenarios können die Common Language Runtime und die COM+-Dienste mit Serviced Components umgehen, die sich nicht im globalen Assemblycache befinden.</span><span class="sxs-lookup"><span data-stu-id="cadb0-106">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="cadb0-107">Folgende Beispielszenarien verdeutlichen dies:</span><span class="sxs-lookup"><span data-stu-id="cadb0-107">The following scenarios illustrate this:</span></span>  
  
- <span data-ttu-id="cadb0-108">Für Serviced Components in einer COM+-Serveranwendung muss sich die Assembly, die die Komponenten enthält, im globalen Assemblycache befinden. Der Grund dafür ist, dass die Dllhost.exe-Datei nicht in dem Verzeichnis ausgeführt werden kann, das die Serviced Components enthält.</span><span class="sxs-lookup"><span data-stu-id="cadb0-108">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
- <span data-ttu-id="cadb0-109">Bei Serviced Components in einer COM+-Bibliotheksanwendung können die Common Language Runtime und die COM+-Dienste durch Durchsuchen des aktuellen Verzeichnisses den Verweis auf die Assembly auflösen.</span><span class="sxs-lookup"><span data-stu-id="cadb0-109">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="cadb0-110">Demzufolge muss sich in diesem Fall die Assembly nicht unbedingt im globalen Assemblycache befinden.</span><span class="sxs-lookup"><span data-stu-id="cadb0-110">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
- <span data-ttu-id="cadb0-111">Bei Serviced Components in einer ASP.NET-Anwendung stellt sich die Situation anders dar.</span><span class="sxs-lookup"><span data-stu-id="cadb0-111">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="cadb0-112">Wenn Sie die Assembly, die Serviced Components enthält, im Verzeichnis „bin“ des Anwendungsstamms ablegen und bedarfsabhängige Registrierung verwenden, wird die Assembly mittels Spiegelung in den Downloadcache kopiert, da ASP.NET die Spiegelungsfunktionen der Common Language Runtime verwendet.</span><span class="sxs-lookup"><span data-stu-id="cadb0-112">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cadb0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cadb0-113">See also</span></span>

- [<span data-ttu-id="cadb0-114">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="cadb0-114">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="cadb0-115">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="cadb0-115">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
