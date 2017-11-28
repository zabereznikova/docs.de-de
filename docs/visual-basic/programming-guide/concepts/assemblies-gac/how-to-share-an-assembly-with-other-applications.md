---
title: 'Vorgehensweise: Freigeben einer Assembly mit anderen Anwendungen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 491791ba9b6f0cf6da86a160eddf8e78109b11c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="63bd3-102">Vorgehensweise: Freigeben einer Assembly mit anderen Anwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63bd3-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="63bd3-103">Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="63bd3-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="63bd3-104">Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.</span><span class="sxs-lookup"><span data-stu-id="63bd3-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="63bd3-105">Freigeben einer Assembly</span><span class="sxs-lookup"><span data-stu-id="63bd3-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="63bd3-106">Erstellen Ihrer Assembly.</span><span class="sxs-lookup"><span data-stu-id="63bd3-106">Create your assembly.</span></span> <span data-ttu-id="63bd3-107">Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="63bd3-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="63bd3-108">Weisen Sie Ihrer Assembly einen starken Namen zu.</span><span class="sxs-lookup"><span data-stu-id="63bd3-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="63bd3-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="63bd3-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="63bd3-110">Weisen Sie Ihrer Assembly Versionsinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="63bd3-110">Assign version information to your assembly.</span></span> <span data-ttu-id="63bd3-111">Weitere Informationen dazu finden Sie unter [Assemblyversionen](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="63bd3-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="63bd3-112">Fügen Sie Ihre Assembly in den globalen Assemblycache ein.</span><span class="sxs-lookup"><span data-stu-id="63bd3-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="63bd3-113">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly in den globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="63bd3-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="63bd3-114">Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="63bd3-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="63bd3-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="63bd3-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bd3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63bd3-116">See Also</span></span>  
 <span data-ttu-id="63bd3-117">[Programmierkonzepte für die](../../../../visual-basic/programming-guide/concepts/index.md) [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="63bd3-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>  
 [<span data-ttu-id="63bd3-118">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="63bd3-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
