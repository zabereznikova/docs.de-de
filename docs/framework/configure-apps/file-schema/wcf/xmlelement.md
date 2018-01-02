---
title: '&lt;xmlElement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 702b5ea1331aa0ac284d62809367a90e200a8ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="9f3b5-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="9f3b5-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="9f3b5-103">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f3b5-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="9f3b5-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9f3b5-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-105">\<bindings></span></span>  
<span data-ttu-id="9f3b5-106">\<WsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="9f3b5-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-107">\<binding></span></span>  
<span data-ttu-id="9f3b5-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-108">\<security></span></span>  
<span data-ttu-id="9f3b5-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-109">\<message></span></span>  
<span data-ttu-id="9f3b5-110">\<TokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f3b5-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f3b5-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f3b5-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f3b5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9f3b5-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f3b5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f3b5-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f3b5-114">Attributes</span></span>  
  
|<span data-ttu-id="9f3b5-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="9f3b5-115">Attribute</span></span>|<span data-ttu-id="9f3b5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f3b5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f3b5-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="9f3b5-117">xmlElement</span></span>|<span data-ttu-id="9f3b5-118">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f3b5-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f3b5-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f3b5-119">Child Elements</span></span>  
 <span data-ttu-id="9f3b5-120">Keine</span><span class="sxs-lookup"><span data-stu-id="9f3b5-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f3b5-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f3b5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9f3b5-122">Element</span><span class="sxs-lookup"><span data-stu-id="9f3b5-122">Element</span></span>|<span data-ttu-id="9f3b5-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f3b5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f3b5-124">\<TokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="9f3b5-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="9f3b5-125">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="9f3b5-125">A collection of token request parameters.</span></span> <span data-ttu-id="9f3b5-126">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="9f3b5-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f3b5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f3b5-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="9f3b5-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9f3b5-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9f3b5-129">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="9f3b5-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9f3b5-130">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f3b5-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9f3b5-131">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="9f3b5-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9f3b5-132">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f3b5-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
