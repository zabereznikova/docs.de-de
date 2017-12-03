---
title: '&lt;issuedToken&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b77dd374a508c10d4070a271e7bfba9eefe67c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuedtokengt"></a><span data-ttu-id="befb4-102">&lt;issuedToken&gt;</span><span class="sxs-lookup"><span data-stu-id="befb4-102">&lt;issuedToken&gt;</span></span>
<span data-ttu-id="befb4-103">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="befb4-103">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="befb4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="befb4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="befb4-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="befb4-105">\<behaviors></span></span>  
<span data-ttu-id="befb4-106">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="befb4-106">endpointBehaviors section</span></span>  
<span data-ttu-id="befb4-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="befb4-107">\<behavior></span></span>  
<span data-ttu-id="befb4-108">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="befb4-108">\<clientCredentials></span></span>  
<span data-ttu-id="befb4-109">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="befb4-109">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="befb4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="befb4-110">Syntax</span></span>  
  
```xml  
<issuedToken   
   cacheIssuedTokens="Boolean"  
   defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"  
   issuedTokenRenewalThresholdPercentage = "0 to 100"  
   issuerChannelBehaviors="String"  
      localIssuerChannelBehaviors="String"  
   maxIssuedTokenCachingTime="TimeSpan"  
</issuedToken>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="befb4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="befb4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="befb4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="befb4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="befb4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="befb4-113">Attributes</span></span>  
  
|<span data-ttu-id="befb4-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="befb4-114">Attribute</span></span>|<span data-ttu-id="befb4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="befb4-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="befb4-116">Optionales boolesches Attribut, das angibt, ob Token zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="befb4-116">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="befb4-117">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="befb4-117">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="befb4-118">Optionales Zeichenfolgenattribut, das angibt, welche Zufallsvariablen (Entropien) für Handshakevorgänge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="befb4-118">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="befb4-119">Zu den Werten zählen `ClientEntropy`, `ServerEntropy` und `CombinedEntropy`. Die Standardeinstellung lautet `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="befb4-119">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="befb4-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="befb4-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="befb4-121">Optionales Ganzzahlattribut, das den Prozentwert eines gültigen Zeitrahmens (geliefert vom Tokenaussteller) angibt, der verstreichen kann, bevor ein Token erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="befb4-121">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="befb4-122">Die Werte reichen von 0 bis 100.</span><span class="sxs-lookup"><span data-stu-id="befb4-122">Values are from 0 to 100.</span></span> <span data-ttu-id="befb4-123">Die Standardeinstellung ist 60, was 60 % der Zeiten ohne Aktivität entspricht, bevor ein erneuter Versuch durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="befb4-123">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="befb4-124">Optionales Attribut, das das für die Kommunikation mit dem Aussteller zu verwendende Kanalverhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="befb4-124">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="befb4-125">Optionales Attribut, das das für die Kommunikation mit dem lokalen Aussteller zu verwendende Kanalverhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="befb4-125">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="befb4-126">Optionales Timespan-Attribut, das die Dauer angibt, die ausgestellte Token zwischengespeichert werden, wenn der Tokenaussteller (ein STS) keine Zeit angibt.</span><span class="sxs-lookup"><span data-stu-id="befb4-126">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="befb4-127">Die Standardeinstellung ist "10675199.02:48:05.4775807."</span><span class="sxs-lookup"><span data-stu-id="befb4-127">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="befb4-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="befb4-128">Child Elements</span></span>  
  
|<span data-ttu-id="befb4-129">Element</span><span class="sxs-lookup"><span data-stu-id="befb4-129">Element</span></span>|<span data-ttu-id="befb4-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="befb4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="befb4-131">\<LocalIssuer ></span><span class="sxs-lookup"><span data-stu-id="befb4-131">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="befb4-132">Gibt die Adresse des lokalen Tokenausstellers sowie die Bindung an, die für die Kommunikation mit dem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="befb4-132">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="befb4-133">\<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="befb4-133">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="befb4-134">Gibt das Endpunktverhalten an, das beim Kontaktieren eines lokalen Ausstellers verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="befb4-134">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="befb4-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="befb4-135">Parent Elements</span></span>  
  
|<span data-ttu-id="befb4-136">Element</span><span class="sxs-lookup"><span data-stu-id="befb4-136">Element</span></span>|<span data-ttu-id="befb4-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="befb4-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="befb4-138">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="befb4-138">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="befb4-139">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="befb4-139">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="befb4-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="befb4-140">Remarks</span></span>  
 <span data-ttu-id="befb4-141">Ein ausgestelltes Token ist ein benutzerdefinierter Anmeldeinformationstyp, zum Beispiel für die Authentifizierung mit einem Secure Token Service (STS) in einem Verbundszenario.</span><span class="sxs-lookup"><span data-stu-id="befb4-141">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="befb4-142">Standardmäßig ist das Token ein SAML-Token.</span><span class="sxs-lookup"><span data-stu-id="befb4-142">By default, the token is a SAML token.</span></span> <span data-ttu-id="befb4-143">Weitere Informationen finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="befb4-143">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="befb4-144">und [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="befb4-144">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="befb4-145">Dieser Abschnitt enthält die Elemente, die zum Konfigurieren eines lokalen Tokenausstellers verwendet werden, bzw. die mit einem Sicherheitstokendienst verwendeten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="befb4-145">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="befb4-146">Anweisungen zum Konfigurieren eines Clients für einen lokalen Aussteller verwenden, finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="befb4-146">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befb4-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="befb4-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="befb4-148">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="befb4-148">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="befb4-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="befb4-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="befb4-150">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="befb4-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="befb4-151">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="befb4-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="befb4-152">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="befb4-152">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="befb4-153">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="befb4-153">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="befb4-154">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="befb4-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
