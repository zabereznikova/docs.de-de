---
title: "Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab1c7c5cc7a7f4ad899df7722769238e05d96e6b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="73636-102">Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="73636-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="73636-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="73636-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="73636-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="73636-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="73636-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, jedoch nicht mitgespeichert ein `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="73636-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="73636-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="73636-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73636-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="73636-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="73636-108">Bestimmen Sie den öffentlichen Schlüssel für die Assembly mit starkem Namen "Friend".</span><span class="sxs-lookup"><span data-stu-id="73636-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="73636-109">Den öffentlichen Schlüssel enthalten, als Teil der Assemblyname übergeben der <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="73636-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73636-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73636-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="73636-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="73636-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

