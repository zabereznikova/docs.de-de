---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: e08d2c0b42cfd8e302223915f0256f8cb2d1468b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204956"
---
# \<localIssuer>

<span data-ttu-id="5eb12-101">Gibt die Adresse und Bindung des lokalen Ausstellers zum Abrufen eines Sicherheitstokens an.</span><span class="sxs-lookup"><span data-stu-id="5eb12-101">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="5eb12-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="5eb12-102">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5eb12-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5eb12-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5eb12-104">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5eb12-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5eb12-105">Attributes</span><span class="sxs-lookup"><span data-stu-id="5eb12-105">Attributes</span></span>  
  
|<span data-ttu-id="5eb12-106">attribute</span><span class="sxs-lookup"><span data-stu-id="5eb12-106">Attribute</span></span>|<span data-ttu-id="5eb12-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5eb12-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5eb12-108">address</span><span class="sxs-lookup"><span data-stu-id="5eb12-108">address</span></span>|<span data-ttu-id="5eb12-109">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5eb12-109">Required string.</span></span> <span data-ttu-id="5eb12-110">Gibt den URI des lokalen Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="5eb12-110">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="5eb12-111">binding</span><span class="sxs-lookup"><span data-stu-id="5eb12-111">binding</span></span>|<span data-ttu-id="5eb12-112">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5eb12-112">Optional string.</span></span> <span data-ttu-id="5eb12-113">Eine der vom System bereitgestellten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="5eb12-113">One of the system-provided bindings.</span></span> <span data-ttu-id="5eb12-114">Eine Liste finden Sie unter vom [System bereitgestellte Bindungen](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="5eb12-114">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="5eb12-115">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5eb12-115">bindingConfiguration</span></span>|<span data-ttu-id="5eb12-116">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5eb12-116">Optional string.</span></span> <span data-ttu-id="5eb12-117">Gibt eine Bindungskonfiguration aus der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="5eb12-117">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5eb12-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5eb12-118">Child Elements</span></span>  
  
|<span data-ttu-id="5eb12-119">Element</span><span class="sxs-lookup"><span data-stu-id="5eb12-119">Element</span></span>|<span data-ttu-id="5eb12-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5eb12-120">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="5eb12-121">Gibt Identitätsinformationen für den lokalen Aussteller an.</span><span class="sxs-lookup"><span data-stu-id="5eb12-121">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="5eb12-122">Eine Auflistung von Adressheadern, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="5eb12-122">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="5eb12-123">Sie können das `add`-Schlüsselwort verwenden, um dieser Auflistung einen Header hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5eb12-123">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5eb12-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5eb12-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5eb12-125">Element</span><span class="sxs-lookup"><span data-stu-id="5eb12-125">Element</span></span>|<span data-ttu-id="5eb12-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5eb12-126">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="5eb12-127">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5eb12-127">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eb12-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5eb12-128">Remarks</span></span>  

 <span data-ttu-id="5eb12-129">Beim Abrufen eines von einem Sicherheitstokendienst ( Security Token Service, STS) ausgestellten Tokens muss die Clientanwendung mit der zu verwendenden Adresse und Bindung konfiguriert sein, um mit dem STS kommunizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="5eb12-129">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="5eb12-130">Wenn das <xref:System.ServiceModel.WSFederationHttpBinding> keine URL für den Sicherheitstokendienst bereitstellt oder wenn die Aussteller Adresse einer Verbund Bindung `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` oder ist `null` , verwendet der Windows Communication Foundation (WCF)-Kanal des Clients die Werte, die von und angegeben werden, `address` `binding` um mit dem STS zu kommunizieren, um das ausgestellte Token abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5eb12-130">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="5eb12-131">Weitere Informationen zum Konfigurieren eines lokalen Ausstellers finden Sie unter Vorgehens [Weise: Konfigurieren eines lokalen](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)Ausstellers.</span><span class="sxs-lookup"><span data-stu-id="5eb12-131">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eb12-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5eb12-132">Example</span></span>  

 <span data-ttu-id="5eb12-133">Im folgenden Beispiel werden die Attribute `address`, `binding` und `bindingConfiguration` eines `localIssuer`-Elements festgelegt:</span><span class="sxs-lookup"><span data-stu-id="5eb12-133">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5eb12-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5eb12-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="5eb12-135">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="5eb12-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5eb12-136">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="5eb12-136">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="5eb12-137">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5eb12-137">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5eb12-138">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="5eb12-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5eb12-139">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="5eb12-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5eb12-140">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5eb12-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5eb12-141">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="5eb12-141">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5eb12-142">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="5eb12-142">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="5eb12-143">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="5eb12-143">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
