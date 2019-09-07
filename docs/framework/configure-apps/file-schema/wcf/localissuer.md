---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397866"
---
# <a name="localissuer"></a><span data-ttu-id="6c8ec-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="6c8ec-101">\<localIssuer></span></span>
<span data-ttu-id="6c8ec-102">Gibt die Adresse und Bindung des lokalen Ausstellers zum Abrufen eines Sicherheitstokens an.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
<span data-ttu-id="6c8ec-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6c8ec-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6c8ec-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6c8ec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6c8ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6c8ec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="6c8ec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IssuedToken->** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="6c8ec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="6c8ec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<localIssuer >**</span><span class="sxs-lookup"><span data-stu-id="6c8ec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c8ec-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c8ec-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c8ec-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c8ec-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c8ec-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c8ec-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c8ec-114">Attributes</span></span>  
  
|<span data-ttu-id="6c8ec-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="6c8ec-115">Attribute</span></span>|<span data-ttu-id="6c8ec-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c8ec-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c8ec-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="6c8ec-117">address</span></span>|<span data-ttu-id="6c8ec-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-118">Required string.</span></span> <span data-ttu-id="6c8ec-119">Gibt den URI des lokalen Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="6c8ec-120">Bindung</span><span class="sxs-lookup"><span data-stu-id="6c8ec-120">binding</span></span>|<span data-ttu-id="6c8ec-121">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-121">Optional string.</span></span> <span data-ttu-id="6c8ec-122">Eine der vom System bereitgestellten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-122">One of the system-provided bindings.</span></span> <span data-ttu-id="6c8ec-123">Eine Liste finden Sie unter vom [System bereitgestellte Bindungen](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="6c8ec-123">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="6c8ec-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6c8ec-124">bindingConfiguration</span></span>|<span data-ttu-id="6c8ec-125">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-125">Optional string.</span></span> <span data-ttu-id="6c8ec-126">Gibt eine Bindungskonfiguration aus der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c8ec-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c8ec-127">Child Elements</span></span>  
  
|<span data-ttu-id="6c8ec-128">Element</span><span class="sxs-lookup"><span data-stu-id="6c8ec-128">Element</span></span>|<span data-ttu-id="6c8ec-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c8ec-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c8ec-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="6c8ec-130">\<identity></span></span>](identity.md)|<span data-ttu-id="6c8ec-131">Gibt Identitätsinformationen für den lokalen Aussteller an.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="6c8ec-132">\<headers></span><span class="sxs-lookup"><span data-stu-id="6c8ec-132">\<headers></span></span>](headers-element.md)|<span data-ttu-id="6c8ec-133">Eine Auflistung von Adressheadern, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="6c8ec-134">Sie können das `add`-Schlüsselwort verwenden, um dieser Auflistung einen Header hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c8ec-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c8ec-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6c8ec-136">Element</span><span class="sxs-lookup"><span data-stu-id="6c8ec-136">Element</span></span>|<span data-ttu-id="6c8ec-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c8ec-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c8ec-138">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="6c8ec-138">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="6c8ec-139">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c8ec-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c8ec-140">Remarks</span></span>  
 <span data-ttu-id="6c8ec-141">Beim Abrufen eines von einem Sicherheitstokendienst ( Security Token Service, STS) ausgestellten Tokens muss die Clientanwendung mit der zu verwendenden Adresse und Bindung konfiguriert sein, um mit dem STS kommunizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="6c8ec-142">Wenn das <xref:System.ServiceModel.WSFederationHttpBinding> keine URL für den Sicherheitstokendienst bereitstellt oder wenn die Aussteller Adresse einer Verbund Bindung oder `null`ist `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` , verwendet der Windows Communication Foundation (WCF)-Kanal des Clients die Werte, die von `address`angegebenwerden. und`binding` zur Kommunikation mit dem STS, um das ausgestellte Token abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="6c8ec-143">Weitere Informationen zum Konfigurieren eines lokalen Ausstellers finden [Sie unter Gewusst wie: Konfigurieren Sie einen lokalen](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)Aussteller.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c8ec-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c8ec-144">Example</span></span>  
 <span data-ttu-id="6c8ec-145">Im folgenden Beispiel werden die Attribute `address`, `binding` und `bindingConfiguration` eines `localIssuer`-Elements festgelegt:</span><span class="sxs-lookup"><span data-stu-id="6c8ec-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c8ec-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c8ec-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="6c8ec-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="6c8ec-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6c8ec-148">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="6c8ec-148">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="6c8ec-149">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6c8ec-149">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6c8ec-150">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="6c8ec-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6c8ec-151">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="6c8ec-151">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="6c8ec-152">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="6c8ec-152">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6c8ec-153">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="6c8ec-153">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="6c8ec-154">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="6c8ec-154">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="6c8ec-155">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="6c8ec-155">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
