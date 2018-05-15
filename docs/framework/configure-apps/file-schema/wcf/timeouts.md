---
title: '&lt;timeOuts&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 1f0638f85177d2acb6f61e3246a1a5ee9a4e2f5c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="cdbea-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="cdbea-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="cdbea-103">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="cdbea-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="cdbea-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cdbea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cdbea-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="cdbea-105">\<client></span></span>  
<span data-ttu-id="cdbea-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="cdbea-106">\<endpoint></span></span>  
<span data-ttu-id="cdbea-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="cdbea-107">\<host></span></span>  
<span data-ttu-id="cdbea-108">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="cdbea-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdbea-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdbea-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdbea-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cdbea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cdbea-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cdbea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdbea-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="cdbea-112">Attributes</span></span>  
  
|<span data-ttu-id="cdbea-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="cdbea-113">Attribute</span></span>|<span data-ttu-id="cdbea-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdbea-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="cdbea-115">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="cdbea-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="cdbea-116">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="cdbea-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdbea-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cdbea-117">Child Elements</span></span>  
 <span data-ttu-id="cdbea-118">Keine</span><span class="sxs-lookup"><span data-stu-id="cdbea-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdbea-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cdbea-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cdbea-120">Element</span><span class="sxs-lookup"><span data-stu-id="cdbea-120">Element</span></span>|<span data-ttu-id="cdbea-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdbea-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdbea-122">\<Host ></span><span class="sxs-lookup"><span data-stu-id="cdbea-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="cdbea-123">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="cdbea-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cdbea-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdbea-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="cdbea-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="cdbea-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
