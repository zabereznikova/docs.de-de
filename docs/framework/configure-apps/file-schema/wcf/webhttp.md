---
title: '&lt;webHttp&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9bf92421d09f25c760f8edc5062b7b7d6276902f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="882bf-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="882bf-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="882bf-103">Dieses Element gibt anhand der Konfiguration <xref:System.ServiceModel.Description.WebHttpBehavior> in einem Endpunkt an.</span><span class="sxs-lookup"><span data-stu-id="882bf-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="882bf-104">Dieses Verhalten, bei der Verwendung in Verbindung mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) -standardbindung ermöglicht das Webprogrammiermodell für einen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Dienst.</span><span class="sxs-lookup"><span data-stu-id="882bf-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>  
  
 <span data-ttu-id="882bf-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="882bf-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="882bf-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="882bf-106">\<behaviors></span></span>  
<span data-ttu-id="882bf-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="882bf-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="882bf-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="882bf-108">\<behavior></span></span>  
<span data-ttu-id="882bf-109">\<WebHttp ></span><span class="sxs-lookup"><span data-stu-id="882bf-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882bf-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="882bf-110">Syntax</span></span>  
  
```xml  
<webHttp />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="882bf-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="882bf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="882bf-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="882bf-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="882bf-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="882bf-113">Attributes</span></span>  
  
|<span data-ttu-id="882bf-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="882bf-114">Attribute</span></span>|<span data-ttu-id="882bf-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="882bf-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="882bf-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="882bf-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="882bf-117">Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format.</span><span class="sxs-lookup"><span data-stu-id="882bf-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="882bf-118">Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="882bf-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="882bf-119">Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="882bf-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="882bf-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="882bf-120">defaultBodyStyle</span></span>|<span data-ttu-id="882bf-121">Gibt den Standardtextstil der zurückgegebenen Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="882bf-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="882bf-122">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Web.WebMessageBodyStyle> und [WCF Web-HTTP-Formatierung](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="882bf-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="882bf-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="882bf-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="882bf-124">Gibt das Standardformat für ausgehende Antwortnachrichten an.</span><span class="sxs-lookup"><span data-stu-id="882bf-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="882bf-125">Weitere Informationen finden Sie unter [WCF Web-HTTP-Formatierung](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="882bf-125">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="882bf-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="882bf-126">faultExceptionEnabled</span></span>|<span data-ttu-id="882bf-127">Ruft das Flag ab bzw. legt das Flag fest, das angibt, ob ein FaultException-Element generiert wird, wenn ein interner Serverfehler (HTTP-Statuscode: 500) auftritt.</span><span class="sxs-lookup"><span data-stu-id="882bf-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="882bf-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="882bf-128">helpEnabled</span></span>|<span data-ttu-id="882bf-129">Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob die Hilfeseite aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="882bf-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="882bf-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="882bf-130">Child Elements</span></span>  
 <span data-ttu-id="882bf-131">Keine</span><span class="sxs-lookup"><span data-stu-id="882bf-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="882bf-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="882bf-132">Parent Elements</span></span>  
  
|<span data-ttu-id="882bf-133">Element</span><span class="sxs-lookup"><span data-stu-id="882bf-133">Element</span></span>|<span data-ttu-id="882bf-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="882bf-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="882bf-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="882bf-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="882bf-136">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="882bf-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="882bf-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="882bf-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="882bf-138">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="882bf-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="882bf-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="882bf-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
