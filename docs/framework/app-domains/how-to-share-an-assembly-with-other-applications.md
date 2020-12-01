---
title: 'Vorgehensweise: Freigeben einer Assembly für andere Anwendungen'
description: Hier erfahren Sie, wie Sie eine Assembly für andere Anwendungen in .NET freigeben. Assemblys können privat (Standardeinstellung) oder freigegeben sein. Fügen Sie eine Assembly in den globalen Assemblycache ein, um sie freizugeben.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 1056f8b555713d5d67488537e6c06cc457c4d312
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242538"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="ccbde-105">Vorgehensweise: Freigeben einer Assembly für andere Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ccbde-105">How to: Share an assembly with other applications</span></span>

<span data-ttu-id="ccbde-106">Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="ccbde-106">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="ccbde-107">Wenn Sie eine Assembly mit anderen Anwendungen verwenden möchten, muss diese in den [globalen Assemblycache](gac.md) eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ccbde-107">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="ccbde-108">So nutzen Sie eine Assembly mit anderen Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="ccbde-108">To share an assembly:</span></span>
  
1. <span data-ttu-id="ccbde-109">Erstellen Ihrer Assembly.</span><span class="sxs-lookup"><span data-stu-id="ccbde-109">Create your assembly.</span></span> <span data-ttu-id="ccbde-110">Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="ccbde-110">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="ccbde-111">Weisen Sie Ihrer Assembly einen starken Namen zu.</span><span class="sxs-lookup"><span data-stu-id="ccbde-111">Assign a strong name to your assembly.</span></span> <span data-ttu-id="ccbde-112">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="ccbde-112">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="ccbde-113">Weisen Sie Ihrer Assembly Versionsinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="ccbde-113">Assign version information to your assembly.</span></span> <span data-ttu-id="ccbde-114">Weitere Informationen dazu finden Sie unter [Versionsverwaltung für Assemblys](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="ccbde-114">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="ccbde-115">Fügen Sie Ihre Assembly in den globalen Assemblycache ein.</span><span class="sxs-lookup"><span data-stu-id="ccbde-115">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="ccbde-116">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="ccbde-116">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="ccbde-117">Greifen Sie über andere Anwendungen auf die Typen in der Assembly zu.</span><span class="sxs-lookup"><span data-stu-id="ccbde-117">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="ccbde-118">Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="ccbde-118">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbde-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccbde-119">See also</span></span>

- [<span data-ttu-id="ccbde-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ccbde-120">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="ccbde-121">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccbde-121">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="ccbde-122">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="ccbde-122">Program with assemblies</span></span>](../../standard/assembly/index.md)
