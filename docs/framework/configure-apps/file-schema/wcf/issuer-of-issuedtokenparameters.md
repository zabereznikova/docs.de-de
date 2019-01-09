---
title: '&lt;issuer&gt; von &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: aa647f448bad74e25ffce4a5622c7489274996c7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151136"
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="5be29-102">&lt;issuer&gt; von &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="5be29-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="5be29-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="5be29-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="5be29-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5be29-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5be29-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5be29-105">\<bindings></span></span>  
<span data-ttu-id="5be29-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5be29-106">\<customBinding></span></span>  
<span data-ttu-id="5be29-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5be29-107">\<binding></span></span>  
<span data-ttu-id="5be29-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="5be29-108">\<security></span></span>  
<span data-ttu-id="5be29-109">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="5be29-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="5be29-110">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="5be29-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be29-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="5be29-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be29-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5be29-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5be29-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5be29-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be29-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="5be29-114">Attributes</span></span>  
  
|<span data-ttu-id="5be29-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="5be29-115">Attribute</span></span>|<span data-ttu-id="5be29-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5be29-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5be29-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="5be29-117">address</span></span>|<span data-ttu-id="5be29-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5be29-118">Required string.</span></span> <span data-ttu-id="5be29-119">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="5be29-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be29-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5be29-120">Child Elements</span></span>  
  
|<span data-ttu-id="5be29-121">Element</span><span class="sxs-lookup"><span data-stu-id="5be29-121">Element</span></span>|<span data-ttu-id="5be29-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5be29-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be29-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="5be29-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="5be29-124">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="5be29-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="5be29-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="5be29-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="5be29-126">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="5be29-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5be29-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5be29-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5be29-128">Element</span><span class="sxs-lookup"><span data-stu-id="5be29-128">Element</span></span>|<span data-ttu-id="5be29-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5be29-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be29-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="5be29-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="5be29-131">Gibt das aktuell ausgegebene Token an.</span><span class="sxs-lookup"><span data-stu-id="5be29-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5be29-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5be29-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="5be29-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5be29-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="5be29-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="5be29-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="5be29-135">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5be29-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="5be29-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="5be29-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="5be29-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5be29-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5be29-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="5be29-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="5be29-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="5be29-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="5be29-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5be29-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="5be29-141">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5be29-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="5be29-142">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5be29-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
