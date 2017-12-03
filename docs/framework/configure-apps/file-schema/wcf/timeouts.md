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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da80ab797078e1fe912ccbfff07d7fb2da49664e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="ca019-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="ca019-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="ca019-103">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="ca019-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="ca019-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ca019-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca019-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="ca019-105">\<client></span></span>  
<span data-ttu-id="ca019-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="ca019-106">\<endpoint></span></span>  
<span data-ttu-id="ca019-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="ca019-107">\<host></span></span>  
<span data-ttu-id="ca019-108">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="ca019-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca019-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca019-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca019-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ca019-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca019-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca019-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca019-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ca019-112">Attributes</span></span>  
  
|<span data-ttu-id="ca019-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ca019-113">Attribute</span></span>|<span data-ttu-id="ca019-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca019-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ca019-115">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="ca019-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="ca019-116">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="ca019-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca019-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca019-117">Child Elements</span></span>  
 <span data-ttu-id="ca019-118">Keine</span><span class="sxs-lookup"><span data-stu-id="ca019-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca019-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca019-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ca019-120">Element</span><span class="sxs-lookup"><span data-stu-id="ca019-120">Element</span></span>|<span data-ttu-id="ca019-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca019-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca019-122">\<Host ></span><span class="sxs-lookup"><span data-stu-id="ca019-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="ca019-123">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="ca019-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca019-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca019-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="ca019-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="ca019-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
