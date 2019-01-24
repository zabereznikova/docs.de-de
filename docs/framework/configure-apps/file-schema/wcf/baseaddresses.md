---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730125"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="d0a22-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="d0a22-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="d0a22-103">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="d0a22-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="d0a22-104">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d0a22-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="d0a22-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d0a22-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0a22-106">\<client></span><span class="sxs-lookup"><span data-stu-id="d0a22-106">\<client></span></span>  
<span data-ttu-id="d0a22-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="d0a22-107">\<endpoint></span></span>  
<span data-ttu-id="d0a22-108">\<host></span><span class="sxs-lookup"><span data-stu-id="d0a22-108">\<host></span></span>  
<span data-ttu-id="d0a22-109">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="d0a22-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a22-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0a22-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="d0a22-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d0a22-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0a22-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d0a22-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d0a22-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d0a22-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0a22-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d0a22-114">Attributes</span></span>  
 <span data-ttu-id="d0a22-115">Keine</span><span class="sxs-lookup"><span data-stu-id="d0a22-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0a22-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d0a22-116">Child Elements</span></span>  
  
|<span data-ttu-id="d0a22-117">Element</span><span class="sxs-lookup"><span data-stu-id="d0a22-117">Element</span></span>|<span data-ttu-id="d0a22-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0a22-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0a22-119">\<add></span><span class="sxs-lookup"><span data-stu-id="d0a22-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="d0a22-120">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="d0a22-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0a22-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d0a22-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d0a22-122">Element</span><span class="sxs-lookup"><span data-stu-id="d0a22-122">Element</span></span>|<span data-ttu-id="d0a22-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0a22-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0a22-124">\<host></span><span class="sxs-lookup"><span data-stu-id="d0a22-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="d0a22-125">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="d0a22-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0a22-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0a22-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="d0a22-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="d0a22-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
