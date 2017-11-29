---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7cdc85c23202154728610ab4721bf830004928c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="ed1b6-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="ed1b6-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="ed1b6-103">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ed1b6-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="ed1b6-104">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ed1b6-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="ed1b6-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ed1b6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ed1b6-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="ed1b6-106">\<behaviors></span></span>  
<span data-ttu-id="ed1b6-107">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ed1b6-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="ed1b6-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="ed1b6-108">\<behavior></span></span>  
<span data-ttu-id="ed1b6-109">\<ClientVia ></span><span class="sxs-lookup"><span data-stu-id="ed1b6-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed1b6-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed1b6-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed1b6-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed1b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ed1b6-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed1b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed1b6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed1b6-113">Attributes</span></span>  
  
|<span data-ttu-id="ed1b6-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ed1b6-114">Attribute</span></span>|<span data-ttu-id="ed1b6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed1b6-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="ed1b6-116">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="ed1b6-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed1b6-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed1b6-117">Child Elements</span></span>  
 <span data-ttu-id="ed1b6-118">Keine</span><span class="sxs-lookup"><span data-stu-id="ed1b6-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed1b6-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed1b6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ed1b6-120">Element</span><span class="sxs-lookup"><span data-stu-id="ed1b6-120">Element</span></span>|<span data-ttu-id="ed1b6-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed1b6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed1b6-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="ed1b6-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ed1b6-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="ed1b6-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed1b6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed1b6-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
