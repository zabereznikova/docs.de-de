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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3782eb9cbe793fef450c8b1c58456a1d4f7b0b94
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="04305-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="04305-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="04305-103">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="04305-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="04305-104">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="04305-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="04305-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="04305-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="04305-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="04305-106">\<behaviors></span></span>  
<span data-ttu-id="04305-107">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="04305-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="04305-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="04305-108">\<behavior></span></span>  
<span data-ttu-id="04305-109">\<ClientVia ></span><span class="sxs-lookup"><span data-stu-id="04305-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04305-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="04305-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04305-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="04305-111">Attributes and Elements</span></span>  
 <span data-ttu-id="04305-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04305-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04305-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="04305-113">Attributes</span></span>  
  
|<span data-ttu-id="04305-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="04305-114">Attribute</span></span>|<span data-ttu-id="04305-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04305-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="04305-116">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="04305-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04305-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04305-117">Child Elements</span></span>  
 <span data-ttu-id="04305-118">Keine</span><span class="sxs-lookup"><span data-stu-id="04305-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04305-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04305-119">Parent Elements</span></span>  
  
|<span data-ttu-id="04305-120">Element</span><span class="sxs-lookup"><span data-stu-id="04305-120">Element</span></span>|<span data-ttu-id="04305-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04305-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04305-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="04305-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="04305-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="04305-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04305-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04305-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
