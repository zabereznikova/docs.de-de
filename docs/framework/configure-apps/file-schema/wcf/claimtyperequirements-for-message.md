---
title: '&lt;claimTypeRequirements&gt; von &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: f4460311f5478f441b819bc8a48540d6feea69b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a><span data-ttu-id="f4ae5-102">&lt;claimTypeRequirements&gt; von &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="f4ae5-102">&lt;claimTypeRequirements&gt; for &lt;message&gt;</span></span>
<span data-ttu-id="f4ae5-103">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="f4ae5-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="f4ae5-104">Die Auflistung wird vom Dienst verwendet, um erforderliche und optionale Ansprüche anzugeben, die sich in dem vom Client für den Dienstzugriff verwendeten ausgestellten Token befinden müssen.</span><span class="sxs-lookup"><span data-stu-id="f4ae5-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="f4ae5-105">Der Dienst macht die erforderlichen Anspruchstypen in Metadaten verfügbar, wenn die WSDL-Veröffentlichung aktiviert wurde, aber WCF erfordert nicht, dass das ausgestellte Token die angegebenen Anspruchstypen enthält.</span><span class="sxs-lookup"><span data-stu-id="f4ae5-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="f4ae5-106">Dienste, die versuchen, erforderliche Anspruchstypen durchzusetzen, sollten mit Autorisierungsrichtlinien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4ae5-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="f4ae5-107">Bei verbundenen Clients enthält diese Auflistung die Liste erforderlicher und optionaler Ansprüche, die an den Sicherheitstokendienst in der Clientanforderung für einen ausgestellten Token gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4ae5-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ae5-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4ae5-108">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
