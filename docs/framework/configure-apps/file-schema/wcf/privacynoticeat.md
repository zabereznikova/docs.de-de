---
title: '&lt;privacyNoticeAt&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30b3f0bdd1aa02473470c354a730bcfa450f0264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="a7fbc-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="a7fbc-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="a7fbc-103">Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.</span><span class="sxs-lookup"><span data-stu-id="a7fbc-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="a7fbc-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a7fbc-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-105">\<bindings></span></span>  
<span data-ttu-id="a7fbc-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-106">\<customBinding></span></span>  
<span data-ttu-id="a7fbc-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-107">\<binding></span></span>  
<span data-ttu-id="a7fbc-108">\<Das PrivacyNotice ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7fbc-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7fbc-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="a7fbc-110">Typ</span><span class="sxs-lookup"><span data-stu-id="a7fbc-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7fbc-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7fbc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a7fbc-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7fbc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7fbc-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7fbc-113">Attributes</span></span>  
  
|<span data-ttu-id="a7fbc-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="a7fbc-114">Attribute</span></span>|<span data-ttu-id="a7fbc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7fbc-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="a7fbc-116">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="a7fbc-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="a7fbc-117">Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="a7fbc-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7fbc-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7fbc-118">Child Elements</span></span>  
 <span data-ttu-id="a7fbc-119">Keine</span><span class="sxs-lookup"><span data-stu-id="a7fbc-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7fbc-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7fbc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a7fbc-121">Element</span><span class="sxs-lookup"><span data-stu-id="a7fbc-121">Element</span></span>|<span data-ttu-id="a7fbc-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7fbc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7fbc-123">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a7fbc-124">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="a7fbc-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7fbc-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7fbc-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a7fbc-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a7fbc-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a7fbc-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="a7fbc-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a7fbc-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a7fbc-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a7fbc-129">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="a7fbc-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
