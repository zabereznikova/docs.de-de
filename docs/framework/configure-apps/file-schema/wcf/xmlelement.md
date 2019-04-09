---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230498"
---
# <a name="xmlelement"></a><span data-ttu-id="14bc8-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="14bc8-101">\<xmlElement></span></span>
<span data-ttu-id="14bc8-102">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="14bc8-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="14bc8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="14bc8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="14bc8-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="14bc8-104">\<bindings></span></span>  
<span data-ttu-id="14bc8-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="14bc8-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="14bc8-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="14bc8-106">\<binding></span></span>  
<span data-ttu-id="14bc8-107">\<security></span><span class="sxs-lookup"><span data-stu-id="14bc8-107">\<security></span></span>  
<span data-ttu-id="14bc8-108">\<message></span><span class="sxs-lookup"><span data-stu-id="14bc8-108">\<message></span></span>  
<span data-ttu-id="14bc8-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="14bc8-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14bc8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="14bc8-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14bc8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14bc8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="14bc8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14bc8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14bc8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="14bc8-113">Attributes</span></span>  
  
|<span data-ttu-id="14bc8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="14bc8-114">Attribute</span></span>|<span data-ttu-id="14bc8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14bc8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14bc8-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="14bc8-116">xmlElement</span></span>|<span data-ttu-id="14bc8-117">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="14bc8-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14bc8-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14bc8-118">Child Elements</span></span>  
 <span data-ttu-id="14bc8-119">Keine</span><span class="sxs-lookup"><span data-stu-id="14bc8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14bc8-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14bc8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="14bc8-121">Element</span><span class="sxs-lookup"><span data-stu-id="14bc8-121">Element</span></span>|<span data-ttu-id="14bc8-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14bc8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14bc8-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="14bc8-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="14bc8-124">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="14bc8-124">A collection of token request parameters.</span></span> <span data-ttu-id="14bc8-125">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="14bc8-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14bc8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14bc8-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="14bc8-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="14bc8-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="14bc8-128">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="14bc8-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="14bc8-129">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="14bc8-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="14bc8-130">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="14bc8-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="14bc8-131">Bindungen</span><span class="sxs-lookup"><span data-stu-id="14bc8-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
