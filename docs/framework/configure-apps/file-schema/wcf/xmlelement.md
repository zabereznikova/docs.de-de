---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398990"
---
# <a name="xmlelement"></a><span data-ttu-id="16a69-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="16a69-101">\<xmlElement></span></span>
<span data-ttu-id="16a69-102">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="16a69-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="16a69-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="16a69-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="16a69-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="16a69-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding->** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="16a69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="16a69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="16a69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="16a69-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Message >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="16a69-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TokenRequestParameters->** ](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="16a69-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="16a69-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<XmlElement->**</span><span class="sxs-lookup"><span data-stu-id="16a69-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a69-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="16a69-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16a69-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16a69-113">Attributes and Elements</span></span>  
 <span data-ttu-id="16a69-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16a69-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16a69-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="16a69-115">Attributes</span></span>  
  
|<span data-ttu-id="16a69-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="16a69-116">Attribute</span></span>|<span data-ttu-id="16a69-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16a69-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16a69-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="16a69-118">xmlElement</span></span>|<span data-ttu-id="16a69-119">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="16a69-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16a69-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16a69-120">Child Elements</span></span>  
 <span data-ttu-id="16a69-121">Keine</span><span class="sxs-lookup"><span data-stu-id="16a69-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16a69-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16a69-122">Parent Elements</span></span>  
  
|<span data-ttu-id="16a69-123">Element</span><span class="sxs-lookup"><span data-stu-id="16a69-123">Element</span></span>|<span data-ttu-id="16a69-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16a69-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16a69-125">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="16a69-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="16a69-126">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="16a69-126">A collection of token request parameters.</span></span> <span data-ttu-id="16a69-127">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="16a69-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16a69-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16a69-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="16a69-129">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="16a69-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="16a69-130">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="16a69-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="16a69-131">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="16a69-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="16a69-132">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="16a69-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="16a69-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="16a69-133">Bindings</span></span>](../../../wcf/bindings.md)
