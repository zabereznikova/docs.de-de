---
title: "Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dedbd90cdc6f33bfa03ce5e38138ca3b23178b95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="43b0a-102">Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)</span><span class="sxs-lookup"><span data-stu-id="43b0a-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="43b0a-103">Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="43b0a-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="43b0a-104">Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.</span><span class="sxs-lookup"><span data-stu-id="43b0a-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="43b0a-105">Freigeben einer Assembly</span><span class="sxs-lookup"><span data-stu-id="43b0a-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="43b0a-106">Erstellen Ihrer Assembly.</span><span class="sxs-lookup"><span data-stu-id="43b0a-106">Create your assembly.</span></span> <span data-ttu-id="43b0a-107">Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="43b0a-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="43b0a-108">Weisen Sie Ihrer Assembly einen starken Namen zu.</span><span class="sxs-lookup"><span data-stu-id="43b0a-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="43b0a-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="43b0a-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="43b0a-110">Weisen Sie Ihrer Assembly Versionsinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="43b0a-110">Assign version information to your assembly.</span></span> <span data-ttu-id="43b0a-111">Weitere Informationen dazu finden Sie unter [Assemblyversionen](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="43b0a-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="43b0a-112">Fügen Sie Ihre Assembly in den globalen Assemblycache ein.</span><span class="sxs-lookup"><span data-stu-id="43b0a-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="43b0a-113">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly in den globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="43b0a-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="43b0a-114">Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="43b0a-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="43b0a-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="43b0a-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b0a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43b0a-116">See Also</span></span>  
 [<span data-ttu-id="43b0a-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="43b0a-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="43b0a-118">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="43b0a-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
