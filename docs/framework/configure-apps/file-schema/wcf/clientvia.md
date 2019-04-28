---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673627"
---
# <a name="clientvia"></a><span data-ttu-id="8f0c5-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="8f0c5-101">\<clientVia></span></span>
<span data-ttu-id="8f0c5-102">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8f0c5-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="8f0c5-103">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="8f0c5-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="8f0c5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8f0c5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f0c5-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8f0c5-105">\<behaviors></span></span>  
<span data-ttu-id="8f0c5-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8f0c5-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8f0c5-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8f0c5-107">\<behavior></span></span>  
<span data-ttu-id="8f0c5-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="8f0c5-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f0c5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f0c5-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f0c5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f0c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f0c5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f0c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f0c5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f0c5-112">Attributes</span></span>  
  
|<span data-ttu-id="8f0c5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f0c5-113">Attribute</span></span>|<span data-ttu-id="8f0c5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f0c5-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="8f0c5-115">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="8f0c5-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f0c5-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f0c5-116">Child Elements</span></span>  
 <span data-ttu-id="8f0c5-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="8f0c5-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f0c5-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f0c5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8f0c5-119">Element</span><span class="sxs-lookup"><span data-stu-id="8f0c5-119">Element</span></span>|<span data-ttu-id="8f0c5-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f0c5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f0c5-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8f0c5-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8f0c5-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="8f0c5-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f0c5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f0c5-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
