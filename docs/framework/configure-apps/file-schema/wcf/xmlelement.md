---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 648147a7e3977648ac3c26c9dfc469629f3b70c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278290"
---
# <a name="xmlelement"></a><span data-ttu-id="c7bbe-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="c7bbe-101">\<xmlElement></span></span>
<span data-ttu-id="c7bbe-102">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="c7bbe-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c7bbe-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c7bbe-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c7bbe-104">\<bindings></span></span>  
<span data-ttu-id="c7bbe-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="c7bbe-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c7bbe-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c7bbe-106">\<binding></span></span>  
<span data-ttu-id="c7bbe-107">\<security></span><span class="sxs-lookup"><span data-stu-id="c7bbe-107">\<security></span></span>  
<span data-ttu-id="c7bbe-108">\<message></span><span class="sxs-lookup"><span data-stu-id="c7bbe-108">\<message></span></span>  
<span data-ttu-id="c7bbe-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c7bbe-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7bbe-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7bbe-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7bbe-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c7bbe-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c7bbe-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7bbe-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c7bbe-113">Attributes</span></span>  
  
|<span data-ttu-id="c7bbe-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c7bbe-114">Attribute</span></span>|<span data-ttu-id="c7bbe-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7bbe-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7bbe-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="c7bbe-116">xmlElement</span></span>|<span data-ttu-id="c7bbe-117">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7bbe-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7bbe-118">Child Elements</span></span>  
 <span data-ttu-id="c7bbe-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c7bbe-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7bbe-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7bbe-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c7bbe-121">Element</span><span class="sxs-lookup"><span data-stu-id="c7bbe-121">Element</span></span>|<span data-ttu-id="c7bbe-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7bbe-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7bbe-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c7bbe-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="c7bbe-124">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-124">A collection of token request parameters.</span></span> <span data-ttu-id="c7bbe-125">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7bbe-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7bbe-126">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="c7bbe-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7bbe-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c7bbe-128">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="c7bbe-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c7bbe-129">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c7bbe-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c7bbe-130">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="c7bbe-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c7bbe-131">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c7bbe-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
