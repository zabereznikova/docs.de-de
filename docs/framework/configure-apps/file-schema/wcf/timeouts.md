---
title: '&lt;timeOuts&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: e39deeb251865b87eb7734e4447088ca2f221d1d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148330"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="9f1fd-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="9f1fd-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="9f1fd-103">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="9f1fd-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="9f1fd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9f1fd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9f1fd-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="9f1fd-105">\<client></span></span>  
<span data-ttu-id="9f1fd-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="9f1fd-106">\<endpoint></span></span>  
<span data-ttu-id="9f1fd-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="9f1fd-107">\<host></span></span>  
<span data-ttu-id="9f1fd-108">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="9f1fd-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f1fd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f1fd-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f1fd-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f1fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9f1fd-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f1fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f1fd-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f1fd-112">Attributes</span></span>  
  
|<span data-ttu-id="9f1fd-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9f1fd-113">Attribute</span></span>|<span data-ttu-id="9f1fd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f1fd-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="9f1fd-115">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="9f1fd-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="9f1fd-116">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="9f1fd-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f1fd-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f1fd-117">Child Elements</span></span>  
 <span data-ttu-id="9f1fd-118">Keine</span><span class="sxs-lookup"><span data-stu-id="9f1fd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f1fd-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f1fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9f1fd-120">Element</span><span class="sxs-lookup"><span data-stu-id="9f1fd-120">Element</span></span>|<span data-ttu-id="9f1fd-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f1fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f1fd-122">\<Host ></span><span class="sxs-lookup"><span data-stu-id="9f1fd-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="9f1fd-123">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="9f1fd-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f1fd-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f1fd-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="9f1fd-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="9f1fd-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
