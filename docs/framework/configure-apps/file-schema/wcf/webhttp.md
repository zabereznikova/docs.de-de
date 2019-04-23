---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 795e61b9054d2ea9276970988018c50099bcbe17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129648"
---
# <a name="webhttp"></a><span data-ttu-id="77bd2-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="77bd2-101">\<webHttp></span></span>
<span data-ttu-id="77bd2-102">Dieses Element gibt anhand der Konfiguration <xref:System.ServiceModel.Description.WebHttpBehavior> in einem Endpunkt an.</span><span class="sxs-lookup"><span data-stu-id="77bd2-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="77bd2-103">Dieses Verhalten, bei der Verwendung in Verbindung mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standardbindung, aktiviert das Webprogrammiermodell für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="77bd2-103">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="77bd2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="77bd2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="77bd2-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="77bd2-105">\<behaviors></span></span>  
<span data-ttu-id="77bd2-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="77bd2-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="77bd2-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="77bd2-107">\<behavior></span></span>  
<span data-ttu-id="77bd2-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="77bd2-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77bd2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="77bd2-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77bd2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="77bd2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="77bd2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="77bd2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77bd2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="77bd2-112">Attributes</span></span>  
  
|<span data-ttu-id="77bd2-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="77bd2-113">Attribute</span></span>|<span data-ttu-id="77bd2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77bd2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77bd2-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="77bd2-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="77bd2-116">Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format.</span><span class="sxs-lookup"><span data-stu-id="77bd2-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="77bd2-117">Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="77bd2-118">Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="77bd2-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="77bd2-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="77bd2-119">defaultBodyStyle</span></span>|<span data-ttu-id="77bd2-120">Gibt den Standardtextstil der zurückgegebenen Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="77bd2-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="77bd2-121">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Web.WebMessageBodyStyle> und [WCF Web-HTTP-Formatierung](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="77bd2-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="77bd2-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="77bd2-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="77bd2-123">Gibt das Standardformat für ausgehende Antwortnachrichten an.</span><span class="sxs-lookup"><span data-stu-id="77bd2-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="77bd2-124">Weitere Informationen finden Sie unter [WCF Web-HTTP-Formatierung](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="77bd2-124">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="77bd2-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="77bd2-125">faultExceptionEnabled</span></span>|<span data-ttu-id="77bd2-126">Ruft das Flag ab bzw. legt das Flag fest, das angibt, ob ein FaultException-Element generiert wird, wenn ein interner Serverfehler (HTTP-Statuscode: 500) auftritt.</span><span class="sxs-lookup"><span data-stu-id="77bd2-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="77bd2-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="77bd2-127">helpEnabled</span></span>|<span data-ttu-id="77bd2-128">Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob die Hilfeseite aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="77bd2-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77bd2-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="77bd2-129">Child Elements</span></span>  
 <span data-ttu-id="77bd2-130">Keine</span><span class="sxs-lookup"><span data-stu-id="77bd2-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77bd2-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="77bd2-131">Parent Elements</span></span>  
  
|<span data-ttu-id="77bd2-132">Element</span><span class="sxs-lookup"><span data-stu-id="77bd2-132">Element</span></span>|<span data-ttu-id="77bd2-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77bd2-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77bd2-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="77bd2-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="77bd2-135">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="77bd2-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77bd2-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77bd2-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="77bd2-137">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="77bd2-137">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="77bd2-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="77bd2-138">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
