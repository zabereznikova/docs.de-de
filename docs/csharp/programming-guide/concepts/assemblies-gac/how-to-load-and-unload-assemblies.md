---
title: 'Vorgehensweise: Laden und Entladen von Assemblys (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6bf6de24f4cbc3f3bd855b6d2cafa8120ebd90ee
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="d4d4e-102">Vorgehensweise: Laden und Entladen von Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="d4d4e-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="d4d4e-103">Assemblys, auf die das Programm verweist, werden automatisch zur Buildzeit geladen. Es ist jedoch ebenfalls möglich, bestimmte Assemblys zur Laufzeit in die aktuelle Anwendungsdomäne zu laden.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="d4d4e-104">Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d4d4e-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="d4d4e-105">Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="d4d4e-106">Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="d4d4e-107">Wenn Sie nur einige Assemblys entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="d4d4e-108">Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d4d4e-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="d4d4e-109">So laden Sie eine Assembly in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="d4d4e-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="d4d4e-110">Verwenden Sie eine der Load-Methoden in den <xref:System.AppDomain>-Klassen und in den <xref:System.Reflection>-Klassen.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="d4d4e-111">Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d4d4e-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="d4d4e-112">So entladen Sie eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="d4d4e-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="d4d4e-113">Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="d4d4e-114">Verwenden Sie die `Unload`-Methode von <xref:System.AppDomain>, um die Anwendungsdomänen zu entladen.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="d4d4e-115">Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d4d4e-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d4e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4d4e-116">See Also</span></span>  
 <span data-ttu-id="d4d4e-117">[C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4d4e-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d4d4e-118">[Assemblys und der globale Assemblycache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4d4e-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 [<span data-ttu-id="d4d4e-119">Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="d4d4e-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)

