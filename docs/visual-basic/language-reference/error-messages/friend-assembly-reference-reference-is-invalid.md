---
title: Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: c47fae9c60dc04ee02b1ff015d3dde87b8920c02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587370"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="5790c-102">Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5790c-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="5790c-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5790c-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="5790c-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="5790c-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="5790c-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, jedoch nicht mitgespeichert ein `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="5790c-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="5790c-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="5790c-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5790c-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5790c-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="5790c-108">Bestimmen Sie den öffentlichen Schlüssel für die Assembly mit starkem Namen "Friend".</span><span class="sxs-lookup"><span data-stu-id="5790c-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="5790c-109">Den öffentlichen Schlüssel enthalten, als Teil der Assemblyname übergeben der <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="5790c-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5790c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5790c-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="5790c-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="5790c-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

