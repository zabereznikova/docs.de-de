---
title: Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611929"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="67e55-102">Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="67e55-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="67e55-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="67e55-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="67e55-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="67e55-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="67e55-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, aber er enthält keine `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="67e55-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="67e55-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="67e55-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="67e55-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="67e55-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="67e55-108">Bestimmen Sie den öffentlichen Schlüssel für den starken Namen der Friend-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="67e55-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="67e55-109">Die öffentlichen Schlüssel enthalten, wie Teil des Namens der Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="67e55-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e55-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67e55-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="67e55-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="67e55-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


