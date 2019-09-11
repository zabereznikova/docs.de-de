---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850211"
---
# <a name="baseaddresses"></a><span data-ttu-id="33cb1-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="33cb1-101">\<baseAddresses></span></span>
<span data-ttu-id="33cb1-102">Stellt eine Auflistung von `baseAddress`-Elementen dar, bei denen es sich um Basisadressen für einen Diensthost in einer selbst gehosteten Umgebung handelt.</span><span class="sxs-lookup"><span data-stu-id="33cb1-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="33cb1-103">Wenn eine Basisadresse vorhanden ist, können Endpunkte mit Adressen relativ zur Basisadresse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="33cb1-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="33cb1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33cb1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33cb1-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33cb1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33cb1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienste >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="33cb1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="33cb1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienst >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="33cb1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="33cb1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Host >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="33cb1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="33cb1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<baseadressen->**</span><span class="sxs-lookup"><span data-stu-id="33cb1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cb1-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="33cb1-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="33cb1-111">Typ</span><span class="sxs-lookup"><span data-stu-id="33cb1-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33cb1-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="33cb1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="33cb1-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="33cb1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33cb1-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="33cb1-114">Attributes</span></span>  
 <span data-ttu-id="33cb1-115">Keine</span><span class="sxs-lookup"><span data-stu-id="33cb1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33cb1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33cb1-116">Child Elements</span></span>  
  
|<span data-ttu-id="33cb1-117">Element</span><span class="sxs-lookup"><span data-stu-id="33cb1-117">Element</span></span>|<span data-ttu-id="33cb1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33cb1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33cb1-119">\<add></span><span class="sxs-lookup"><span data-stu-id="33cb1-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="33cb1-120">Ein Konfigurationselement, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="33cb1-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33cb1-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33cb1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="33cb1-122">Element</span><span class="sxs-lookup"><span data-stu-id="33cb1-122">Element</span></span>|<span data-ttu-id="33cb1-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33cb1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33cb1-124">\<host></span><span class="sxs-lookup"><span data-stu-id="33cb1-124">\<host></span></span>](host.md)|<span data-ttu-id="33cb1-125">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="33cb1-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33cb1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33cb1-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="33cb1-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="33cb1-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
