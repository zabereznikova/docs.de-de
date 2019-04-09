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
# <a name="finding-claims-in-a-claimset"></a>Suchen von Ansprüchen in einem ClaimSet
Bei der Verwendung der anspruchbasierten Autorisierung muss häufig der Inhalt eines <xref:System.IdentityModel.Claims.ClaimSet> für bestimmte Anspruchstypen überprüft werden. Verwenden Sie die <xref:System.IdentityModel.Claims.ClaimSet>-Methode, um <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> auf das Vorhandensein eines bestimmten Anspruchs zu überprüfen. Diese Methode ist leistungsstärker als eine direkte Iteration über <xref:System.IdentityModel.Claims.ClaimSet>. Im folgenden Beispiel wird diese Verwendung veranschaulicht. Beachten Sie, dass die Parameter `claimType` und `claimRight``null` sein können. In diesem Fall entsprechen die Parameter allen Anspruchstypen und Anspruchsrechten.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
