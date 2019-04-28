---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756259"
---
# <a name="issuer"></a><span data-ttu-id="2a8d1-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2a8d1-101">\<issuer></span></span>
<span data-ttu-id="2a8d1-102">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="2a8d1-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2a8d1-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2a8d1-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2a8d1-104">\<bindings></span></span>  
<span data-ttu-id="2a8d1-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2a8d1-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="2a8d1-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2a8d1-106">\<binding></span></span>  
<span data-ttu-id="2a8d1-107">\<security></span><span class="sxs-lookup"><span data-stu-id="2a8d1-107">\<security></span></span>  
<span data-ttu-id="2a8d1-108">\<message></span><span class="sxs-lookup"><span data-stu-id="2a8d1-108">\<message></span></span>  
<span data-ttu-id="2a8d1-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2a8d1-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a8d1-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a8d1-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a8d1-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2a8d1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2a8d1-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a8d1-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2a8d1-113">Attributes</span></span>  
  
|<span data-ttu-id="2a8d1-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="2a8d1-114">Attribute</span></span>|<span data-ttu-id="2a8d1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a8d1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a8d1-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="2a8d1-116">address</span></span>|<span data-ttu-id="2a8d1-117">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-117">Required string.</span></span> <span data-ttu-id="2a8d1-118">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a8d1-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a8d1-119">Child Elements</span></span>  
  
|<span data-ttu-id="2a8d1-120">Element</span><span class="sxs-lookup"><span data-stu-id="2a8d1-120">Element</span></span>|<span data-ttu-id="2a8d1-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a8d1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a8d1-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="2a8d1-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="2a8d1-123">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="2a8d1-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="2a8d1-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="2a8d1-125">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a8d1-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a8d1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2a8d1-127">Element</span><span class="sxs-lookup"><span data-stu-id="2a8d1-127">Element</span></span>|<span data-ttu-id="2a8d1-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a8d1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a8d1-129">\<message></span><span class="sxs-lookup"><span data-stu-id="2a8d1-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="2a8d1-130">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="2a8d1-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a8d1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a8d1-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="2a8d1-132">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2a8d1-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2a8d1-133">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2a8d1-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2a8d1-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2a8d1-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2a8d1-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2a8d1-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2a8d1-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2a8d1-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2a8d1-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2a8d1-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
