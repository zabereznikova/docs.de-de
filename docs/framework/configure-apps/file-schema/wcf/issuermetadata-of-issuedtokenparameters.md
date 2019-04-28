---
title: <issuerMetadata> von <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: e46e56c6285af24941a550b2c4f7dec3b441db69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764100"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="ac24f-102">\<issuerMetadata> of \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="ac24f-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>
<span data-ttu-id="ac24f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ac24f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ac24f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ac24f-104">\<bindings></span></span>  
<span data-ttu-id="ac24f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ac24f-105">\<customBinding></span></span>  
<span data-ttu-id="ac24f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ac24f-106">\<binding></span></span>  
<span data-ttu-id="ac24f-107">\<security></span><span class="sxs-lookup"><span data-stu-id="ac24f-107">\<security></span></span>  
<span data-ttu-id="ac24f-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="ac24f-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="ac24f-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="ac24f-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac24f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac24f-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac24f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ac24f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ac24f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac24f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac24f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac24f-113">Attributes</span></span>  
  
|<span data-ttu-id="ac24f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ac24f-114">Attribute</span></span>|<span data-ttu-id="ac24f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac24f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac24f-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="ac24f-116">address</span></span>|<span data-ttu-id="ac24f-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac24f-117">Required.</span></span> <span data-ttu-id="ac24f-118">Eine Zeichenfolge, die die Adresse des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="ac24f-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="ac24f-119">Die Adresse muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="ac24f-119">The address must be an absolute URI.</span></span> <span data-ttu-id="ac24f-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ac24f-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac24f-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac24f-121">Child Elements</span></span>  
  
|<span data-ttu-id="ac24f-122">Element</span><span class="sxs-lookup"><span data-stu-id="ac24f-122">Element</span></span>|<span data-ttu-id="ac24f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac24f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac24f-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="ac24f-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="ac24f-125">Eine Auflistung von Adressheadern.</span><span class="sxs-lookup"><span data-stu-id="ac24f-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="ac24f-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="ac24f-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ac24f-127">Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="ac24f-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac24f-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac24f-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ac24f-129">Element</span><span class="sxs-lookup"><span data-stu-id="ac24f-129">Element</span></span>|<span data-ttu-id="ac24f-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac24f-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac24f-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="ac24f-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="ac24f-132">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ac24f-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac24f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac24f-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ac24f-134">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ac24f-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ac24f-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ac24f-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ac24f-136">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ac24f-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ac24f-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ac24f-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ac24f-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ac24f-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ac24f-139">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ac24f-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ac24f-140">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ac24f-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ac24f-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ac24f-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="ac24f-142">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ac24f-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="ac24f-143">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ac24f-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
