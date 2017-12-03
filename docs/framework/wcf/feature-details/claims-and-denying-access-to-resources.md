---
title: "Ansprüche und das Verweigern des Zugriffs auf Ressourcen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00d6a797b8099313c15d075457ee757c1f22f744
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="67291-102">Ansprüche und das Verweigern des Zugriffs auf Ressourcen</span><span class="sxs-lookup"><span data-stu-id="67291-102">Claims and Denying Access to Resources</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="67291-103"> unterstützt einen anspruchsbasierten Autorisierungsmechanismus.</span><span class="sxs-lookup"><span data-stu-id="67291-103"> supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="67291-104">Systeme erlauben den Zugriff auf Ressourcen basierend auf dem Vorhandensein von Ansprüchen, verweigern jedoch auch häufig einen solchen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="67291-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="67291-105">Derartige Systeme sollten den <xref:System.IdentityModel.Policy.AuthorizationContext> nach Ansprüchen untersuchen, die dazu führen, dass der Zugriff verweigert wird, bevor sie nach Ansprüchen suchen, die zum Zulassen des Zugriffs führen.</span><span class="sxs-lookup"><span data-stu-id="67291-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="67291-106">Ein System kann beispielsweise einem Benutzer, der einen Anspruch des Typs `Age`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und den Ressourcenwert `Under 21` besitzt, den Zugriff auf eine Ressource nur verweigern, wenn dieser außerdem einen Anspruch des Typs `Name`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.Identity%2A> und den Ressourcenwert `Mallory` besitzt.</span><span class="sxs-lookup"><span data-stu-id="67291-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="67291-107">Anders ausgedrückt, das System verweigert jedem Benutzer den Zugriff, der unter 21 Jahre alt ist, und lässt den Zugriff zu, wenn der Name Mallory lautet.</span><span class="sxs-lookup"><span data-stu-id="67291-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="67291-108">Um diese semantischen Informationen richtig zu implementieren, ist es wichtig, erst nach dem `Age`-Anspruch zu suchen und dann zu bestimmen, ob das Alter unter 21 Jahre liegt.</span><span class="sxs-lookup"><span data-stu-id="67291-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="67291-109">Andernfalls kann, wenn Mallory unter 21 ist, der Zugriff auf die Ressource einzig auf Basis des `Name`-Anspruchs zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="67291-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67291-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67291-110">See Also</span></span>  
 [<span data-ttu-id="67291-111">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="67291-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="67291-112">Ansprüche und Token</span><span class="sxs-lookup"><span data-stu-id="67291-112">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
