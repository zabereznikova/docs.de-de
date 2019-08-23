---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940501"
---
# <a name="webhttp"></a><span data-ttu-id="c51f8-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="c51f8-101">\<webHttp></span></span>
<span data-ttu-id="c51f8-102">Dieses Element gibt anhand der Konfiguration <xref:System.ServiceModel.Description.WebHttpBehavior> in einem Endpunkt an.</span><span class="sxs-lookup"><span data-stu-id="c51f8-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="c51f8-103">Wenn dieses Verhalten in Verbindung mit der [ \<WebHttpBinding->](webhttpbinding.md) Standard Bindung verwendet wird, wird das webprogrammier Modell für einen Windows Communication Foundation (WCF)-Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c51f8-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="c51f8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c51f8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c51f8-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c51f8-105">\<behaviors></span></span>  
<span data-ttu-id="c51f8-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c51f8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c51f8-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c51f8-107">\<behavior></span></span>  
<span data-ttu-id="c51f8-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="c51f8-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c51f8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c51f8-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c51f8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c51f8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c51f8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c51f8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c51f8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c51f8-112">Attributes</span></span>  
  
|<span data-ttu-id="c51f8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c51f8-113">Attribute</span></span>|<span data-ttu-id="c51f8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c51f8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c51f8-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="c51f8-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="c51f8-116">Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format.</span><span class="sxs-lookup"><span data-stu-id="c51f8-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="c51f8-117">Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="c51f8-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="c51f8-118">Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c51f8-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="c51f8-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="c51f8-119">defaultBodyStyle</span></span>|<span data-ttu-id="c51f8-120">Gibt den Standardtextstil der zurückgegebenen Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="c51f8-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="c51f8-121">Weitere Informationen finden <xref:System.ServiceModel.Web.WebMessageBodyStyle> Sie unter und [WCF-Web-http-Formatierung](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="c51f8-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="c51f8-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="c51f8-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="c51f8-123">Gibt das Standardformat für ausgehende Antwortnachrichten an.</span><span class="sxs-lookup"><span data-stu-id="c51f8-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="c51f8-124">Weitere Informationen finden Sie unter [WCF-Web-http-Formatierung](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="c51f8-124">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="c51f8-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="c51f8-125">faultExceptionEnabled</span></span>|<span data-ttu-id="c51f8-126">Ruft das Flag ab bzw. legt das Flag fest, das angibt, ob ein FaultException-Element generiert wird, wenn ein interner Serverfehler (HTTP-Statuscode: 500) auftritt.</span><span class="sxs-lookup"><span data-stu-id="c51f8-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="c51f8-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="c51f8-127">helpEnabled</span></span>|<span data-ttu-id="c51f8-128">Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob die Hilfeseite aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c51f8-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c51f8-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c51f8-129">Child Elements</span></span>  
 <span data-ttu-id="c51f8-130">Keine</span><span class="sxs-lookup"><span data-stu-id="c51f8-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c51f8-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c51f8-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c51f8-132">Element</span><span class="sxs-lookup"><span data-stu-id="c51f8-132">Element</span></span>|<span data-ttu-id="c51f8-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c51f8-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c51f8-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c51f8-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c51f8-135">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="c51f8-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c51f8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c51f8-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="c51f8-137">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c51f8-137">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="c51f8-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c51f8-138">\<webHttpBinding></span></span>](webhttpbinding.md)
