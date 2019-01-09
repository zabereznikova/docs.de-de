---
title: '&lt;"issuermetadata"&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 38fa373212464a7dc919c2f364524a391db17d43
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149357"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="839c7-102">&lt;"issuermetadata"&gt;</span><span class="sxs-lookup"><span data-stu-id="839c7-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="839c7-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="839c7-103">\<system.serviceModel></span></span>  
<span data-ttu-id="839c7-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="839c7-104">\<bindings></span></span>  
<span data-ttu-id="839c7-105">\<WsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="839c7-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="839c7-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="839c7-106">\<binding></span></span>  
<span data-ttu-id="839c7-107">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="839c7-107">\<security></span></span>  
<span data-ttu-id="839c7-108">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="839c7-108">\<message></span></span>  
<span data-ttu-id="839c7-109">\<"issuermetadata" ></span><span class="sxs-lookup"><span data-stu-id="839c7-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="839c7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="839c7-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="839c7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="839c7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="839c7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="839c7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="839c7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="839c7-113">Attributes</span></span>  
  
|<span data-ttu-id="839c7-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="839c7-114">Attribute</span></span>|<span data-ttu-id="839c7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="839c7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="839c7-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="839c7-116">address</span></span>|<span data-ttu-id="839c7-117">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="839c7-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="839c7-118">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="839c7-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="839c7-119">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="839c7-119">The address must be an absolute URI.</span></span> <span data-ttu-id="839c7-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="839c7-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="839c7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="839c7-121">Child Elements</span></span>  
  
|<span data-ttu-id="839c7-122">Element</span><span class="sxs-lookup"><span data-stu-id="839c7-122">Element</span></span>|<span data-ttu-id="839c7-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="839c7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="839c7-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="839c7-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="839c7-125">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="839c7-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="839c7-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="839c7-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="839c7-127">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="839c7-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="839c7-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="839c7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="839c7-129">Element</span><span class="sxs-lookup"><span data-stu-id="839c7-129">Element</span></span>|<span data-ttu-id="839c7-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="839c7-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="839c7-131">\<message></span><span class="sxs-lookup"><span data-stu-id="839c7-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="839c7-132">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="839c7-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="839c7-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="839c7-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="839c7-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="839c7-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="839c7-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="839c7-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="839c7-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="839c7-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="839c7-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="839c7-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
