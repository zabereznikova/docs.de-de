---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 624b52c0618362f48063c8f7e7c53c5a68d7de8f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400027"
---
# <a name="privacynoticeat"></a><span data-ttu-id="572d2-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="572d2-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="572d2-102">Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.</span><span class="sxs-lookup"><span data-stu-id="572d2-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="572d2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="572d2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="572d2-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="572d2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="572d2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="572d2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="572d2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="572d2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="572d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="572d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="572d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<PrivacyNotice->**</span><span class="sxs-lookup"><span data-stu-id="572d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572d2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="572d2-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="572d2-110">Typ</span><span class="sxs-lookup"><span data-stu-id="572d2-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="572d2-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="572d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="572d2-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="572d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="572d2-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="572d2-113">Attributes</span></span>  
  
|<span data-ttu-id="572d2-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="572d2-114">Attribute</span></span>|<span data-ttu-id="572d2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="572d2-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="572d2-116">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="572d2-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="572d2-117">Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="572d2-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="572d2-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="572d2-118">Child Elements</span></span>  
 <span data-ttu-id="572d2-119">Keine</span><span class="sxs-lookup"><span data-stu-id="572d2-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="572d2-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="572d2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="572d2-121">Element</span><span class="sxs-lookup"><span data-stu-id="572d2-121">Element</span></span>|<span data-ttu-id="572d2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="572d2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="572d2-123">\<binding></span><span class="sxs-lookup"><span data-stu-id="572d2-123">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="572d2-124">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="572d2-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="572d2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="572d2-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="572d2-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="572d2-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="572d2-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="572d2-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="572d2-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="572d2-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="572d2-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="572d2-129">\<customBinding></span></span>](custombinding.md)
