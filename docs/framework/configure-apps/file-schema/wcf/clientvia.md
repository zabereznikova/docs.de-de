---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176812"
---
# <a name="clientvia"></a><span data-ttu-id="6f7db-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="6f7db-101">\<clientVia></span></span>
<span data-ttu-id="6f7db-102">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="6f7db-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="6f7db-103">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="6f7db-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="6f7db-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6f7db-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6f7db-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6f7db-105">\<behaviors></span></span>  
<span data-ttu-id="6f7db-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6f7db-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="6f7db-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6f7db-107">\<behavior></span></span>  
<span data-ttu-id="6f7db-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="6f7db-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f7db-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f7db-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f7db-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6f7db-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f7db-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f7db-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f7db-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6f7db-112">Attributes</span></span>  
  
|<span data-ttu-id="6f7db-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6f7db-113">Attribute</span></span>|<span data-ttu-id="6f7db-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f7db-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="6f7db-115">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="6f7db-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f7db-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f7db-116">Child Elements</span></span>  
 <span data-ttu-id="6f7db-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="6f7db-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f7db-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f7db-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6f7db-119">Element</span><span class="sxs-lookup"><span data-stu-id="6f7db-119">Element</span></span>|<span data-ttu-id="6f7db-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f7db-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f7db-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6f7db-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6f7db-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="6f7db-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f7db-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f7db-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
