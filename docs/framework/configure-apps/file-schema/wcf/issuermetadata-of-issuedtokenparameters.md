---
title: <issuerMetadata> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400345"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="d401f-102">\<issuerMetadata-> \<von issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="d401f-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="d401f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d401f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d401f-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d401f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d401f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d401f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d401f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d401f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="d401f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="d401f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d401f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d401f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="d401f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters->** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="d401f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="d401f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata->**</span><span class="sxs-lookup"><span data-stu-id="d401f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d401f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="d401f-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d401f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d401f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d401f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d401f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d401f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d401f-114">Attributes</span></span>  
  
|<span data-ttu-id="d401f-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="d401f-115">Attribute</span></span>|<span data-ttu-id="d401f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d401f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d401f-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="d401f-117">address</span></span>|<span data-ttu-id="d401f-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d401f-118">Required.</span></span> <span data-ttu-id="d401f-119">Eine Zeichenfolge, die die Adresse des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="d401f-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="d401f-120">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="d401f-120">The address must be an absolute URI.</span></span> <span data-ttu-id="d401f-121">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d401f-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d401f-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d401f-122">Child Elements</span></span>  
  
|<span data-ttu-id="d401f-123">Element</span><span class="sxs-lookup"><span data-stu-id="d401f-123">Element</span></span>|<span data-ttu-id="d401f-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d401f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d401f-125">\<headers></span><span class="sxs-lookup"><span data-stu-id="d401f-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="d401f-126">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="d401f-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="d401f-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="d401f-127">\<identity></span></span>](identity.md)|<span data-ttu-id="d401f-128">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="d401f-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d401f-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d401f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="d401f-130">Element</span><span class="sxs-lookup"><span data-stu-id="d401f-130">Element</span></span>|<span data-ttu-id="d401f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d401f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d401f-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="d401f-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="d401f-133">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d401f-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d401f-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d401f-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d401f-135">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d401f-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d401f-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="d401f-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d401f-137">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="d401f-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d401f-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="d401f-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d401f-139">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d401f-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d401f-140">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d401f-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d401f-141">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d401f-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d401f-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d401f-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="d401f-143">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d401f-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d401f-144">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="d401f-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
