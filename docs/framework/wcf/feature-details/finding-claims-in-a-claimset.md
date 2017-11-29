---
title: "Suchen von Ansprüchen in einem ClaimSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cc6a4d98529357aa58f55be2fc33d6b7a95a8999
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="8207c-102">Suchen von Ansprüchen in einem ClaimSet</span><span class="sxs-lookup"><span data-stu-id="8207c-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="8207c-103">Bei der Verwendung der anspruchbasierten Autorisierung muss häufig der Inhalt eines <xref:System.IdentityModel.Claims.ClaimSet> für bestimmte Anspruchstypen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="8207c-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="8207c-104">Verwenden Sie die <xref:System.IdentityModel.Claims.ClaimSet>-Methode, um <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> auf das Vorhandensein eines bestimmten Anspruchs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8207c-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="8207c-105">Diese Methode ist leistungsstärker als eine direkte Iteration über <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="8207c-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="8207c-106">Im folgenden Beispiel wird diese Verwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8207c-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="8207c-107">Beachten Sie, dass die Parameter `claimType` und `claimRight` `null` sein können.</span><span class="sxs-lookup"><span data-stu-id="8207c-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="8207c-108">In diesem Fall entsprechen die Parameter allen Anspruchstypen und Anspruchsrechten.</span><span class="sxs-lookup"><span data-stu-id="8207c-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8207c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8207c-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8207c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8207c-110">See Also</span></span>  
 [<span data-ttu-id="8207c-111">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="8207c-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
