---
title: '&lt;xmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 40703bdf62e8c69ac7e09a0d715e2a2f99408680
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612280"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="0c4a4-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="0c4a4-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="0c4a4-103">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="0c4a4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c4a4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c4a4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0c4a4-105">\<bindings></span></span>  
<span data-ttu-id="0c4a4-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="0c4a4-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="0c4a4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0c4a4-107">\<binding></span></span>  
<span data-ttu-id="0c4a4-108">\<security></span><span class="sxs-lookup"><span data-stu-id="0c4a4-108">\<security></span></span>  
<span data-ttu-id="0c4a4-109">\<message></span><span class="sxs-lookup"><span data-stu-id="0c4a4-109">\<message></span></span>  
<span data-ttu-id="0c4a4-110">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="0c4a4-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4a4-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c4a4-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c4a4-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0c4a4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0c4a4-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c4a4-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="0c4a4-114">Attributes</span></span>  
  
|<span data-ttu-id="0c4a4-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="0c4a4-115">Attribute</span></span>|<span data-ttu-id="0c4a4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c4a4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c4a4-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="0c4a4-117">xmlElement</span></span>|<span data-ttu-id="0c4a4-118">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c4a4-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c4a4-119">Child Elements</span></span>  
 <span data-ttu-id="0c4a4-120">Keine</span><span class="sxs-lookup"><span data-stu-id="0c4a4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c4a4-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c4a4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0c4a4-122">Element</span><span class="sxs-lookup"><span data-stu-id="0c4a4-122">Element</span></span>|<span data-ttu-id="0c4a4-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c4a4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c4a4-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="0c4a4-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="0c4a4-125">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-125">A collection of token request parameters.</span></span> <span data-ttu-id="0c4a4-126">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c4a4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c4a4-127">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="0c4a4-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c4a4-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0c4a4-129">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="0c4a4-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0c4a4-130">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0c4a4-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="0c4a4-131">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="0c4a4-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0c4a4-132">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0c4a4-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
