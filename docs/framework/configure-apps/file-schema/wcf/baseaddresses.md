---
title: '&lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bf698b64b528b0ea109223a2d94e6725c8ce6b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="20c9f-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="20c9f-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="20c9f-103">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="20c9f-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="20c9f-104">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="20c9f-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="20c9f-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="20c9f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="20c9f-106">\<Client ></span><span class="sxs-lookup"><span data-stu-id="20c9f-106">\<client></span></span>  
<span data-ttu-id="20c9f-107">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="20c9f-107">\<endpoint></span></span>  
<span data-ttu-id="20c9f-108">\<Host ></span><span class="sxs-lookup"><span data-stu-id="20c9f-108">\<host></span></span>  
<span data-ttu-id="20c9f-109">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="20c9f-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c9f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="20c9f-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="20c9f-111">Typ</span><span class="sxs-lookup"><span data-stu-id="20c9f-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20c9f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="20c9f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="20c9f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="20c9f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20c9f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="20c9f-114">Attributes</span></span>  
 <span data-ttu-id="20c9f-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="20c9f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20c9f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20c9f-116">Child Elements</span></span>  
  
|<span data-ttu-id="20c9f-117">Element</span><span class="sxs-lookup"><span data-stu-id="20c9f-117">Element</span></span>|<span data-ttu-id="20c9f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20c9f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20c9f-119">\<add></span><span class="sxs-lookup"><span data-stu-id="20c9f-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="20c9f-120">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="20c9f-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20c9f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20c9f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="20c9f-122">Element</span><span class="sxs-lookup"><span data-stu-id="20c9f-122">Element</span></span>|<span data-ttu-id="20c9f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20c9f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20c9f-124">\<Host ></span><span class="sxs-lookup"><span data-stu-id="20c9f-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="20c9f-125">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="20c9f-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20c9f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20c9f-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="20c9f-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="20c9f-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
