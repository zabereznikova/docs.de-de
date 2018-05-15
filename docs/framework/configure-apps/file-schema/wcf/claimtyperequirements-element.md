---
title: '&lt;claimTypeRequirements&gt;-Element'
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 3a8bacf4dad2140e3d162cca89c6bd3ecf54b41f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequirementsgt-element"></a><span data-ttu-id="e6730-102">&lt;claimTypeRequirements&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="e6730-102">&lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="e6730-103">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="e6730-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="e6730-104">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="e6730-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="e6730-105">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e6730-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="e6730-106">Jedes untergeordnete Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="e6730-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="e6730-107">Eine Anspruchstypanforderung besteht aus dem URI des im ausgestellten Token angeforderten Anspruchstyps zusammen mit einem booleschen Parameter, der angibt, ob ein Anspruchstyp im ausgestellten Token erforderlich oder optional ist.</span><span class="sxs-lookup"><span data-stu-id="e6730-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6730-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6730-108">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e6730-109">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e6730-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e6730-110">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e6730-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="e6730-111">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e6730-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="e6730-112">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e6730-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="e6730-113">\<add></span><span class="sxs-lookup"><span data-stu-id="e6730-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)  
 [<span data-ttu-id="e6730-114">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e6730-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e6730-115">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="e6730-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e6730-116">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e6730-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e6730-117">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e6730-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="e6730-118">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e6730-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="e6730-119">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e6730-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
