---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397883"
---
# \<issuerMetadata>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="e28ae-101">Syntax</span><span class="sxs-lookup"><span data-stu-id="e28ae-101">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e28ae-102">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e28ae-102">Attributes and Elements</span></span>  
 <span data-ttu-id="e28ae-103">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e28ae-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e28ae-104">Attribute</span><span class="sxs-lookup"><span data-stu-id="e28ae-104">Attributes</span></span>  
  
|<span data-ttu-id="e28ae-105">attribute</span><span class="sxs-lookup"><span data-stu-id="e28ae-105">Attribute</span></span>|<span data-ttu-id="e28ae-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e28ae-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e28ae-107">address</span><span class="sxs-lookup"><span data-stu-id="e28ae-107">address</span></span>|<span data-ttu-id="e28ae-108">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="e28ae-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="e28ae-109">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="e28ae-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="e28ae-110">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="e28ae-110">The address must be an absolute URI.</span></span> <span data-ttu-id="e28ae-111">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e28ae-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e28ae-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e28ae-112">Child Elements</span></span>  
  
|<span data-ttu-id="e28ae-113">Element</span><span class="sxs-lookup"><span data-stu-id="e28ae-113">Element</span></span>|<span data-ttu-id="e28ae-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e28ae-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="e28ae-115">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="e28ae-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="e28ae-116">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="e28ae-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e28ae-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e28ae-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e28ae-118">Element</span><span class="sxs-lookup"><span data-stu-id="e28ae-118">Element</span></span>|<span data-ttu-id="e28ae-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e28ae-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="e28ae-120">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e28ae-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e28ae-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e28ae-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="e28ae-122">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e28ae-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e28ae-123">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e28ae-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e28ae-124">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e28ae-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e28ae-125">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e28ae-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
