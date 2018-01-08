---
title: "Assemblys und parallele Ausführung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67e7ecd82e76026bdc7e2252c76c182915d2cda1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="daff9-102">Assemblys und parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="daff9-102">Assemblies and Side-by-Side Execution</span></span>
<span data-ttu-id="daff9-103">Als parallele Ausführung wird die Möglichkeit bezeichnet, mehrere Versionen einer Anwendung oder einer Komponente auf demselben Computer zu speichern und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="daff9-103">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="daff9-104">Das bedeutet, dass Sie gleichzeitig mehrere Versionen der Common Language Runtime sowie mehrere Versionen von Anwendungen und Komponenten, die eine Version der Common Language Runtime verwenden, gleichzeitig auf demselben Computer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="daff9-104">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="daff9-105">Durch die parallele Ausführung können Sie besser steuern, an welche Version einer Komponente eine Anwendung gebunden wird und welche Version der Common Language Runtime eine Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="daff9-105">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
 <span data-ttu-id="daff9-106">Die parallele Speicherung und Ausführung verschiedener Versionen derselben Assembly wird durch starke Namen systematisch unterstützt, und es ist integraler Bestandteil der Infrastruktur der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="daff9-106">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="daff9-107">Da die Versionsnummer zur Identität einer Assembly mit starkem Namen gehört, kann die Laufzeit mehrere Versionen derselben Assembly im globalen Assemblycache speichern und diese Assemblys zur Laufzeit laden.</span><span class="sxs-lookup"><span data-stu-id="daff9-107">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
 <span data-ttu-id="daff9-108">Obwohl die Laufzeit das Erstellen von parallel ausführbaren Anwendungen unterstützt, werden diese nicht automatisch parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="daff9-108">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="daff9-109">Weitere Informationen zur Erstellung von Anwendungen für die parallele Ausführung finden Sie unter [Guidelines for Creating Components for Side-by-Side Execution (Richtlinien für die Erstellung von Komponenten für die parallele Ausführung)](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="daff9-109">For more information on creating applications for side-by-side execution, see [Guidelines for Creating Components for Side-by-Side Execution](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daff9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daff9-110">See Also</span></span>  
 [<span data-ttu-id="daff9-111">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="daff9-111">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="daff9-112">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="daff9-112">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
