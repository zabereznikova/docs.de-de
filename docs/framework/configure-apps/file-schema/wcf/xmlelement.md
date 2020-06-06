---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398990"
---
# \<xmlElement>
<span data-ttu-id="46340-101">Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="46340-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="46340-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="46340-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46340-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="46340-103">Attributes and Elements</span></span>  
 <span data-ttu-id="46340-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46340-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46340-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="46340-105">Attributes</span></span>  
  
|<span data-ttu-id="46340-106">attribute</span><span class="sxs-lookup"><span data-stu-id="46340-106">Attribute</span></span>|<span data-ttu-id="46340-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="46340-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46340-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="46340-108">xmlElement</span></span>|<span data-ttu-id="46340-109">Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="46340-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46340-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46340-110">Child Elements</span></span>  
 <span data-ttu-id="46340-111">Keine</span><span class="sxs-lookup"><span data-stu-id="46340-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46340-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46340-112">Parent Elements</span></span>  
  
|<span data-ttu-id="46340-113">Element</span><span class="sxs-lookup"><span data-stu-id="46340-113">Element</span></span>|<span data-ttu-id="46340-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46340-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="46340-115">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="46340-115">A collection of token request parameters.</span></span> <span data-ttu-id="46340-116">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="46340-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46340-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46340-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="46340-118">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="46340-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="46340-119">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="46340-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="46340-120">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="46340-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="46340-121">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="46340-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="46340-122">Bindungen</span><span class="sxs-lookup"><span data-stu-id="46340-122">Bindings</span></span>](../../../wcf/bindings.md)
