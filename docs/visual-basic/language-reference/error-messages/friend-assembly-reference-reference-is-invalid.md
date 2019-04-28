---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0c1526e32ddc64cb4124c6f8205d58deef911dd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802472"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="05e5e-102">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="05e5e-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="05e5e-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="05e5e-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="05e5e-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="05e5e-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="05e5e-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, aber er enthält keine `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="05e5e-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="05e5e-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="05e5e-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05e5e-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="05e5e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="05e5e-108">Bestimmen Sie den öffentlichen Schlüssel für den starken Namen der Friend-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="05e5e-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="05e5e-109">Die öffentlichen Schlüssel enthalten, wie Teil des Namens der Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="05e5e-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e5e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05e5e-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="05e5e-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="05e5e-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
