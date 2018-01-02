---
title: '&lt;issuer&gt; von &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b31214f5552283c40cdc93e6e72a374bbfef9997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="dee20-102">&lt;issuer&gt; von &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="dee20-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="dee20-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="dee20-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="dee20-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dee20-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dee20-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="dee20-105">\<bindings></span></span>  
<span data-ttu-id="dee20-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="dee20-106">\<customBinding></span></span>  
<span data-ttu-id="dee20-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="dee20-107">\<binding></span></span>  
<span data-ttu-id="dee20-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="dee20-108">\<security></span></span>  
<span data-ttu-id="dee20-109">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="dee20-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="dee20-110">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="dee20-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee20-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="dee20-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dee20-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dee20-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dee20-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dee20-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dee20-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="dee20-114">Attributes</span></span>  
  
|<span data-ttu-id="dee20-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="dee20-115">Attribute</span></span>|<span data-ttu-id="dee20-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dee20-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dee20-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="dee20-117">address</span></span>|<span data-ttu-id="dee20-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dee20-118">Required string.</span></span> <span data-ttu-id="dee20-119">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="dee20-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dee20-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dee20-120">Child Elements</span></span>  
  
|<span data-ttu-id="dee20-121">Element</span><span class="sxs-lookup"><span data-stu-id="dee20-121">Element</span></span>|<span data-ttu-id="dee20-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dee20-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dee20-123">\<Header ></span><span class="sxs-lookup"><span data-stu-id="dee20-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="dee20-124">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="dee20-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="dee20-125">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="dee20-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="dee20-126">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="dee20-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dee20-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dee20-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dee20-128">Element</span><span class="sxs-lookup"><span data-stu-id="dee20-128">Element</span></span>|<span data-ttu-id="dee20-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dee20-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dee20-130">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="dee20-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="dee20-131">Gibt das aktuell ausgegebene Token an.</span><span class="sxs-lookup"><span data-stu-id="dee20-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dee20-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dee20-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="dee20-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="dee20-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="dee20-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="dee20-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="dee20-135">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="dee20-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="dee20-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="dee20-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="dee20-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="dee20-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="dee20-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="dee20-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="dee20-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="dee20-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="dee20-140">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="dee20-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="dee20-141">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dee20-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="dee20-142">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="dee20-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
