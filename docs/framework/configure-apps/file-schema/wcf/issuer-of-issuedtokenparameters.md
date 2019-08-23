---
title: <issuer> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 77ed9534ce872e805a6a6ea2c21a38710e6bc0fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925262"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="261e7-102">\<Aussteller > von \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="261e7-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="261e7-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="261e7-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="261e7-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="261e7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="261e7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="261e7-105">\<bindings></span></span>  
<span data-ttu-id="261e7-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="261e7-106">\<customBinding></span></span>  
<span data-ttu-id="261e7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="261e7-107">\<binding></span></span>  
<span data-ttu-id="261e7-108">\<security></span><span class="sxs-lookup"><span data-stu-id="261e7-108">\<security></span></span>  
<span data-ttu-id="261e7-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="261e7-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="261e7-110">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="261e7-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="261e7-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="261e7-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="261e7-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="261e7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="261e7-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="261e7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="261e7-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="261e7-114">Attributes</span></span>  
  
|<span data-ttu-id="261e7-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="261e7-115">Attribute</span></span>|<span data-ttu-id="261e7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="261e7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="261e7-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="261e7-117">address</span></span>|<span data-ttu-id="261e7-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="261e7-118">Required string.</span></span> <span data-ttu-id="261e7-119">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="261e7-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="261e7-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="261e7-120">Child Elements</span></span>  
  
|<span data-ttu-id="261e7-121">Element</span><span class="sxs-lookup"><span data-stu-id="261e7-121">Element</span></span>|<span data-ttu-id="261e7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="261e7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="261e7-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="261e7-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="261e7-124">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="261e7-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="261e7-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="261e7-125">\<identity></span></span>](identity.md)|<span data-ttu-id="261e7-126">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="261e7-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="261e7-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="261e7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="261e7-128">Element</span><span class="sxs-lookup"><span data-stu-id="261e7-128">Element</span></span>|<span data-ttu-id="261e7-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="261e7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="261e7-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="261e7-130">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="261e7-131">Gibt das aktuell ausgegebene Token an.</span><span class="sxs-lookup"><span data-stu-id="261e7-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="261e7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="261e7-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="261e7-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="261e7-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="261e7-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="261e7-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="261e7-135">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="261e7-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="261e7-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="261e7-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="261e7-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="261e7-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="261e7-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="261e7-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="261e7-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="261e7-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="261e7-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="261e7-140">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="261e7-141">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="261e7-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="261e7-142">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="261e7-142">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
