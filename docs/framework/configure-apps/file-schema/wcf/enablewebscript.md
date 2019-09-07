---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400387"
---
# <a name="enablewebscript"></a><span data-ttu-id="4e112-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="4e112-101">\<enableWebScript></span></span>
<span data-ttu-id="4e112-102">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e112-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="4e112-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e112-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e112-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e112-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4e112-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4e112-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4e112-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4e112-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4e112-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4e112-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4e112-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<enableWebScript->**</span><span class="sxs-lookup"><span data-stu-id="4e112-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e112-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e112-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e112-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4e112-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4e112-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e112-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e112-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="4e112-112">Attributes</span></span>  
 <span data-ttu-id="4e112-113">Keine</span><span class="sxs-lookup"><span data-stu-id="4e112-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e112-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e112-114">Child Elements</span></span>  
 <span data-ttu-id="4e112-115">Keine</span><span class="sxs-lookup"><span data-stu-id="4e112-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e112-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e112-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4e112-117">Element</span><span class="sxs-lookup"><span data-stu-id="4e112-117">Element</span></span>|<span data-ttu-id="4e112-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e112-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e112-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4e112-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4e112-120">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="4e112-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e112-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e112-121">Remarks</span></span>  
 <span data-ttu-id="4e112-122">Dieses Verhalten sollte nur in Verbindung mit der [ \<WebHttpBinding->](webhttpbinding.md) Standard Bindung oder dem [ \<> Bindungs Element webMessageEncoding](webmessageencoding.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e112-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="4e112-123">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="4e112-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e112-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e112-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="4e112-125">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4e112-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="4e112-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="4e112-126">\<webHttp></span></span>](webhttp.md)
