---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 70ff9b93bcd59331c5fa5e66bb51dc4cd1e043ff
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="cf9d8-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="cf9d8-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="cf9d8-103">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf9d8-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="cf9d8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cf9d8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cf9d8-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cf9d8-105">\<bindings></span></span>  
<span data-ttu-id="cf9d8-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="cf9d8-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="cf9d8-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="cf9d8-107">\<binding></span></span>  
<span data-ttu-id="cf9d8-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="cf9d8-108">\<security></span></span>  
<span data-ttu-id="cf9d8-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="cf9d8-109">\<message></span></span>  
<span data-ttu-id="cf9d8-110">\<TokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="cf9d8-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9d8-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf9d8-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf9d8-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf9d8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cf9d8-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf9d8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf9d8-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf9d8-114">Attributes</span></span>  
  
|<span data-ttu-id="cf9d8-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="cf9d8-115">Attribute</span></span>|<span data-ttu-id="cf9d8-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf9d8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf9d8-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="cf9d8-117">xmlElement</span></span>|<span data-ttu-id="cf9d8-118">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf9d8-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf9d8-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf9d8-119">Child Elements</span></span>  
 <span data-ttu-id="cf9d8-120">Keine</span><span class="sxs-lookup"><span data-stu-id="cf9d8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf9d8-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf9d8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cf9d8-122">Element</span><span class="sxs-lookup"><span data-stu-id="cf9d8-122">Element</span></span>|<span data-ttu-id="cf9d8-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf9d8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf9d8-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="cf9d8-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="cf9d8-125">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="cf9d8-125">A collection of token request parameters.</span></span> <span data-ttu-id="cf9d8-126">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="cf9d8-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf9d8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf9d8-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="cf9d8-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="cf9d8-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="cf9d8-129">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="cf9d8-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="cf9d8-130">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="cf9d8-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="cf9d8-131">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="cf9d8-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="cf9d8-132">Bindungen</span><span class="sxs-lookup"><span data-stu-id="cf9d8-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
