---
title: '&lt;issuerMetadata&gt; von &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd0417aeebbaf08d28457dd94a4d1698882c79e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="e04b6-102">&lt;issuerMetadata&gt; von &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="e04b6-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="e04b6-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e04b6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e04b6-104">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="e04b6-104">\<bindings></span></span>  
<span data-ttu-id="e04b6-105">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="e04b6-105">\<customBinding></span></span>  
<span data-ttu-id="e04b6-106">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="e04b6-106">\<binding></span></span>  
<span data-ttu-id="e04b6-107">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="e04b6-107">\<security></span></span>  
<span data-ttu-id="e04b6-108">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="e04b6-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="e04b6-109">\<IssuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="e04b6-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04b6-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e04b6-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e04b6-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e04b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e04b6-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e04b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e04b6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e04b6-113">Attributes</span></span>  
  
|<span data-ttu-id="e04b6-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e04b6-114">Attribute</span></span>|<span data-ttu-id="e04b6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e04b6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e04b6-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="e04b6-116">address</span></span>|<span data-ttu-id="e04b6-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e04b6-117">Required.</span></span> <span data-ttu-id="e04b6-118">Eine Zeichenfolge, die die Adresse des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="e04b6-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="e04b6-119">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="e04b6-119">The address must be an absolute URI.</span></span> <span data-ttu-id="e04b6-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e04b6-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e04b6-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e04b6-121">Child Elements</span></span>  
  
|<span data-ttu-id="e04b6-122">Element</span><span class="sxs-lookup"><span data-stu-id="e04b6-122">Element</span></span>|<span data-ttu-id="e04b6-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e04b6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e04b6-124">\<Header ></span><span class="sxs-lookup"><span data-stu-id="e04b6-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="e04b6-125">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="e04b6-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="e04b6-126">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="e04b6-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e04b6-127">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="e04b6-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e04b6-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e04b6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e04b6-129">Element</span><span class="sxs-lookup"><span data-stu-id="e04b6-129">Element</span></span>|<span data-ttu-id="e04b6-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e04b6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e04b6-131">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="e04b6-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="e04b6-132">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e04b6-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e04b6-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e04b6-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e04b6-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e04b6-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e04b6-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e04b6-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="e04b6-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e04b6-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="e04b6-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e04b6-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="e04b6-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e04b6-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e04b6-139">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="e04b6-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e04b6-140">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e04b6-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e04b6-141">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="e04b6-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="e04b6-142">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e04b6-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="e04b6-143">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e04b6-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
