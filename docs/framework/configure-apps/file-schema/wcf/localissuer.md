---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122875"
---
# <a name="localissuer"></a><span data-ttu-id="ceb34-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="ceb34-101">\<localIssuer></span></span>
<span data-ttu-id="ceb34-102">Gibt die Adresse und Bindung des lokalen Ausstellers zum Abrufen eines Sicherheitstokens an.</span><span class="sxs-lookup"><span data-stu-id="ceb34-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="ceb34-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ceb34-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ceb34-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ceb34-104">\<behaviors></span></span>  
<span data-ttu-id="ceb34-105">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ceb34-105">endpointBehaviors section</span></span>  
<span data-ttu-id="ceb34-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ceb34-106">\<behavior></span></span>  
<span data-ttu-id="ceb34-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ceb34-107">\<clientCredentials></span></span>  
<span data-ttu-id="ceb34-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="ceb34-108">\<issuedToken></span></span>  
<span data-ttu-id="ceb34-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="ceb34-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb34-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ceb34-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ceb34-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ceb34-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ceb34-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ceb34-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ceb34-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ceb34-113">Attributes</span></span>  
  
|<span data-ttu-id="ceb34-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ceb34-114">Attribute</span></span>|<span data-ttu-id="ceb34-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceb34-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ceb34-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="ceb34-116">address</span></span>|<span data-ttu-id="ceb34-117">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ceb34-117">Required string.</span></span> <span data-ttu-id="ceb34-118">Gibt den URI des lokalen Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="ceb34-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="ceb34-119">Bindung</span><span class="sxs-lookup"><span data-stu-id="ceb34-119">binding</span></span>|<span data-ttu-id="ceb34-120">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ceb34-120">Optional string.</span></span> <span data-ttu-id="ceb34-121">Eine der vom System bereitgestellten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="ceb34-121">One of the system-provided bindings.</span></span> <span data-ttu-id="ceb34-122">Eine Liste finden Sie unter [System-provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ceb34-122">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="ceb34-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ceb34-123">bindingConfiguration</span></span>|<span data-ttu-id="ceb34-124">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ceb34-124">Optional string.</span></span> <span data-ttu-id="ceb34-125">Gibt eine Bindungskonfiguration aus der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="ceb34-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ceb34-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ceb34-126">Child Elements</span></span>  
  
|<span data-ttu-id="ceb34-127">Element</span><span class="sxs-lookup"><span data-stu-id="ceb34-127">Element</span></span>|<span data-ttu-id="ceb34-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceb34-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ceb34-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="ceb34-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ceb34-130">Gibt Identitätsinformationen für den lokalen Aussteller an.</span><span class="sxs-lookup"><span data-stu-id="ceb34-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="ceb34-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="ceb34-131">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="ceb34-132">Eine Auflistung von Adressheadern, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="ceb34-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="ceb34-133">Sie können das `add`-Schlüsselwort verwenden, um dieser Auflistung einen Header hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ceb34-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ceb34-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ceb34-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ceb34-135">Element</span><span class="sxs-lookup"><span data-stu-id="ceb34-135">Element</span></span>|<span data-ttu-id="ceb34-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceb34-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ceb34-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="ceb34-137">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="ceb34-138">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ceb34-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceb34-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ceb34-139">Remarks</span></span>  
 <span data-ttu-id="ceb34-140">Beim Abrufen eines von einem Sicherheitstokendienst ( Security Token Service, STS) ausgestellten Tokens muss die Clientanwendung mit der zu verwendenden Adresse und Bindung konfiguriert sein, um mit dem STS kommunizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="ceb34-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="ceb34-141">Wenn die <xref:System.ServiceModel.WSFederationHttpBinding> stellt keine URL für den Sicherheitstokendienst, oder wenn die Ausstelleradresse einer verbundbindung `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` oder `null`, Windows Communication Foundation (WCF)-Clientchannel verwendet die angegebenen Werte von `address`und `binding` für die Kommunikation mit dem STS, um das ausgestellte Token abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ceb34-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="ceb34-142">Weitere Informationen zum Konfigurieren eines lokalen Ausstellers finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="ceb34-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceb34-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ceb34-143">Example</span></span>  
 <span data-ttu-id="ceb34-144">Im folgenden Beispiel werden die Attribute `address`, `binding` und `bindingConfiguration` eines `localIssuer`-Elements festgelegt:</span><span class="sxs-lookup"><span data-stu-id="ceb34-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ceb34-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceb34-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="ceb34-146">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="ceb34-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ceb34-147">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="ceb34-147">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="ceb34-148">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ceb34-148">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ceb34-149">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="ceb34-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ceb34-150">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ceb34-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ceb34-151">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ceb34-151">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ceb34-152">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="ceb34-152">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="ceb34-153">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="ceb34-153">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ceb34-154">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ceb34-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
