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
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="5f62e-102">Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5f62e-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="5f62e-103">Friend-Assemblyverweis \<Verweis > ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5f62e-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="5f62e-104">Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="5f62e-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="5f62e-105">Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, jedoch nicht mitgespeichert ein `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="5f62e-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="5f62e-106">**Fehler-ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="5f62e-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f62e-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5f62e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="5f62e-108">Bestimmen Sie den öffentlichen Schlüssel für die Assembly mit starkem Namen "Friend".</span><span class="sxs-lookup"><span data-stu-id="5f62e-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="5f62e-109">Den öffentlichen Schlüssel enthalten, als Teil der Assemblyname übergeben der <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.</span><span class="sxs-lookup"><span data-stu-id="5f62e-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f62e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f62e-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="5f62e-111">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="5f62e-111">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [<span data-ttu-id="5f62e-112">Gewusst wie: Erstellen von signierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="5f62e-112">How to: Create Signed Friend Assemblies</span></span>](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
