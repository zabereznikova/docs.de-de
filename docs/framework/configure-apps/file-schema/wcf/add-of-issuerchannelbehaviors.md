---
title: '&lt;add&gt; von &lt;issuerChannelBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf66b3d3b531ae41329aade6a416c330957d83c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="16d39-102">&lt;add&gt; von &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="16d39-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="16d39-103">Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.</span><span class="sxs-lookup"><span data-stu-id="16d39-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16d39-104">Wenn alle Endpunktverhalten enthält eine [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="16d39-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="16d39-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="16d39-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="16d39-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="16d39-106">\<behaviors></span></span>  
<span data-ttu-id="16d39-107">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="16d39-107">endpointBehaviors section</span></span>  
<span data-ttu-id="16d39-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="16d39-108">\<behavior></span></span>  
<span data-ttu-id="16d39-109">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="16d39-109">\<clientCredentials></span></span>  
<span data-ttu-id="16d39-110">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="16d39-110">\<issuedToken></span></span>  
<span data-ttu-id="16d39-111">\<IssuerChannelBehaviors >-Element</span><span class="sxs-lookup"><span data-stu-id="16d39-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="16d39-112">\<add></span><span class="sxs-lookup"><span data-stu-id="16d39-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d39-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="16d39-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16d39-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16d39-114">Attributes and Elements</span></span>  
 <span data-ttu-id="16d39-115">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16d39-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16d39-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="16d39-116">Attributes</span></span>  
  
|<span data-ttu-id="16d39-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="16d39-117">Attribute</span></span>|<span data-ttu-id="16d39-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16d39-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16d39-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="16d39-119">issuerAddress</span></span>|<span data-ttu-id="16d39-120">Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.</span><span class="sxs-lookup"><span data-stu-id="16d39-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="16d39-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="16d39-121">behaviorConfiguration</span></span>|<span data-ttu-id="16d39-122">Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.</span><span class="sxs-lookup"><span data-stu-id="16d39-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16d39-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16d39-123">Child Elements</span></span>  
 <span data-ttu-id="16d39-124">Keine</span><span class="sxs-lookup"><span data-stu-id="16d39-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16d39-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16d39-125">Parent Elements</span></span>  
  
|<span data-ttu-id="16d39-126">Element</span><span class="sxs-lookup"><span data-stu-id="16d39-126">Element</span></span>|<span data-ttu-id="16d39-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16d39-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16d39-128">\<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="16d39-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="16d39-129">Enthält eine Auflistung der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Client-Endpunktverhalten, die für die Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="16d39-129">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16d39-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16d39-130">Remarks</span></span>  
 <span data-ttu-id="16d39-131">`issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte.</span><span class="sxs-lookup"><span data-stu-id="16d39-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="16d39-132">`behaviorConfiguration` verweist auf ein Endpunktverhalten, das von der Anwendung in den von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] erstellten Kanälen verwendet wird, um die ausgestellten Token aus den Sicherheitstokendiensten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="16d39-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d39-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16d39-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="16d39-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="16d39-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="16d39-135">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="16d39-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="16d39-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="16d39-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="16d39-137">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="16d39-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="16d39-138">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="16d39-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="16d39-139">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="16d39-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="16d39-140">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="16d39-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="16d39-141">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="16d39-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="16d39-142">\<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="16d39-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
