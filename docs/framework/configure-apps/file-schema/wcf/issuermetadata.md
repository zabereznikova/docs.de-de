---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 10a6d2aaad7d63d00b3a57032d0d218f756454d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175953"
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
  
## <a name="syntax"></a><span data-ttu-id="47e22-101">Syntax</span><span class="sxs-lookup"><span data-stu-id="47e22-101">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47e22-102">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="47e22-102">Attributes and Elements</span></span>  

 <span data-ttu-id="47e22-103">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="47e22-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47e22-104">Attribute</span><span class="sxs-lookup"><span data-stu-id="47e22-104">Attributes</span></span>  
  
|<span data-ttu-id="47e22-105">attribute</span><span class="sxs-lookup"><span data-stu-id="47e22-105">Attribute</span></span>|<span data-ttu-id="47e22-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="47e22-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47e22-107">address</span><span class="sxs-lookup"><span data-stu-id="47e22-107">address</span></span>|<span data-ttu-id="47e22-108">Erforderliches `string`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="47e22-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="47e22-109">Gibt die Adresse des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="47e22-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="47e22-110">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="47e22-110">The address must be an absolute URI.</span></span> <span data-ttu-id="47e22-111">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="47e22-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47e22-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47e22-112">Child Elements</span></span>  
  
|<span data-ttu-id="47e22-113">Element</span><span class="sxs-lookup"><span data-stu-id="47e22-113">Element</span></span>|<span data-ttu-id="47e22-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47e22-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="47e22-115">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="47e22-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="47e22-116">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="47e22-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47e22-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47e22-117">Parent Elements</span></span>  
  
|<span data-ttu-id="47e22-118">Element</span><span class="sxs-lookup"><span data-stu-id="47e22-118">Element</span></span>|<span data-ttu-id="47e22-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47e22-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="47e22-120">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="47e22-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47e22-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47e22-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="47e22-122">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="47e22-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="47e22-123">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="47e22-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="47e22-124">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="47e22-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="47e22-125">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="47e22-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
