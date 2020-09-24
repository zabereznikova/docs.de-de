---
title: <issuer> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bfe8163d2d6baba1d6e8053f7f6579673d8b4b21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157277"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="a36b4-102">\<issuer> von \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="a36b4-102">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="a36b4-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="a36b4-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="a36b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a36b4-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a36b4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a36b4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a36b4-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a36b4-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a36b4-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="a36b4-107">Attributes</span></span>  
  
|<span data-ttu-id="a36b4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a36b4-108">Attribute</span></span>|<span data-ttu-id="a36b4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a36b4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a36b4-110">address</span><span class="sxs-lookup"><span data-stu-id="a36b4-110">address</span></span>|<span data-ttu-id="a36b4-111">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a36b4-111">Required string.</span></span> <span data-ttu-id="a36b4-112">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="a36b4-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a36b4-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a36b4-113">Child Elements</span></span>  
  
|<span data-ttu-id="a36b4-114">Element</span><span class="sxs-lookup"><span data-stu-id="a36b4-114">Element</span></span>|<span data-ttu-id="a36b4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a36b4-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="a36b4-116">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="a36b4-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="a36b4-117">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="a36b4-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a36b4-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a36b4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a36b4-119">Element</span><span class="sxs-lookup"><span data-stu-id="a36b4-119">Element</span></span>|<span data-ttu-id="a36b4-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a36b4-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="a36b4-121">Gibt das aktuell ausgegebene Token an.</span><span class="sxs-lookup"><span data-stu-id="a36b4-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a36b4-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a36b4-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a36b4-123">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a36b4-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a36b4-124">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a36b4-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a36b4-125">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a36b4-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a36b4-126">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a36b4-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a36b4-127">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a36b4-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a36b4-128">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="a36b4-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a36b4-129">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a36b4-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="a36b4-130">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a36b4-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a36b4-131">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a36b4-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
