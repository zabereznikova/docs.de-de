---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 08fda249b526961ff711f439cf729a18e15b412b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929375"
---
# <a name="issuer"></a><span data-ttu-id="89e3f-101">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="89e3f-101">\<issuer></span></span>
<span data-ttu-id="89e3f-102">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="89e3f-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="89e3f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="89e3f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="89e3f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="89e3f-104">\<bindings></span></span>  
<span data-ttu-id="89e3f-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="89e3f-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="89e3f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="89e3f-106">\<binding></span></span>  
<span data-ttu-id="89e3f-107">\<security></span><span class="sxs-lookup"><span data-stu-id="89e3f-107">\<security></span></span>  
<span data-ttu-id="89e3f-108">\<Message ></span><span class="sxs-lookup"><span data-stu-id="89e3f-108">\<message></span></span>  
<span data-ttu-id="89e3f-109">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="89e3f-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e3f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="89e3f-110">Syntax</span></span>  
  
```xml  
<issuer address="Uri">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89e3f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89e3f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="89e3f-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89e3f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89e3f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="89e3f-113">Attributes</span></span>  
  
|<span data-ttu-id="89e3f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="89e3f-114">Attribute</span></span>|<span data-ttu-id="89e3f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89e3f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89e3f-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="89e3f-116">address</span></span>|<span data-ttu-id="89e3f-117">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="89e3f-117">Required string.</span></span> <span data-ttu-id="89e3f-118">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="89e3f-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89e3f-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89e3f-119">Child Elements</span></span>  
  
|<span data-ttu-id="89e3f-120">Element</span><span class="sxs-lookup"><span data-stu-id="89e3f-120">Element</span></span>|<span data-ttu-id="89e3f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89e3f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89e3f-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="89e3f-122">\<headers></span></span>](headers-element.md)|<span data-ttu-id="89e3f-123">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="89e3f-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="89e3f-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="89e3f-124">\<identity></span></span>](identity.md)|<span data-ttu-id="89e3f-125">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="89e3f-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89e3f-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89e3f-126">Parent Elements</span></span>  
  
|<span data-ttu-id="89e3f-127">Element</span><span class="sxs-lookup"><span data-stu-id="89e3f-127">Element</span></span>|<span data-ttu-id="89e3f-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89e3f-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89e3f-129">\<message></span><span class="sxs-lookup"><span data-stu-id="89e3f-129">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="89e3f-130">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das [ \<WSFederationHttpBinding->](wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="89e3f-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89e3f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89e3f-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="89e3f-132">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89e3f-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="89e3f-133">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="89e3f-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89e3f-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89e3f-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="89e3f-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="89e3f-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89e3f-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="89e3f-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="89e3f-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="89e3f-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
