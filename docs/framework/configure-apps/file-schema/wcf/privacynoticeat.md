---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200765"
---
# <a name="privacynoticeat"></a><span data-ttu-id="7cbb3-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="7cbb3-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="7cbb3-102">Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="7cbb3-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7cbb3-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7cbb3-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7cbb3-104">\<bindings></span></span>  
<span data-ttu-id="7cbb3-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7cbb3-105">\<customBinding></span></span>  
<span data-ttu-id="7cbb3-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="7cbb3-106">\<binding></span></span>  
<span data-ttu-id="7cbb3-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="7cbb3-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbb3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cbb3-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="7cbb3-109">Typ</span><span class="sxs-lookup"><span data-stu-id="7cbb3-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cbb3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7cbb3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7cbb3-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cbb3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7cbb3-112">Attributes</span></span>  
  
|<span data-ttu-id="7cbb3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7cbb3-113">Attribute</span></span>|<span data-ttu-id="7cbb3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cbb3-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="7cbb3-115">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="7cbb3-116">Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cbb3-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7cbb3-117">Child Elements</span></span>  
 <span data-ttu-id="7cbb3-118">Keine</span><span class="sxs-lookup"><span data-stu-id="7cbb3-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cbb3-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7cbb3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7cbb3-120">Element</span><span class="sxs-lookup"><span data-stu-id="7cbb3-120">Element</span></span>|<span data-ttu-id="7cbb3-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cbb3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cbb3-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="7cbb3-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7cbb3-123">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7cbb3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cbb3-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7cbb3-125">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7cbb3-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7cbb3-126">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="7cbb3-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7cbb3-127">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="7cbb3-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7cbb3-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7cbb3-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
