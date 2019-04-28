---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 0dffad6a17720dd0506acbcd60efe4aafe24ed28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761675"
---
# <a name="issuermetadata"></a><span data-ttu-id="88f50-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="88f50-101">\<issuerMetadata></span></span>
<span data-ttu-id="88f50-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="88f50-102">\<system.serviceModel></span></span>  
<span data-ttu-id="88f50-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="88f50-103">\<bindings></span></span>  
<span data-ttu-id="88f50-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="88f50-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="88f50-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="88f50-105">\<binding></span></span>  
<span data-ttu-id="88f50-106">\<security></span><span class="sxs-lookup"><span data-stu-id="88f50-106">\<security></span></span>  
<span data-ttu-id="88f50-107">\<message></span><span class="sxs-lookup"><span data-stu-id="88f50-107">\<message></span></span>  
<span data-ttu-id="88f50-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="88f50-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88f50-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="88f50-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88f50-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="88f50-110">Attributes and Elements</span></span>  
 <span data-ttu-id="88f50-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="88f50-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88f50-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="88f50-112">Attributes</span></span>  
  
|<span data-ttu-id="88f50-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="88f50-113">Attribute</span></span>|<span data-ttu-id="88f50-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88f50-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88f50-115">Adresse</span><span class="sxs-lookup"><span data-stu-id="88f50-115">address</span></span>|<span data-ttu-id="88f50-116">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="88f50-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="88f50-117">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="88f50-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="88f50-118">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="88f50-118">The address must be an absolute URI.</span></span> <span data-ttu-id="88f50-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="88f50-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88f50-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="88f50-120">Child Elements</span></span>  
  
|<span data-ttu-id="88f50-121">Element</span><span class="sxs-lookup"><span data-stu-id="88f50-121">Element</span></span>|<span data-ttu-id="88f50-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88f50-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88f50-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="88f50-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="88f50-124">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="88f50-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="88f50-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="88f50-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="88f50-126">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="88f50-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88f50-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="88f50-127">Parent Elements</span></span>  
  
|<span data-ttu-id="88f50-128">Element</span><span class="sxs-lookup"><span data-stu-id="88f50-128">Element</span></span>|<span data-ttu-id="88f50-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88f50-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88f50-130">\<message></span><span class="sxs-lookup"><span data-stu-id="88f50-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="88f50-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="88f50-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88f50-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88f50-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="88f50-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="88f50-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="88f50-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="88f50-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="88f50-135">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="88f50-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="88f50-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="88f50-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
