---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176812"
---
# <a name="clientvia"></a><span data-ttu-id="dfbcd-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="dfbcd-101">\<clientVia></span></span>
<span data-ttu-id="dfbcd-102">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="dfbcd-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="dfbcd-103">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="dfbcd-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="dfbcd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dfbcd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dfbcd-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="dfbcd-105">\<behaviors></span></span>  
<span data-ttu-id="dfbcd-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="dfbcd-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="dfbcd-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dfbcd-107">\<behavior></span></span>  
<span data-ttu-id="dfbcd-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="dfbcd-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfbcd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfbcd-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfbcd-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dfbcd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dfbcd-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfbcd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfbcd-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="dfbcd-112">Attributes</span></span>  
  
|<span data-ttu-id="dfbcd-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="dfbcd-113">Attribute</span></span>|<span data-ttu-id="dfbcd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfbcd-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="dfbcd-115">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="dfbcd-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfbcd-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dfbcd-116">Child Elements</span></span>  
 <span data-ttu-id="dfbcd-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="dfbcd-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfbcd-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dfbcd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dfbcd-119">Element</span><span class="sxs-lookup"><span data-stu-id="dfbcd-119">Element</span></span>|<span data-ttu-id="dfbcd-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfbcd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfbcd-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dfbcd-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="dfbcd-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="dfbcd-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfbcd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfbcd-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
