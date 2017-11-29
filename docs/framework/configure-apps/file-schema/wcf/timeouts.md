---
title: '&lt;timeOuts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41ebd88f64b001b577342562c9c3010b307aaccc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="beeb4-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="beeb4-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="beeb4-103">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="beeb4-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="beeb4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="beeb4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="beeb4-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="beeb4-105">\<client></span></span>  
<span data-ttu-id="beeb4-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="beeb4-106">\<endpoint></span></span>  
<span data-ttu-id="beeb4-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="beeb4-107">\<host></span></span>  
<span data-ttu-id="beeb4-108">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="beeb4-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beeb4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="beeb4-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beeb4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="beeb4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="beeb4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="beeb4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beeb4-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="beeb4-112">Attributes</span></span>  
  
|<span data-ttu-id="beeb4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="beeb4-113">Attribute</span></span>|<span data-ttu-id="beeb4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beeb4-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="beeb4-115">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="beeb4-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="beeb4-116">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="beeb4-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="beeb4-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beeb4-117">Child Elements</span></span>  
 <span data-ttu-id="beeb4-118">Keine</span><span class="sxs-lookup"><span data-stu-id="beeb4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="beeb4-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beeb4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="beeb4-120">Element</span><span class="sxs-lookup"><span data-stu-id="beeb4-120">Element</span></span>|<span data-ttu-id="beeb4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beeb4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="beeb4-122">\<Host ></span><span class="sxs-lookup"><span data-stu-id="beeb4-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="beeb4-123">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="beeb4-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="beeb4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beeb4-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="beeb4-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="beeb4-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
