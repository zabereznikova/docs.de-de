---
title: 'Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 3d29a3558a64c02fc8c59035f2fee5c64c4a776f
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089411"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="ebba2-102">Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebba2-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="ebba2-103">Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="ebba2-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="ebba2-104">Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.</span><span class="sxs-lookup"><span data-stu-id="ebba2-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="ebba2-105">Freigeben einer Assembly</span><span class="sxs-lookup"><span data-stu-id="ebba2-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="ebba2-106">Erstellen Ihrer Assembly.</span><span class="sxs-lookup"><span data-stu-id="ebba2-106">Create your assembly.</span></span> <span data-ttu-id="ebba2-107">Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ebba2-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="ebba2-108">Weisen Sie Ihrer Assembly einen starken Namen zu.</span><span class="sxs-lookup"><span data-stu-id="ebba2-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="ebba2-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="ebba2-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="ebba2-110">Weisen Sie Ihrer Assembly Versionsinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="ebba2-110">Assign version information to your assembly.</span></span> <span data-ttu-id="ebba2-111">Weitere Informationen dazu finden Sie unter [Assemblyversionen](../../../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="ebba2-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="ebba2-112">Fügen Sie Ihre Assembly in den globalen Assemblycache ein.</span><span class="sxs-lookup"><span data-stu-id="ebba2-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="ebba2-113">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly in den globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="ebba2-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="ebba2-114">Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ebba2-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="ebba2-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="ebba2-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebba2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebba2-116">See also</span></span>

- [<span data-ttu-id="ebba2-117">Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="ebba2-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="ebba2-118">Assemblys und der globale Assemblycache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebba2-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="ebba2-119">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="ebba2-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
