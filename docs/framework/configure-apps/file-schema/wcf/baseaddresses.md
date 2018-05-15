---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 8de962cc70e1399dd1e9459473055651f9aca5fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="3bcda-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="3bcda-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="3bcda-103">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="3bcda-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="3bcda-104">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3bcda-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="3bcda-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3bcda-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3bcda-106">\<Client ></span><span class="sxs-lookup"><span data-stu-id="3bcda-106">\<client></span></span>  
<span data-ttu-id="3bcda-107">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="3bcda-107">\<endpoint></span></span>  
<span data-ttu-id="3bcda-108">\<Host ></span><span class="sxs-lookup"><span data-stu-id="3bcda-108">\<host></span></span>  
<span data-ttu-id="3bcda-109">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="3bcda-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bcda-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bcda-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="3bcda-111">Typ</span><span class="sxs-lookup"><span data-stu-id="3bcda-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bcda-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3bcda-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3bcda-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3bcda-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bcda-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3bcda-114">Attributes</span></span>  
 <span data-ttu-id="3bcda-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3bcda-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3bcda-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bcda-116">Child Elements</span></span>  
  
|<span data-ttu-id="3bcda-117">Element</span><span class="sxs-lookup"><span data-stu-id="3bcda-117">Element</span></span>|<span data-ttu-id="3bcda-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bcda-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bcda-119">\<add></span><span class="sxs-lookup"><span data-stu-id="3bcda-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="3bcda-120">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="3bcda-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3bcda-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bcda-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3bcda-122">Element</span><span class="sxs-lookup"><span data-stu-id="3bcda-122">Element</span></span>|<span data-ttu-id="3bcda-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bcda-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bcda-124">\<Host ></span><span class="sxs-lookup"><span data-stu-id="3bcda-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="3bcda-125">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="3bcda-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bcda-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bcda-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="3bcda-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="3bcda-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
