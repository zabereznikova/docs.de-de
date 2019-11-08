---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738762"
---
# <a name="privacynoticeat"></a><span data-ttu-id="197c5-101">\<privacyNoticeAt ></span><span class="sxs-lookup"><span data-stu-id="197c5-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="197c5-102">Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.</span><span class="sxs-lookup"><span data-stu-id="197c5-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="197c5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="197c5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="197c5-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="197c5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="197c5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="197c5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="197c5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="197c5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="197c5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="197c5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="197c5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<PrivacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="197c5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="197c5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="197c5-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="197c5-110">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="197c5-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="197c5-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="197c5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="197c5-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="197c5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="197c5-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="197c5-113">Attributes</span></span>  
  
|<span data-ttu-id="197c5-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="197c5-114">Attribute</span></span>|<span data-ttu-id="197c5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="197c5-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="197c5-116">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="197c5-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="197c5-117">Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="197c5-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="197c5-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="197c5-118">Child Elements</span></span>  
 <span data-ttu-id="197c5-119">Keine</span><span class="sxs-lookup"><span data-stu-id="197c5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="197c5-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="197c5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="197c5-121">Element</span><span class="sxs-lookup"><span data-stu-id="197c5-121">Element</span></span>|<span data-ttu-id="197c5-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="197c5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="197c5-123">\<binding ></span><span class="sxs-lookup"><span data-stu-id="197c5-123">\<binding></span></span>](bindings.md)|<span data-ttu-id="197c5-124">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="197c5-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="197c5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="197c5-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="197c5-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="197c5-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="197c5-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="197c5-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="197c5-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="197c5-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="197c5-129">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="197c5-129">\<customBinding></span></span>](custombinding.md)
