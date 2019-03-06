---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 796c16e912283d86496a4ccbd3b675ac1433f02d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356402"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="1306e-102">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="1306e-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="1306e-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="1306e-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="1306e-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="1306e-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="1306e-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, aber er enthält keine `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="1306e-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="1306e-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="1306e-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1306e-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1306e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="1306e-108">Bestimmen Sie den öffentlichen Schlüssel für den starken Namen der Friend-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="1306e-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="1306e-109">Die öffentlichen Schlüssel enthalten, wie Teil des Namens der Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="1306e-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1306e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1306e-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="1306e-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="1306e-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)


