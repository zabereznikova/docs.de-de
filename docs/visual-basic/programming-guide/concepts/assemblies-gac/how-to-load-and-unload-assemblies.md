---
title: 'Gewusst wie: Laden und Entladen von Assemblys (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e38be72bb58573b532fa42a569563df0be8301d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="f3d58-102">Gewusst wie: Laden und Entladen von Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3d58-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="f3d58-103">Assemblys, auf die das Programm verweist, werden automatisch zur Buildzeit geladen. Es ist jedoch ebenfalls möglich, bestimmte Assemblys zur Laufzeit in die aktuelle Anwendungsdomäne zu laden.</span><span class="sxs-lookup"><span data-stu-id="f3d58-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="f3d58-104">Weitere Informationen finden Sie unter [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span><span class="sxs-lookup"><span data-stu-id="f3d58-104">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
 <span data-ttu-id="f3d58-105">Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="f3d58-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="f3d58-106">Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f3d58-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="f3d58-107">Wenn Sie nur einige Assemblys entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen.</span><span class="sxs-lookup"><span data-stu-id="f3d58-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="f3d58-108">Weitere Informationen finden Sie unter [Gewusst wie: Entladen einer Anwendungsdomäne](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span><span class="sxs-lookup"><span data-stu-id="f3d58-108">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="f3d58-109">So laden Sie eine Assembly in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="f3d58-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="f3d58-110">Verwenden Sie eine der Load-Methoden in den Klassen <xref:System.AppDomain>und <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="f3d58-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="f3d58-111">Weitere Informationen finden Sie unter [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span><span class="sxs-lookup"><span data-stu-id="f3d58-111">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="f3d58-112">So entladen Sie eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="f3d58-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="f3d58-113">Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="f3d58-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="f3d58-114">Verwenden der `Unload` aus <xref:System.AppDomain>, die Anwendungsdomänen zu entladen.</xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="f3d58-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="f3d58-115">Weitere Informationen finden Sie unter [Gewusst wie: Entladen einer Anwendungsdomäne](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span><span class="sxs-lookup"><span data-stu-id="f3d58-115">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d58-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3d58-116">See Also</span></span>  
 <span data-ttu-id="f3d58-117">[Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3d58-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="f3d58-118"> [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3d58-118"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="f3d58-119"> [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span><span class="sxs-lookup"><span data-stu-id="f3d58-119"> [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span></span>
