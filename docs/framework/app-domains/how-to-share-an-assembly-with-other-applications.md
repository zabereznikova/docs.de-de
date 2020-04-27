---
title: 'Vorgehensweise: Verwenden einer Assembly mit anderen Anwendungen'
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b4c183c3fc0b04121be8bbc2db4027887cbc3132
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644291"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="d5bbe-102">Vorgehensweise: Freigeben einer Assembly für andere Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d5bbe-102">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="d5bbe-103">Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="d5bbe-104">Wenn Sie eine Assembly mit anderen Anwendungen verwenden möchten, muss diese in den [globalen Assemblycache](gac.md) eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-104">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="d5bbe-105">So nutzen Sie eine Assembly mit anderen Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="d5bbe-105">To share an assembly:</span></span>
  
1. <span data-ttu-id="d5bbe-106">Erstellen Ihrer Assembly.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-106">Create your assembly.</span></span> <span data-ttu-id="d5bbe-107">Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="d5bbe-107">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="d5bbe-108">Weisen Sie Ihrer Assembly einen starken Namen zu.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="d5bbe-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="d5bbe-109">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="d5bbe-110">Weisen Sie Ihrer Assembly Versionsinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-110">Assign version information to your assembly.</span></span> <span data-ttu-id="d5bbe-111">Weitere Informationen dazu finden Sie unter [Versionsverwaltung für Assemblys](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="d5bbe-111">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="d5bbe-112">Fügen Sie Ihre Assembly in den globalen Assemblycache ein.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-112">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="d5bbe-113">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="d5bbe-113">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="d5bbe-114">Greifen Sie über andere Anwendungen auf die Typen in der Assembly zu.</span><span class="sxs-lookup"><span data-stu-id="d5bbe-114">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="d5bbe-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="d5bbe-115">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bbe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5bbe-116">See also</span></span>

- [<span data-ttu-id="d5bbe-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d5bbe-117">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="d5bbe-118">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5bbe-118">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="d5bbe-119">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="d5bbe-119">Program with assemblies</span></span>](../../standard/assembly/index.md)
