---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398110"
---
# <a name="clientvia"></a><span data-ttu-id="b0504-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="b0504-101">\<clientVia></span></span>
<span data-ttu-id="b0504-102">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="b0504-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="b0504-103">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="b0504-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="b0504-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0504-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b0504-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b0504-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b0504-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b0504-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b0504-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b0504-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b0504-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b0504-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b0504-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientVia->**</span><span class="sxs-lookup"><span data-stu-id="b0504-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0504-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0504-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0504-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0504-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b0504-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0504-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0504-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0504-113">Attributes</span></span>  
  
|<span data-ttu-id="b0504-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0504-114">Attribute</span></span>|<span data-ttu-id="b0504-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0504-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="b0504-116">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="b0504-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0504-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0504-117">Child Elements</span></span>  
 <span data-ttu-id="b0504-118">None</span><span class="sxs-lookup"><span data-stu-id="b0504-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0504-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0504-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b0504-120">Element</span><span class="sxs-lookup"><span data-stu-id="b0504-120">Element</span></span>|<span data-ttu-id="b0504-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0504-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0504-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b0504-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b0504-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="b0504-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0504-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0504-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
