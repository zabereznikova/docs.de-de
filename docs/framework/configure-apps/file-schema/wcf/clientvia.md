---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 063dbee71a91e098e26026ea78c74642115c7955
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266662"
---
# <a name="clientvia"></a><span data-ttu-id="f6be8-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="f6be8-101">\<clientVia></span></span>
<span data-ttu-id="f6be8-102">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="f6be8-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="f6be8-103">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="f6be8-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="f6be8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f6be8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6be8-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f6be8-105">\<behaviors></span></span>  
<span data-ttu-id="f6be8-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f6be8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f6be8-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f6be8-107">\<behavior></span></span>  
<span data-ttu-id="f6be8-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="f6be8-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6be8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6be8-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6be8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f6be8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f6be8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6be8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6be8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f6be8-112">Attributes</span></span>  
  
|<span data-ttu-id="f6be8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f6be8-113">Attribute</span></span>|<span data-ttu-id="f6be8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6be8-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="f6be8-115">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="f6be8-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6be8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f6be8-116">Child Elements</span></span>  
 <span data-ttu-id="f6be8-117">Keine</span><span class="sxs-lookup"><span data-stu-id="f6be8-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6be8-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f6be8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f6be8-119">Element</span><span class="sxs-lookup"><span data-stu-id="f6be8-119">Element</span></span>|<span data-ttu-id="f6be8-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6be8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6be8-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f6be8-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f6be8-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="f6be8-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6be8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6be8-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
