---
title: '&lt;BaseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 0af5dee41c6adf560c90874e6e9a44b62c5decc6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147355"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="9effd-102">&lt;BaseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="9effd-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="9effd-103">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="9effd-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="9effd-104">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9effd-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="9effd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9effd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9effd-106">\<Client ></span><span class="sxs-lookup"><span data-stu-id="9effd-106">\<client></span></span>  
<span data-ttu-id="9effd-107">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="9effd-107">\<endpoint></span></span>  
<span data-ttu-id="9effd-108">\<Host ></span><span class="sxs-lookup"><span data-stu-id="9effd-108">\<host></span></span>  
<span data-ttu-id="9effd-109">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="9effd-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9effd-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9effd-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="9effd-111">Typ</span><span class="sxs-lookup"><span data-stu-id="9effd-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9effd-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9effd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9effd-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9effd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9effd-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="9effd-114">Attributes</span></span>  
 <span data-ttu-id="9effd-115">Keine</span><span class="sxs-lookup"><span data-stu-id="9effd-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9effd-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9effd-116">Child Elements</span></span>  
  
|<span data-ttu-id="9effd-117">Element</span><span class="sxs-lookup"><span data-stu-id="9effd-117">Element</span></span>|<span data-ttu-id="9effd-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9effd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9effd-119">\<add></span><span class="sxs-lookup"><span data-stu-id="9effd-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="9effd-120">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="9effd-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9effd-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9effd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9effd-122">Element</span><span class="sxs-lookup"><span data-stu-id="9effd-122">Element</span></span>|<span data-ttu-id="9effd-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9effd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9effd-124">\<Host ></span><span class="sxs-lookup"><span data-stu-id="9effd-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="9effd-125">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="9effd-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9effd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9effd-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="9effd-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="9effd-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
