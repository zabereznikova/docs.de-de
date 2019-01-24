---
title: '&lt;issuer&gt;'
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 8313d7e361356e5159d1f2d531a6dd34ae7ff4d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612176"
---
# <a name="ltissuergt"></a><span data-ttu-id="a2869-102">&lt;issuer&gt;</span><span class="sxs-lookup"><span data-stu-id="a2869-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="a2869-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="a2869-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="a2869-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a2869-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a2869-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a2869-105">\<bindings></span></span>  
<span data-ttu-id="a2869-106">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a2869-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="a2869-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2869-107">\<binding></span></span>  
<span data-ttu-id="a2869-108">\<security></span><span class="sxs-lookup"><span data-stu-id="a2869-108">\<security></span></span>  
<span data-ttu-id="a2869-109">\<message></span><span class="sxs-lookup"><span data-stu-id="a2869-109">\<message></span></span>  
<span data-ttu-id="a2869-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="a2869-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2869-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2869-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2869-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2869-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a2869-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2869-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2869-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2869-114">Attributes</span></span>  
  
|<span data-ttu-id="a2869-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a2869-115">Attribute</span></span>|<span data-ttu-id="a2869-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2869-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2869-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="a2869-117">address</span></span>|<span data-ttu-id="a2869-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a2869-118">Required string.</span></span> <span data-ttu-id="a2869-119">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="a2869-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2869-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2869-120">Child Elements</span></span>  
  
|<span data-ttu-id="a2869-121">Element</span><span class="sxs-lookup"><span data-stu-id="a2869-121">Element</span></span>|<span data-ttu-id="a2869-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2869-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2869-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="a2869-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="a2869-124">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="a2869-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="a2869-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="a2869-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a2869-126">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="a2869-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2869-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2869-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a2869-128">Element</span><span class="sxs-lookup"><span data-stu-id="a2869-128">Element</span></span>|<span data-ttu-id="a2869-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2869-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2869-130">\<message></span><span class="sxs-lookup"><span data-stu-id="a2869-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="a2869-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="a2869-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2869-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2869-132">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="a2869-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a2869-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a2869-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a2869-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a2869-135">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a2869-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a2869-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a2869-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a2869-137">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a2869-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a2869-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a2869-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
