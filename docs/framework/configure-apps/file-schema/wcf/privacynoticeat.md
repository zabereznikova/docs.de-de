---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 5e772e23b21c566c906be854e33b924698dcf3e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158707"
---
# \<privacyNoticeAt>

<span data-ttu-id="d4531-101">Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.</span><span class="sxs-lookup"><span data-stu-id="d4531-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="d4531-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4531-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="d4531-103">Typ</span><span class="sxs-lookup"><span data-stu-id="d4531-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4531-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d4531-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d4531-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d4531-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4531-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="d4531-106">Attributes</span></span>  
  
|<span data-ttu-id="d4531-107">attribute</span><span class="sxs-lookup"><span data-stu-id="d4531-107">Attribute</span></span>|<span data-ttu-id="d4531-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4531-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="d4531-109">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="d4531-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="d4531-110">Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="d4531-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4531-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4531-111">Child Elements</span></span>  

 <span data-ttu-id="d4531-112">Keine</span><span class="sxs-lookup"><span data-stu-id="d4531-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4531-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4531-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d4531-114">Element</span><span class="sxs-lookup"><span data-stu-id="d4531-114">Element</span></span>|<span data-ttu-id="d4531-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4531-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d4531-116">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="d4531-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4531-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4531-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d4531-118">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d4531-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d4531-119">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d4531-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d4531-120">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d4531-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
