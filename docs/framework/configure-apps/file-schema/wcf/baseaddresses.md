---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926424"
---
# <a name="baseaddresses"></a><span data-ttu-id="936ae-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="936ae-101">\<baseAddresses></span></span>
<span data-ttu-id="936ae-102">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="936ae-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="936ae-103">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="936ae-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="936ae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="936ae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="936ae-105">\<client></span><span class="sxs-lookup"><span data-stu-id="936ae-105">\<client></span></span>  
<span data-ttu-id="936ae-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="936ae-106">\<endpoint></span></span>  
<span data-ttu-id="936ae-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="936ae-107">\<host></span></span>  
<span data-ttu-id="936ae-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="936ae-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936ae-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="936ae-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="936ae-110">Typ</span><span class="sxs-lookup"><span data-stu-id="936ae-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="936ae-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="936ae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="936ae-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="936ae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="936ae-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="936ae-113">Attributes</span></span>  
 <span data-ttu-id="936ae-114">Keine</span><span class="sxs-lookup"><span data-stu-id="936ae-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="936ae-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="936ae-115">Child Elements</span></span>  
  
|<span data-ttu-id="936ae-116">Element</span><span class="sxs-lookup"><span data-stu-id="936ae-116">Element</span></span>|<span data-ttu-id="936ae-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="936ae-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="936ae-118">\<add></span><span class="sxs-lookup"><span data-stu-id="936ae-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="936ae-119">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="936ae-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="936ae-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="936ae-120">Parent Elements</span></span>  
  
|<span data-ttu-id="936ae-121">Element</span><span class="sxs-lookup"><span data-stu-id="936ae-121">Element</span></span>|<span data-ttu-id="936ae-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="936ae-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="936ae-123">\<host></span><span class="sxs-lookup"><span data-stu-id="936ae-123">\<host></span></span>](host.md)|<span data-ttu-id="936ae-124">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="936ae-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="936ae-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="936ae-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="936ae-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="936ae-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
