---
title: 'Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 8bb36c2aded1144349b86b17a45eef4b48c8aabe
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314788"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="06636-102">Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)</span><span class="sxs-lookup"><span data-stu-id="06636-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="06636-103">Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="06636-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="06636-104">Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.</span><span class="sxs-lookup"><span data-stu-id="06636-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="06636-105">Freigeben einer Assembly</span><span class="sxs-lookup"><span data-stu-id="06636-105">Sharing an assembly</span></span>  
  
1. <span data-ttu-id="06636-106">Erstellen Ihrer Assembly.</span><span class="sxs-lookup"><span data-stu-id="06636-106">Create your assembly.</span></span> <span data-ttu-id="06636-107">Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="06636-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2. <span data-ttu-id="06636-108">Weisen Sie Ihrer Assembly einen starken Namen zu.</span><span class="sxs-lookup"><span data-stu-id="06636-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="06636-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="06636-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3. <span data-ttu-id="06636-110">Weisen Sie Ihrer Assembly Versionsinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="06636-110">Assign version information to your assembly.</span></span> <span data-ttu-id="06636-111">Weitere Informationen dazu finden Sie unter [Assemblyversionen](../../../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="06636-111">For more information, see [Assembly Versioning](../../../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
4. <span data-ttu-id="06636-112">Fügen Sie Ihre Assembly in den globalen Assemblycache ein.</span><span class="sxs-lookup"><span data-stu-id="06636-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="06636-113">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="06636-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5. <span data-ttu-id="06636-114">Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="06636-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="06636-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="06636-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06636-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06636-116">See also</span></span>

- [<span data-ttu-id="06636-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="06636-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="06636-118">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="06636-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
