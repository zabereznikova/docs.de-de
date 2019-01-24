---
title: '&lt;privacyNoticeAt&gt;'
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: bf694911e0715275991084604ce44535d9183eff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683715"
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="ce188-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="ce188-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="ce188-103">Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.</span><span class="sxs-lookup"><span data-stu-id="ce188-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="ce188-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce188-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ce188-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ce188-105">\<bindings></span></span>  
<span data-ttu-id="ce188-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ce188-106">\<customBinding></span></span>  
<span data-ttu-id="ce188-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ce188-107">\<binding></span></span>  
<span data-ttu-id="ce188-108">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="ce188-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce188-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce188-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="ce188-110">Typ</span><span class="sxs-lookup"><span data-stu-id="ce188-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce188-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce188-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce188-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce188-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce188-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce188-113">Attributes</span></span>  
  
|<span data-ttu-id="ce188-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce188-114">Attribute</span></span>|<span data-ttu-id="ce188-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce188-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="ce188-116">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="ce188-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="ce188-117">Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="ce188-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce188-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce188-118">Child Elements</span></span>  
 <span data-ttu-id="ce188-119">Keine</span><span class="sxs-lookup"><span data-stu-id="ce188-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce188-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce188-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ce188-121">Element</span><span class="sxs-lookup"><span data-stu-id="ce188-121">Element</span></span>|<span data-ttu-id="ce188-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce188-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce188-123">\<binding></span><span class="sxs-lookup"><span data-stu-id="ce188-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ce188-124">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ce188-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce188-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce188-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ce188-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ce188-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ce188-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ce188-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ce188-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ce188-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ce188-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ce188-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
