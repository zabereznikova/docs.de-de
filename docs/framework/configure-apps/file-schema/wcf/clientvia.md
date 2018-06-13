---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6218bb3f205f2825eb3f10fabf834cfd0396ac87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754131"
---
# <a name="ltclientviagt"></a><span data-ttu-id="d26f4-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="d26f4-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="d26f4-103">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="d26f4-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="d26f4-104">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="d26f4-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="d26f4-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d26f4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d26f4-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d26f4-106">\<behaviors></span></span>  
<span data-ttu-id="d26f4-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d26f4-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="d26f4-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d26f4-108">\<behavior></span></span>  
<span data-ttu-id="d26f4-109">\<ClientVia ></span><span class="sxs-lookup"><span data-stu-id="d26f4-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26f4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d26f4-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d26f4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d26f4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d26f4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d26f4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d26f4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="d26f4-113">Attributes</span></span>  
  
|<span data-ttu-id="d26f4-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="d26f4-114">Attribute</span></span>|<span data-ttu-id="d26f4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d26f4-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="d26f4-116">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="d26f4-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d26f4-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d26f4-117">Child Elements</span></span>  
 <span data-ttu-id="d26f4-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="d26f4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d26f4-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d26f4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d26f4-120">Element</span><span class="sxs-lookup"><span data-stu-id="d26f4-120">Element</span></span>|<span data-ttu-id="d26f4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d26f4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d26f4-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d26f4-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d26f4-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="d26f4-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d26f4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d26f4-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
