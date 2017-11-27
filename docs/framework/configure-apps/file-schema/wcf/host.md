---
title: '&lt;Host&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bded8d718259bf4fc84bfe790db069a77fc2a703
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lthostgt"></a><span data-ttu-id="68e4e-102">&lt;Host&gt;</span><span class="sxs-lookup"><span data-stu-id="68e4e-102">&lt;host&gt;</span></span>
<span data-ttu-id="68e4e-103">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="68e4e-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="68e4e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68e4e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68e4e-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="68e4e-105">\<services></span></span>  
<span data-ttu-id="68e4e-106">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="68e4e-106">\<service></span></span>  
<span data-ttu-id="68e4e-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="68e4e-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68e4e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="68e4e-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="68e4e-109">Typ</span><span class="sxs-lookup"><span data-stu-id="68e4e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68e4e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68e4e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68e4e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68e4e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68e4e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="68e4e-112">Attributes</span></span>  
 <span data-ttu-id="68e4e-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="68e4e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="68e4e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68e4e-114">Child Elements</span></span>  
  
|<span data-ttu-id="68e4e-115">Element</span><span class="sxs-lookup"><span data-stu-id="68e4e-115">Element</span></span>|<span data-ttu-id="68e4e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68e4e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68e4e-117">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="68e4e-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="68e4e-118">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="68e4e-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="68e4e-119">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="68e4e-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="68e4e-120">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="68e4e-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68e4e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68e4e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68e4e-122">Element</span><span class="sxs-lookup"><span data-stu-id="68e4e-122">Element</span></span>|<span data-ttu-id="68e4e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68e4e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68e4e-124">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="68e4e-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="68e4e-125">Gibt die Einstellungen für einen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="68e4e-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68e4e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68e4e-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="68e4e-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="68e4e-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
