---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 716d960e2d5f896976c22a60d419d9b165b36178
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202460"
---
# \<webHttp>

<span data-ttu-id="7ff66-101">Dieses Element gibt anhand der Konfiguration <xref:System.ServiceModel.Description.WebHttpBehavior> in einem Endpunkt an.</span><span class="sxs-lookup"><span data-stu-id="7ff66-101">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="7ff66-102">Wenn dieses Verhalten in Verbindung mit der [\<webHttpBinding>](webhttpbinding.md) Standard Bindung verwendet wird, wird das webprogrammier Modell für einen Windows Communication Foundation (WCF)-Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ff66-102">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="7ff66-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ff66-103">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ff66-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ff66-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7ff66-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ff66-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ff66-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ff66-106">Attributes</span></span>  
  
|<span data-ttu-id="7ff66-107">attribute</span><span class="sxs-lookup"><span data-stu-id="7ff66-107">Attribute</span></span>|<span data-ttu-id="7ff66-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ff66-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ff66-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="7ff66-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="7ff66-110">Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format.</span><span class="sxs-lookup"><span data-stu-id="7ff66-110">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="7ff66-111">Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7ff66-111">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="7ff66-112">Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ff66-112">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="7ff66-113">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="7ff66-113">defaultBodyStyle</span></span>|<span data-ttu-id="7ff66-114">Gibt den Standardtextstil der zurückgegebenen Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="7ff66-114">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="7ff66-115">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Web.WebMessageBodyStyle> und [WCF-Web-http-Formatierung](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="7ff66-115">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="7ff66-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="7ff66-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="7ff66-117">Gibt das Standardformat für ausgehende Antwortnachrichten an.</span><span class="sxs-lookup"><span data-stu-id="7ff66-117">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="7ff66-118">Weitere Informationen finden Sie unter [WCF-Web-http-Formatierung](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="7ff66-118">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="7ff66-119">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="7ff66-119">faultExceptionEnabled</span></span>|<span data-ttu-id="7ff66-120">Ruft das Flag ab bzw. legt das Flag fest, das angibt, ob ein FaultException-Element generiert wird, wenn ein interner Serverfehler (HTTP-Statuscode: 500) auftritt.</span><span class="sxs-lookup"><span data-stu-id="7ff66-120">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="7ff66-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="7ff66-121">helpEnabled</span></span>|<span data-ttu-id="7ff66-122">Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob die Hilfeseite aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7ff66-122">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ff66-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ff66-123">Child Elements</span></span>  

 <span data-ttu-id="7ff66-124">Keine</span><span class="sxs-lookup"><span data-stu-id="7ff66-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ff66-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ff66-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7ff66-126">Element</span><span class="sxs-lookup"><span data-stu-id="7ff66-126">Element</span></span>|<span data-ttu-id="7ff66-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ff66-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7ff66-128">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="7ff66-128">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ff66-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ff66-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="7ff66-130">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7ff66-130">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
