---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230498"
---
# <a name="xmlelement"></a><span data-ttu-id="e5128-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="e5128-101">\<xmlElement></span></span>
<span data-ttu-id="e5128-102">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5128-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="e5128-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5128-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5128-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e5128-104">\<bindings></span></span>  
<span data-ttu-id="e5128-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="e5128-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="e5128-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e5128-106">\<binding></span></span>  
<span data-ttu-id="e5128-107">\<security></span><span class="sxs-lookup"><span data-stu-id="e5128-107">\<security></span></span>  
<span data-ttu-id="e5128-108">\<message></span><span class="sxs-lookup"><span data-stu-id="e5128-108">\<message></span></span>  
<span data-ttu-id="e5128-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="e5128-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5128-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5128-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5128-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e5128-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5128-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5128-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5128-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e5128-113">Attributes</span></span>  
  
|<span data-ttu-id="e5128-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e5128-114">Attribute</span></span>|<span data-ttu-id="e5128-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5128-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5128-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="e5128-116">xmlElement</span></span>|<span data-ttu-id="e5128-117">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5128-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5128-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5128-118">Child Elements</span></span>  
 <span data-ttu-id="e5128-119">Keine</span><span class="sxs-lookup"><span data-stu-id="e5128-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5128-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5128-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e5128-121">Element</span><span class="sxs-lookup"><span data-stu-id="e5128-121">Element</span></span>|<span data-ttu-id="e5128-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5128-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5128-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="e5128-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="e5128-124">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="e5128-124">A collection of token request parameters.</span></span> <span data-ttu-id="e5128-125">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="e5128-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5128-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5128-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="e5128-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e5128-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e5128-128">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e5128-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e5128-129">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e5128-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e5128-130">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="e5128-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e5128-131">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e5128-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
