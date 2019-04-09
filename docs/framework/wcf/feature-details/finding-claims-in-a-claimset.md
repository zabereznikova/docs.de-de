---
title: Suchen von Ansprüchen in einem ClaimSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 42e6ee682220913f872da337eb41f6c290082988
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137123"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="ad5ec-102">Suchen von Ansprüchen in einem ClaimSet</span><span class="sxs-lookup"><span data-stu-id="ad5ec-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="ad5ec-103">Bei der Verwendung der anspruchbasierten Autorisierung muss häufig der Inhalt eines <xref:System.IdentityModel.Claims.ClaimSet> für bestimmte Anspruchstypen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="ad5ec-104">Verwenden Sie die <xref:System.IdentityModel.Claims.ClaimSet>-Methode, um <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> auf das Vorhandensein eines bestimmten Anspruchs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="ad5ec-105">Diese Methode ist leistungsstärker als eine direkte Iteration über <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="ad5ec-106">Im folgenden Beispiel wird diese Verwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="ad5ec-107">Beachten Sie, dass die Parameter `claimType` und `claimRight``null` sein können.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="ad5ec-108">In diesem Fall entsprechen die Parameter allen Anspruchstypen und Anspruchsrechten.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad5ec-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad5ec-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ad5ec-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad5ec-110">See also</span></span>

- [<span data-ttu-id="ad5ec-111">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="ad5ec-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
