---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212101"
---
# <a name="baseaddresses"></a><span data-ttu-id="073e3-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="073e3-101">\<baseAddresses></span></span>
<span data-ttu-id="073e3-102">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="073e3-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="073e3-103">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="073e3-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="073e3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="073e3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="073e3-105">\<client></span><span class="sxs-lookup"><span data-stu-id="073e3-105">\<client></span></span>  
<span data-ttu-id="073e3-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="073e3-106">\<endpoint></span></span>  
<span data-ttu-id="073e3-107">\<host></span><span class="sxs-lookup"><span data-stu-id="073e3-107">\<host></span></span>  
<span data-ttu-id="073e3-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="073e3-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073e3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="073e3-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="073e3-110">Typ</span><span class="sxs-lookup"><span data-stu-id="073e3-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="073e3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="073e3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="073e3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="073e3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="073e3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="073e3-113">Attributes</span></span>  
 <span data-ttu-id="073e3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="073e3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="073e3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="073e3-115">Child Elements</span></span>  
  
|<span data-ttu-id="073e3-116">Element</span><span class="sxs-lookup"><span data-stu-id="073e3-116">Element</span></span>|<span data-ttu-id="073e3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="073e3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="073e3-118">\<add></span><span class="sxs-lookup"><span data-stu-id="073e3-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="073e3-119">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="073e3-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="073e3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="073e3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="073e3-121">Element</span><span class="sxs-lookup"><span data-stu-id="073e3-121">Element</span></span>|<span data-ttu-id="073e3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="073e3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="073e3-123">\<host></span><span class="sxs-lookup"><span data-stu-id="073e3-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="073e3-124">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="073e3-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="073e3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="073e3-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="073e3-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="073e3-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
