---
title: 'Vorgehensweise: Laden und Entladen von Assemblys (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd52a1094dba16c7e1bcba5bface9e13747cd4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="19dff-102">Vorgehensweise: Laden und Entladen von Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19dff-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="19dff-103">Assemblys, auf die das Programm verweist, werden automatisch zur Buildzeit geladen. Es ist jedoch ebenfalls möglich, bestimmte Assemblys zur Laufzeit in die aktuelle Anwendungsdomäne zu laden.</span><span class="sxs-lookup"><span data-stu-id="19dff-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="19dff-104">Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="19dff-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="19dff-105">Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="19dff-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="19dff-106">Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="19dff-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="19dff-107">Wenn Sie nur einige Assemblys entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen.</span><span class="sxs-lookup"><span data-stu-id="19dff-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="19dff-108">Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="19dff-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="19dff-109">So laden Sie eine Assembly in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="19dff-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="19dff-110">Verwenden Sie eine der Load-Methoden in den <xref:System.AppDomain>-Klassen und in den <xref:System.Reflection>-Klassen.</span><span class="sxs-lookup"><span data-stu-id="19dff-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="19dff-111">Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="19dff-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="19dff-112">So entladen Sie eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="19dff-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="19dff-113">Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="19dff-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="19dff-114">Verwenden Sie die `Unload`-Methode von <xref:System.AppDomain>, um die Anwendungsdomänen zu entladen.</span><span class="sxs-lookup"><span data-stu-id="19dff-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="19dff-115">Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="19dff-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19dff-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19dff-116">See Also</span></span>  
 [<span data-ttu-id="19dff-117">Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="19dff-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="19dff-118">Assemblys und der globale Assemblycache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19dff-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="19dff-119">Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="19dff-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
