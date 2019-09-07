---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397916"
---
# <a name="issuer"></a><span data-ttu-id="2c043-101">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="2c043-101">\<issuer></span></span>
<span data-ttu-id="2c043-102">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="2c043-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="2c043-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2c043-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2c043-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2c043-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2c043-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2c043-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2c043-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding->** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c043-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2c043-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="2c043-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2c043-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c043-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2c043-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Message >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2c043-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2c043-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aussteller >**</span><span class="sxs-lookup"><span data-stu-id="2c043-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c043-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c043-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c043-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2c043-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2c043-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c043-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c043-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="2c043-114">Attributes</span></span>  
  
|<span data-ttu-id="2c043-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="2c043-115">Attribute</span></span>|<span data-ttu-id="2c043-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c043-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c043-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="2c043-117">address</span></span>|<span data-ttu-id="2c043-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2c043-118">Required string.</span></span> <span data-ttu-id="2c043-119">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="2c043-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c043-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c043-120">Child Elements</span></span>  
  
|<span data-ttu-id="2c043-121">Element</span><span class="sxs-lookup"><span data-stu-id="2c043-121">Element</span></span>|<span data-ttu-id="2c043-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c043-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c043-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="2c043-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="2c043-124">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2c043-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="2c043-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="2c043-125">\<identity></span></span>](identity.md)|<span data-ttu-id="2c043-126">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="2c043-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c043-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c043-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2c043-128">Element</span><span class="sxs-lookup"><span data-stu-id="2c043-128">Element</span></span>|<span data-ttu-id="2c043-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c043-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c043-130">\<message></span><span class="sxs-lookup"><span data-stu-id="2c043-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="2c043-131">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das [ \<WSFederationHttpBinding->](wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="2c043-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c043-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c043-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="2c043-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2c043-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2c043-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2c043-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2c043-135">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2c043-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2c043-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2c043-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2c043-137">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2c043-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2c043-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2c043-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
