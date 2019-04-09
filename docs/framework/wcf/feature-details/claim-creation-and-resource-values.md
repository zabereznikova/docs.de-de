---
title: Erstellen von Ansprüchen und Ressourcenwerte
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: bd9a8b7faf3cd7a648ff6b2a50ac68f21561497c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093695"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="82e44-102">Erstellen von Ansprüchen und Ressourcenwerte</span><span class="sxs-lookup"><span data-stu-id="82e44-102">Claim Creation and Resource Values</span></span>
<span data-ttu-id="82e44-103">Die <xref:System.IdentityModel.Claims.Claim>-Klasse bietet mehrere Methoden zum Erstellen von Instanzen von integrierten Anspruchstypen.</span><span class="sxs-lookup"><span data-stu-id="82e44-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="82e44-104">Von diesen Methoden führen die folgenden keine semantische Prüfung oder Formatüberprüfung für die angegebene Ressource aus:</span><span class="sxs-lookup"><span data-stu-id="82e44-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> <span data-ttu-id="82e44-105">(die Länge oder den Inhalt des Bytearrays nicht überprüft)</span><span class="sxs-lookup"><span data-stu-id="82e44-105">(does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> <span data-ttu-id="82e44-106">(die Länge oder den Inhalt des Bytearrays nicht überprüft)</span><span class="sxs-lookup"><span data-stu-id="82e44-106">(does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="82e44-107">Gehen Sie beim Aufrufen der oben beschriebenen Methoden äußerst sorgfältig vor, um sicherzustellen, dass die übergebenen Ressourcenwerte das richtige Format aufweisen oder die richtigen Informationen enthalten (oder beides).</span><span class="sxs-lookup"><span data-stu-id="82e44-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="82e44-108">Die folgenden Methoden werden mit bestimmten Typen verwendet:</span><span class="sxs-lookup"><span data-stu-id="82e44-108">The following methods take specific types:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="82e44-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82e44-109">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="82e44-110">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="82e44-110">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
