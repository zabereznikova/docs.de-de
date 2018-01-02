---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c7e5c28325326d838da851ff4add12f8ae612c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="a4dc8-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="a4dc8-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="a4dc8-103">Gibt die Adresse und Bindung des lokalen Ausstellers zum Abrufen eines Sicherheitstokens an.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="a4dc8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4dc8-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-105">\<behaviors></span></span>  
<span data-ttu-id="a4dc8-106">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a4dc8-106">endpointBehaviors section</span></span>  
<span data-ttu-id="a4dc8-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-107">\<behavior></span></span>  
<span data-ttu-id="a4dc8-108">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-108">\<clientCredentials></span></span>  
<span data-ttu-id="a4dc8-109">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-109">\<issuedToken></span></span>  
<span data-ttu-id="a4dc8-110">\<LocalIssuer ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4dc8-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4dc8-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4dc8-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4dc8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a4dc8-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4dc8-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4dc8-114">Attributes</span></span>  
  
|<span data-ttu-id="a4dc8-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a4dc8-115">Attribute</span></span>|<span data-ttu-id="a4dc8-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4dc8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4dc8-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="a4dc8-117">address</span></span>|<span data-ttu-id="a4dc8-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-118">Required string.</span></span> <span data-ttu-id="a4dc8-119">Gibt den URI des lokalen Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="a4dc8-120">Bindung</span><span class="sxs-lookup"><span data-stu-id="a4dc8-120">binding</span></span>|<span data-ttu-id="a4dc8-121">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-121">Optional string.</span></span> <span data-ttu-id="a4dc8-122">Eine der vom System bereitgestellten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-122">One of the system-provided bindings.</span></span> <span data-ttu-id="a4dc8-123">Eine Liste finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a4dc8-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="a4dc8-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a4dc8-124">bindingConfiguration</span></span>|<span data-ttu-id="a4dc8-125">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-125">Optional string.</span></span> <span data-ttu-id="a4dc8-126">Gibt eine Bindungskonfiguration aus der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4dc8-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4dc8-127">Child Elements</span></span>  
  
|<span data-ttu-id="a4dc8-128">Element</span><span class="sxs-lookup"><span data-stu-id="a4dc8-128">Element</span></span>|<span data-ttu-id="a4dc8-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4dc8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4dc8-130">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a4dc8-131">Gibt Identitätsinformationen für den lokalen Aussteller an.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="a4dc8-132">\<Header ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="a4dc8-133">Eine Auflistung von Adressheadern, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="a4dc8-134">Sie können das `add`-Schlüsselwort verwenden, um dieser Auflistung einen Header hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4dc8-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4dc8-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a4dc8-136">Element</span><span class="sxs-lookup"><span data-stu-id="a4dc8-136">Element</span></span>|<span data-ttu-id="a4dc8-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4dc8-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4dc8-138">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="a4dc8-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="a4dc8-139">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4dc8-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4dc8-140">Remarks</span></span>  
 <span data-ttu-id="a4dc8-141">Beim Abrufen eines von einem Sicherheitstokendienst (Security Token Service, STS) ausgestellten Tokens muss die Clientanwendung mit der zu verwendenden Adresse und Bindung konfiguriert sein, um mit dem STS kommunizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="a4dc8-142">Wenn die <xref:System.ServiceModel.WSFederationHttpBinding> keinen URL für den Sicherheitstokendienst bereitstellt oder wenn die Ausstelleradresse einer Verbundbindung http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous oder `null` lautet, verwendet der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Kanal des Clients die durch `address` und `binding` angegebenen Werte zur Kommunikation mit dem STS, um den ausgestellten Token abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a4dc8-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="a4dc8-143">Weitere Informationen zum Konfigurieren eines lokalen Ausstellers finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="a4dc8-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4dc8-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4dc8-144">Example</span></span>  
 <span data-ttu-id="a4dc8-145">Im folgenden Beispiel werden die Attribute `address`, `binding` und `bindingConfiguration` eines `localIssuer`-Elements festgelegt:</span><span class="sxs-lookup"><span data-stu-id="a4dc8-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4dc8-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4dc8-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="a4dc8-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="a4dc8-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a4dc8-148">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="a4dc8-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="a4dc8-149">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4dc8-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a4dc8-150">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="a4dc8-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a4dc8-151">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a4dc8-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a4dc8-152">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a4dc8-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a4dc8-153">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="a4dc8-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="a4dc8-154">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="a4dc8-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="a4dc8-155">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a4dc8-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
