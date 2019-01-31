---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: dc4b31e729f9037da101bdf3e6cde28e91b1a070
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277016"
---
# <a name="baseaddresses"></a><span data-ttu-id="4237f-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="4237f-101">\<baseAddresses></span></span>
<span data-ttu-id="4237f-102">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="4237f-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="4237f-103">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4237f-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="4237f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4237f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4237f-105">\<client></span><span class="sxs-lookup"><span data-stu-id="4237f-105">\<client></span></span>  
<span data-ttu-id="4237f-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="4237f-106">\<endpoint></span></span>  
<span data-ttu-id="4237f-107">\<host></span><span class="sxs-lookup"><span data-stu-id="4237f-107">\<host></span></span>  
<span data-ttu-id="4237f-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="4237f-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4237f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4237f-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="4237f-110">Typ</span><span class="sxs-lookup"><span data-stu-id="4237f-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4237f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4237f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4237f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4237f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4237f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4237f-113">Attributes</span></span>  
 <span data-ttu-id="4237f-114">Keine</span><span class="sxs-lookup"><span data-stu-id="4237f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4237f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4237f-115">Child Elements</span></span>  
  
|<span data-ttu-id="4237f-116">Element</span><span class="sxs-lookup"><span data-stu-id="4237f-116">Element</span></span>|<span data-ttu-id="4237f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4237f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4237f-118">\<add></span><span class="sxs-lookup"><span data-stu-id="4237f-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="4237f-119">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="4237f-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4237f-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4237f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4237f-121">Element</span><span class="sxs-lookup"><span data-stu-id="4237f-121">Element</span></span>|<span data-ttu-id="4237f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4237f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4237f-123">\<host></span><span class="sxs-lookup"><span data-stu-id="4237f-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="4237f-124">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="4237f-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4237f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4237f-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="4237f-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="4237f-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
