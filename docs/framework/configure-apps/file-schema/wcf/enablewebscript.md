---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400387"
---
# \<enableWebScript>
<span data-ttu-id="e9a52-101">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9a52-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="e9a52-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9a52-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9a52-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a52-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e9a52-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9a52-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9a52-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9a52-105">Attributes</span></span>  
 <span data-ttu-id="e9a52-106">Keine</span><span class="sxs-lookup"><span data-stu-id="e9a52-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9a52-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a52-107">Child Elements</span></span>  
 <span data-ttu-id="e9a52-108">Keine.</span><span class="sxs-lookup"><span data-stu-id="e9a52-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9a52-109">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a52-109">Parent Elements</span></span>  
  
|<span data-ttu-id="e9a52-110">Element</span><span class="sxs-lookup"><span data-stu-id="e9a52-110">Element</span></span>|<span data-ttu-id="e9a52-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e9a52-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e9a52-112">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="e9a52-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9a52-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9a52-113">Remarks</span></span>  
 <span data-ttu-id="e9a52-114">Dieses Verhalten sollte nur in Verbindung mit der [\<webHttpBinding>](webhttpbinding.md) Standard Bindung oder dem Bindungs Element verwendet werden [\<webMessageEncoding>](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="e9a52-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="e9a52-115">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="e9a52-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a52-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a52-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="e9a52-117">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="e9a52-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
