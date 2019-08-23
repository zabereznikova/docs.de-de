---
title: <claimTypeRequirements>-Element
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: b4d8479dd9a24774afbd0549caf9e261f55fa147
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926142"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="df907-102">\<claimtyperequirequirements-> Element</span><span class="sxs-lookup"><span data-stu-id="df907-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="df907-103">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="df907-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="df907-104">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="df907-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="df907-105">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="df907-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="df907-106">Jedes untergeordnete Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="df907-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="df907-107">Eine Anspruchstypanforderung besteht aus dem URI des im ausgestellten Token angeforderten Anspruchstyps zusammen mit einem booleschen Parameter, der angibt, ob ein Anspruchstyp im ausgestellten Token erforderlich oder optional ist.</span><span class="sxs-lookup"><span data-stu-id="df907-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df907-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df907-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="df907-109">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="df907-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="df907-110">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="df907-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="df907-111">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="df907-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="df907-112">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="df907-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="df907-113">\<add></span><span class="sxs-lookup"><span data-stu-id="df907-113">\<add></span></span>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="df907-114">Bindungen</span><span class="sxs-lookup"><span data-stu-id="df907-114">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="df907-115">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="df907-115">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="df907-116">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="df907-116">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="df907-117">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="df907-117">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="df907-118">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="df907-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="df907-119">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="df907-119">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
