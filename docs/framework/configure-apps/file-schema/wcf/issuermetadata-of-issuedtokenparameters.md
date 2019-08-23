---
title: <issuerMetadata> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: d9d7d41277eff1de43f717816b35fdc10d52192e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928878"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="10828-102">\<issuerMetadata-> \<von issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="10828-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>
<span data-ttu-id="10828-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="10828-103">\<system.serviceModel></span></span>  
<span data-ttu-id="10828-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="10828-104">\<bindings></span></span>  
<span data-ttu-id="10828-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="10828-105">\<customBinding></span></span>  
<span data-ttu-id="10828-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="10828-106">\<binding></span></span>  
<span data-ttu-id="10828-107">\<security></span><span class="sxs-lookup"><span data-stu-id="10828-107">\<security></span></span>  
<span data-ttu-id="10828-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="10828-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="10828-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="10828-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10828-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="10828-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10828-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="10828-111">Attributes and Elements</span></span>  
 <span data-ttu-id="10828-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10828-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10828-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="10828-113">Attributes</span></span>  
  
|<span data-ttu-id="10828-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="10828-114">Attribute</span></span>|<span data-ttu-id="10828-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10828-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10828-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="10828-116">address</span></span>|<span data-ttu-id="10828-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10828-117">Required.</span></span> <span data-ttu-id="10828-118">Eine Zeichenfolge, die die Adresse des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="10828-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="10828-119">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="10828-119">The address must be an absolute URI.</span></span> <span data-ttu-id="10828-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="10828-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10828-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="10828-121">Child Elements</span></span>  
  
|<span data-ttu-id="10828-122">Element</span><span class="sxs-lookup"><span data-stu-id="10828-122">Element</span></span>|<span data-ttu-id="10828-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10828-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10828-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="10828-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="10828-125">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="10828-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="10828-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="10828-126">\<identity></span></span>](identity.md)|<span data-ttu-id="10828-127">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="10828-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10828-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="10828-128">Parent Elements</span></span>  
  
|<span data-ttu-id="10828-129">Element</span><span class="sxs-lookup"><span data-stu-id="10828-129">Element</span></span>|<span data-ttu-id="10828-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10828-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10828-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="10828-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="10828-132">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="10828-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10828-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10828-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="10828-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10828-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="10828-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="10828-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="10828-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="10828-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="10828-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="10828-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="10828-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="10828-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="10828-139">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="10828-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="10828-140">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="10828-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="10828-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="10828-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="10828-142">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="10828-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="10828-143">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="10828-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
