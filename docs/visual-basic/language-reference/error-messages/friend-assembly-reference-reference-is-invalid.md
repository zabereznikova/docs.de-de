---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972391"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="4e1f9-102">Friend-assemblyverweisverweis \<> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="4e1f9-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="4e1f9-103">Der Verweis \<> der Friend-Assembly ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="4e1f9-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="4e1f9-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="4e1f9-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="4e1f9-105">Der AssemblyName, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> der an den Attributkonstruktor übergeben wird, identifiziert eine Assembly mit starkem Namen `PublicKey` , aber kein-Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e1f9-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="4e1f9-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="4e1f9-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e1f9-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4e1f9-107">To correct this error</span></span>  
  
1. <span data-ttu-id="4e1f9-108">Bestimmen Sie den öffentlichen Schlüssel für die Friend-Assembly mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="4e1f9-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="4e1f9-109">Fügen Sie den öffentlichen Schlüssel als Teil des Assemblynamens ein <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> , der mit dem `PublicKey` -Attribut an den Attributkonstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="4e1f9-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1f9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e1f9-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="4e1f9-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="4e1f9-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
