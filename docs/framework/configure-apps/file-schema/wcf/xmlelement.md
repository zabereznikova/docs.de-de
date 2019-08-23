---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: cc178dcc3684ab338282acc369e0ab5c789c15e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941435"
---
# <a name="xmlelement"></a><span data-ttu-id="b1dd0-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="b1dd0-101">\<xmlElement></span></span>
<span data-ttu-id="b1dd0-102">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="b1dd0-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="b1dd0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b1dd0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1dd0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b1dd0-104">\<bindings></span></span>  
<span data-ttu-id="b1dd0-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="b1dd0-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="b1dd0-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b1dd0-106">\<binding></span></span>  
<span data-ttu-id="b1dd0-107">\<security></span><span class="sxs-lookup"><span data-stu-id="b1dd0-107">\<security></span></span>  
<span data-ttu-id="b1dd0-108">\<Message ></span><span class="sxs-lookup"><span data-stu-id="b1dd0-108">\<message></span></span>  
<span data-ttu-id="b1dd0-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="b1dd0-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1dd0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1dd0-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1dd0-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1dd0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b1dd0-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1dd0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1dd0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1dd0-113">Attributes</span></span>  
  
|<span data-ttu-id="b1dd0-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b1dd0-114">Attribute</span></span>|<span data-ttu-id="b1dd0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1dd0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1dd0-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="b1dd0-116">xmlElement</span></span>|<span data-ttu-id="b1dd0-117">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="b1dd0-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1dd0-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1dd0-118">Child Elements</span></span>  
 <span data-ttu-id="b1dd0-119">Keine</span><span class="sxs-lookup"><span data-stu-id="b1dd0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1dd0-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1dd0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b1dd0-121">Element</span><span class="sxs-lookup"><span data-stu-id="b1dd0-121">Element</span></span>|<span data-ttu-id="b1dd0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1dd0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1dd0-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="b1dd0-123">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="b1dd0-124">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="b1dd0-124">A collection of token request parameters.</span></span> <span data-ttu-id="b1dd0-125">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="b1dd0-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1dd0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1dd0-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="b1dd0-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b1dd0-127">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b1dd0-128">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="b1dd0-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b1dd0-129">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b1dd0-129">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="b1dd0-130">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="b1dd0-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b1dd0-131">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b1dd0-131">Bindings</span></span>](../../../wcf/bindings.md)
