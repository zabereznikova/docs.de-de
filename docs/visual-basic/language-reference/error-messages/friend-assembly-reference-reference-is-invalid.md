---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0966cea26c5dde8f116081c7a6411b4275e50f40
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817044"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="a0847-102">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a0847-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="a0847-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a0847-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="a0847-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="a0847-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="a0847-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, aber er enthält keine `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="a0847-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="a0847-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="a0847-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0847-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a0847-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="a0847-108">Bestimmen Sie den öffentlichen Schlüssel für den starken Namen der Friend-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="a0847-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="a0847-109">Die öffentlichen Schlüssel enthalten, wie Teil des Namens der Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="a0847-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0847-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0847-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="a0847-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="a0847-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
