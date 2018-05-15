---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 5f6b8d2f861c4d64a3b81407de4ce13b42d9b864
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="ce7b4-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="ce7b4-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="ce7b4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce7b4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ce7b4-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ce7b4-104">\<bindings></span></span>  
<span data-ttu-id="ce7b4-105">\<WsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ce7b4-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="ce7b4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ce7b4-106">\<binding></span></span>  
<span data-ttu-id="ce7b4-107">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="ce7b4-107">\<security></span></span>  
<span data-ttu-id="ce7b4-108">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="ce7b4-108">\<message></span></span>  
<span data-ttu-id="ce7b4-109">\<IssuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="ce7b4-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7b4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce7b4-110">Syntax</span></span>  
  
```xml  
<issuerMetadata address=String" >  
   <headers>  
      <add name="String"  
                 namespace="String" />  
   </headers>  
   <identity>  
           <certificate encodedValue="String"/>  
      <certificateReference findValue="String"   
         isChainIncluded="Boolean"  
         storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
         storeLocation="LocalMachine/CurrentUser"  
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuerMetadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce7b4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce7b4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce7b4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce7b4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce7b4-113">Attributes</span></span>  
  
|<span data-ttu-id="ce7b4-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce7b4-114">Attribute</span></span>|<span data-ttu-id="ce7b4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce7b4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce7b4-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="ce7b4-116">address</span></span>|<span data-ttu-id="ce7b4-117">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="ce7b4-118">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="ce7b4-119">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-119">The address must be an absolute URI.</span></span> <span data-ttu-id="ce7b4-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce7b4-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce7b4-121">Child Elements</span></span>  
  
|<span data-ttu-id="ce7b4-122">Element</span><span class="sxs-lookup"><span data-stu-id="ce7b4-122">Element</span></span>|<span data-ttu-id="ce7b4-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce7b4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce7b4-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="ce7b4-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="ce7b4-125">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="ce7b4-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="ce7b4-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ce7b4-127">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce7b4-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce7b4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ce7b4-129">Element</span><span class="sxs-lookup"><span data-stu-id="ce7b4-129">Element</span></span>|<span data-ttu-id="ce7b4-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce7b4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce7b4-131">\<message></span><span class="sxs-lookup"><span data-stu-id="ce7b4-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="ce7b4-132">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ce7b4-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce7b4-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce7b4-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="ce7b4-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ce7b4-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="ce7b4-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ce7b4-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="ce7b4-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ce7b4-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="ce7b4-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ce7b4-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
