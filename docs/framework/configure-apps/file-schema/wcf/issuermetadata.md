---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913523"
---
# <a name="issuermetadata"></a><span data-ttu-id="6adac-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="6adac-101">\<issuerMetadata></span></span>
<span data-ttu-id="6adac-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6adac-102">\<system.serviceModel></span></span>  
<span data-ttu-id="6adac-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6adac-103">\<bindings></span></span>  
<span data-ttu-id="6adac-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6adac-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="6adac-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="6adac-105">\<binding></span></span>  
<span data-ttu-id="6adac-106">\<security></span><span class="sxs-lookup"><span data-stu-id="6adac-106">\<security></span></span>  
<span data-ttu-id="6adac-107">\<Message ></span><span class="sxs-lookup"><span data-stu-id="6adac-107">\<message></span></span>  
<span data-ttu-id="6adac-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="6adac-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adac-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6adac-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6adac-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6adac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6adac-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6adac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6adac-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6adac-112">Attributes</span></span>  
  
|<span data-ttu-id="6adac-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6adac-113">Attribute</span></span>|<span data-ttu-id="6adac-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6adac-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6adac-115">Adresse</span><span class="sxs-lookup"><span data-stu-id="6adac-115">address</span></span>|<span data-ttu-id="6adac-116">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="6adac-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="6adac-117">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="6adac-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="6adac-118">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="6adac-118">The address must be an absolute URI.</span></span> <span data-ttu-id="6adac-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6adac-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6adac-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6adac-120">Child Elements</span></span>  
  
|<span data-ttu-id="6adac-121">Element</span><span class="sxs-lookup"><span data-stu-id="6adac-121">Element</span></span>|<span data-ttu-id="6adac-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6adac-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6adac-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="6adac-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="6adac-124">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="6adac-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="6adac-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="6adac-125">\<identity></span></span>](identity.md)|<span data-ttu-id="6adac-126">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="6adac-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6adac-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6adac-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6adac-128">Element</span><span class="sxs-lookup"><span data-stu-id="6adac-128">Element</span></span>|<span data-ttu-id="6adac-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6adac-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6adac-130">\<message></span><span class="sxs-lookup"><span data-stu-id="6adac-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="6adac-131">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das [ \<WSFederationHttpBinding->](wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="6adac-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6adac-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6adac-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="6adac-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6adac-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6adac-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="6adac-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="6adac-135">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="6adac-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="6adac-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="6adac-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
