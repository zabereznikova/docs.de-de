---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397883"
---
# <a name="issuermetadata"></a><span data-ttu-id="fd350-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="fd350-101">\<issuerMetadata></span></span>

<span data-ttu-id="fd350-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd350-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd350-103">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fd350-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fd350-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fd350-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fd350-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding->** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fd350-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="fd350-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="fd350-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fd350-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fd350-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="fd350-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Message >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fd350-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="fd350-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata->**</span><span class="sxs-lookup"><span data-stu-id="fd350-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd350-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd350-110">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
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
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd350-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fd350-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fd350-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd350-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd350-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fd350-113">Attributes</span></span>  
  
|<span data-ttu-id="fd350-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="fd350-114">Attribute</span></span>|<span data-ttu-id="fd350-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd350-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd350-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="fd350-116">address</span></span>|<span data-ttu-id="fd350-117">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="fd350-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="fd350-118">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="fd350-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="fd350-119">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="fd350-119">The address must be an absolute URI.</span></span> <span data-ttu-id="fd350-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fd350-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd350-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd350-121">Child Elements</span></span>  
  
|<span data-ttu-id="fd350-122">Element</span><span class="sxs-lookup"><span data-stu-id="fd350-122">Element</span></span>|<span data-ttu-id="fd350-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd350-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd350-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="fd350-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="fd350-125">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="fd350-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="fd350-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="fd350-126">\<identity></span></span>](identity.md)|<span data-ttu-id="fd350-127">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="fd350-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd350-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd350-128">Parent Elements</span></span>  
  
|<span data-ttu-id="fd350-129">Element</span><span class="sxs-lookup"><span data-stu-id="fd350-129">Element</span></span>|<span data-ttu-id="fd350-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd350-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd350-131">\<message></span><span class="sxs-lookup"><span data-stu-id="fd350-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="fd350-132">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das [ \<WSFederationHttpBinding->](wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="fd350-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd350-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd350-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="fd350-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fd350-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fd350-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="fd350-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fd350-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd350-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="fd350-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="fd350-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
