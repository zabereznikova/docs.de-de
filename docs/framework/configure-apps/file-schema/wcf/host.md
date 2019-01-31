---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 8a8f9db96281d8d775ff5c2923018228b3a9c1e5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269028"
---
# <a name="host"></a><span data-ttu-id="6efe7-101">\<host></span><span class="sxs-lookup"><span data-stu-id="6efe7-101">\<host></span></span>
<span data-ttu-id="6efe7-102">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="6efe7-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="6efe7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6efe7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6efe7-104">\<services></span><span class="sxs-lookup"><span data-stu-id="6efe7-104">\<services></span></span>  
<span data-ttu-id="6efe7-105">\<service></span><span class="sxs-lookup"><span data-stu-id="6efe7-105">\<service></span></span>  
<span data-ttu-id="6efe7-106">\<host></span><span class="sxs-lookup"><span data-stu-id="6efe7-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6efe7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6efe7-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="6efe7-108">Typ</span><span class="sxs-lookup"><span data-stu-id="6efe7-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6efe7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6efe7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6efe7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6efe7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6efe7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6efe7-111">Attributes</span></span>  
 <span data-ttu-id="6efe7-112">Keine</span><span class="sxs-lookup"><span data-stu-id="6efe7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6efe7-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6efe7-113">Child Elements</span></span>  
  
|<span data-ttu-id="6efe7-114">Element</span><span class="sxs-lookup"><span data-stu-id="6efe7-114">Element</span></span>|<span data-ttu-id="6efe7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6efe7-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6efe7-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6efe7-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="6efe7-117">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="6efe7-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="6efe7-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="6efe7-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="6efe7-119">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="6efe7-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6efe7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6efe7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6efe7-121">Element</span><span class="sxs-lookup"><span data-stu-id="6efe7-121">Element</span></span>|<span data-ttu-id="6efe7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6efe7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6efe7-123">\<service></span><span class="sxs-lookup"><span data-stu-id="6efe7-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="6efe7-124">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="6efe7-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6efe7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6efe7-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="6efe7-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="6efe7-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
