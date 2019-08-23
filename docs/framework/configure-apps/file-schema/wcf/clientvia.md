---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b12a882d942555a24c145b243d2cea764ba106b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919505"
---
# <a name="clientvia"></a><span data-ttu-id="acd16-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="acd16-101">\<clientVia></span></span>
<span data-ttu-id="acd16-102">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="acd16-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="acd16-103">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="acd16-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="acd16-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="acd16-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="acd16-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="acd16-105">\<behaviors></span></span>  
<span data-ttu-id="acd16-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="acd16-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="acd16-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="acd16-107">\<behavior></span></span>  
<span data-ttu-id="acd16-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="acd16-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd16-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="acd16-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acd16-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="acd16-110">Attributes and Elements</span></span>  
 <span data-ttu-id="acd16-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="acd16-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acd16-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="acd16-112">Attributes</span></span>  
  
|<span data-ttu-id="acd16-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="acd16-113">Attribute</span></span>|<span data-ttu-id="acd16-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acd16-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="acd16-115">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="acd16-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acd16-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acd16-116">Child Elements</span></span>  
 <span data-ttu-id="acd16-117">None</span><span class="sxs-lookup"><span data-stu-id="acd16-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acd16-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acd16-118">Parent Elements</span></span>  
  
|<span data-ttu-id="acd16-119">Element</span><span class="sxs-lookup"><span data-stu-id="acd16-119">Element</span></span>|<span data-ttu-id="acd16-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acd16-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acd16-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="acd16-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="acd16-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="acd16-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acd16-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acd16-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
