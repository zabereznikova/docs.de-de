---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 48e56b79f47e84122ddd4d7f55d50044510bfa66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149058"
---
# <a name="ltclientviagt"></a><span data-ttu-id="b3c62-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="b3c62-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="b3c62-103">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="b3c62-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="b3c62-104">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="b3c62-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="b3c62-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b3c62-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3c62-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b3c62-106">\<behaviors></span></span>  
<span data-ttu-id="b3c62-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b3c62-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="b3c62-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="b3c62-108">\<behavior></span></span>  
<span data-ttu-id="b3c62-109">\<ClientVia ></span><span class="sxs-lookup"><span data-stu-id="b3c62-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c62-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3c62-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3c62-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b3c62-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b3c62-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3c62-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3c62-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b3c62-113">Attributes</span></span>  
  
|<span data-ttu-id="b3c62-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b3c62-114">Attribute</span></span>|<span data-ttu-id="b3c62-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3c62-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="b3c62-116">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="b3c62-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3c62-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3c62-117">Child Elements</span></span>  
 <span data-ttu-id="b3c62-118">Keine</span><span class="sxs-lookup"><span data-stu-id="b3c62-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3c62-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3c62-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b3c62-120">Element</span><span class="sxs-lookup"><span data-stu-id="b3c62-120">Element</span></span>|<span data-ttu-id="b3c62-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3c62-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3c62-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b3c62-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b3c62-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="b3c62-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3c62-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3c62-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
