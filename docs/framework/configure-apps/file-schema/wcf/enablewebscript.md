---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6dc2654b8c51dad53c05a37f5febe15d6d69fd1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="cc807-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="cc807-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="cc807-103">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cc807-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="cc807-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cc807-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc807-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="cc807-105">\<behaviors></span></span>  
<span data-ttu-id="cc807-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cc807-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cc807-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="cc807-107">\<behavior></span></span>  
<span data-ttu-id="cc807-108">\<EnableWebScript ></span><span class="sxs-lookup"><span data-stu-id="cc807-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc807-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc807-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc807-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc807-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cc807-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc807-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc807-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc807-112">Attributes</span></span>  
 <span data-ttu-id="cc807-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="cc807-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cc807-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc807-114">Child Elements</span></span>  
 <span data-ttu-id="cc807-115">Keine</span><span class="sxs-lookup"><span data-stu-id="cc807-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc807-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc807-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cc807-117">Element</span><span class="sxs-lookup"><span data-stu-id="cc807-117">Element</span></span>|<span data-ttu-id="cc807-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc807-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc807-119">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="cc807-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="cc807-120">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="cc807-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc807-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc807-121">Remarks</span></span>  
 <span data-ttu-id="cc807-122">Dieses Verhalten sollte nur verwendet werden, zusammen mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) -standardbindung oder [ \<WebMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) Binding-Element.</span><span class="sxs-lookup"><span data-stu-id="cc807-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="cc807-123">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="cc807-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc807-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc807-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="cc807-125">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="cc807-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="cc807-126">\<WebHttp ></span><span class="sxs-lookup"><span data-stu-id="cc807-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
