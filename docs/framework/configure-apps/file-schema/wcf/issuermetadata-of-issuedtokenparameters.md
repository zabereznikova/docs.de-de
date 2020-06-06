---
title: <issuerMetadata> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400345"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="f8f9e-102">\<issuerMetadata> von \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="f8f9e-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="f8f9e-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8f9e-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8f9e-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f8f9e-104">Attributes and Elements</span></span>  
 <span data-ttu-id="f8f9e-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8f9e-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="f8f9e-106">Attributes</span></span>  
  
|<span data-ttu-id="f8f9e-107">attribute</span><span class="sxs-lookup"><span data-stu-id="f8f9e-107">Attribute</span></span>|<span data-ttu-id="f8f9e-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8f9e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8f9e-109">address</span><span class="sxs-lookup"><span data-stu-id="f8f9e-109">address</span></span>|<span data-ttu-id="f8f9e-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-110">Required.</span></span> <span data-ttu-id="f8f9e-111">Eine Zeichenfolge, die die Adresse des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="f8f9e-112">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-112">The address must be an absolute URI.</span></span> <span data-ttu-id="f8f9e-113">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8f9e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8f9e-114">Child Elements</span></span>  
  
|<span data-ttu-id="f8f9e-115">Element</span><span class="sxs-lookup"><span data-stu-id="f8f9e-115">Element</span></span>|<span data-ttu-id="f8f9e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8f9e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="f8f9e-117">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="f8f9e-118">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8f9e-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8f9e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f8f9e-120">Element</span><span class="sxs-lookup"><span data-stu-id="f8f9e-120">Element</span></span>|<span data-ttu-id="f8f9e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8f9e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="f8f9e-122">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8f9e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8f9e-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f8f9e-124">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f8f9e-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f8f9e-125">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="f8f9e-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f8f9e-126">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="f8f9e-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f8f9e-127">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="f8f9e-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f8f9e-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f8f9e-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f8f9e-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="f8f9e-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f8f9e-130">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f8f9e-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="f8f9e-131">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f8f9e-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f8f9e-132">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="f8f9e-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
