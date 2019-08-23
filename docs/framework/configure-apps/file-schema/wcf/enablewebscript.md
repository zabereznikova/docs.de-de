---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919113"
---
# <a name="enablewebscript"></a><span data-ttu-id="2d360-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="2d360-101">\<enableWebScript></span></span>
<span data-ttu-id="2d360-102">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d360-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="2d360-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2d360-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d360-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2d360-104">\<behaviors></span></span>  
<span data-ttu-id="2d360-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2d360-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="2d360-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d360-106">\<behavior></span></span>  
<span data-ttu-id="2d360-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="2d360-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d360-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d360-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d360-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d360-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2d360-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d360-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d360-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d360-111">Attributes</span></span>  
 <span data-ttu-id="2d360-112">Keine</span><span class="sxs-lookup"><span data-stu-id="2d360-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d360-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d360-113">Child Elements</span></span>  
 <span data-ttu-id="2d360-114">Keine</span><span class="sxs-lookup"><span data-stu-id="2d360-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d360-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d360-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2d360-116">Element</span><span class="sxs-lookup"><span data-stu-id="2d360-116">Element</span></span>|<span data-ttu-id="2d360-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d360-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d360-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d360-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2d360-119">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="2d360-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d360-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d360-120">Remarks</span></span>  
 <span data-ttu-id="2d360-121">Dieses Verhalten sollte nur in Verbindung mit der [ \<WebHttpBinding->](webhttpbinding.md) Standard Bindung oder dem [ \<> Bindungs Element webMessageEncoding](webmessageencoding.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d360-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="2d360-122">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="2d360-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d360-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d360-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="2d360-124">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="2d360-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="2d360-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="2d360-125">\<webHttp></span></span>](webhttp.md)
