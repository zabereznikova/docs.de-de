---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160710"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="32a97-102">BC31535: friend-Assemblyverweis \<reference> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="32a97-102">BC31535: Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="32a97-103">Der friend-Assemblyverweis \<reference> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="32a97-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="32a97-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="32a97-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>

 <span data-ttu-id="32a97-105">Der AssemblyName, der an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor übergeben wird, identifiziert eine Assembly mit starkem Namen, aber kein- `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="32a97-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>

 <span data-ttu-id="32a97-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="32a97-106">**Error ID:** BC31535</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="32a97-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="32a97-107">To correct this error</span></span>

1. <span data-ttu-id="32a97-108">Bestimmen Sie den öffentlichen Schlüssel für die Friend-Assembly mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="32a97-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="32a97-109">Fügen Sie den öffentlichen Schlüssel als Teil des Assemblynamens ein, der mit dem-Attribut an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor übergeben wird `PublicKey` .</span><span class="sxs-lookup"><span data-stu-id="32a97-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="32a97-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32a97-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="32a97-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="32a97-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
