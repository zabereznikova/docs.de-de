---
title: <issuer> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397944"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="bd659-102">\<Aussteller > von \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="bd659-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="bd659-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="bd659-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="bd659-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd659-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd659-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bd659-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bd659-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="bd659-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="bd659-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bd659-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="bd659-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="bd659-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="bd659-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bd659-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="bd659-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters->** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="bd659-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="bd659-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aussteller >**</span><span class="sxs-lookup"><span data-stu-id="bd659-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd659-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd659-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd659-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bd659-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bd659-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bd659-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd659-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="bd659-115">Attributes</span></span>  
  
|<span data-ttu-id="bd659-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="bd659-116">Attribute</span></span>|<span data-ttu-id="bd659-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd659-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd659-118">Adresse</span><span class="sxs-lookup"><span data-stu-id="bd659-118">address</span></span>|<span data-ttu-id="bd659-119">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bd659-119">Required string.</span></span> <span data-ttu-id="bd659-120">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="bd659-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd659-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd659-121">Child Elements</span></span>  
  
|<span data-ttu-id="bd659-122">Element</span><span class="sxs-lookup"><span data-stu-id="bd659-122">Element</span></span>|<span data-ttu-id="bd659-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd659-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd659-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="bd659-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="bd659-125">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="bd659-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="bd659-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="bd659-126">\<identity></span></span>](identity.md)|<span data-ttu-id="bd659-127">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="bd659-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd659-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd659-128">Parent Elements</span></span>  
  
|<span data-ttu-id="bd659-129">Element</span><span class="sxs-lookup"><span data-stu-id="bd659-129">Element</span></span>|<span data-ttu-id="bd659-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd659-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd659-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="bd659-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="bd659-132">Gibt das aktuell ausgegebene Token an.</span><span class="sxs-lookup"><span data-stu-id="bd659-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd659-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd659-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bd659-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bd659-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="bd659-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="bd659-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="bd659-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd659-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="bd659-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="bd659-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="bd659-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd659-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bd659-139">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd659-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bd659-140">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd659-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bd659-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bd659-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="bd659-142">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="bd659-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="bd659-143">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd659-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
