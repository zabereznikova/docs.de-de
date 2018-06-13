---
title: '&lt;Host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: ec53568e9d1df9ebb04bc299f491e80674950c63
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233729"
---
# <a name="lthostgt"></a><span data-ttu-id="0e654-102">&lt;Host&gt;</span><span class="sxs-lookup"><span data-stu-id="0e654-102">&lt;host&gt;</span></span>
<span data-ttu-id="0e654-103">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="0e654-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="0e654-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e654-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e654-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="0e654-105">\<services></span></span>  
<span data-ttu-id="0e654-106">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="0e654-106">\<service></span></span>  
<span data-ttu-id="0e654-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="0e654-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e654-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e654-108">Syntax</span></span>  
  
```xml  
<host>
    <baseAddresses>  
        <add baseAddress="string" />  
    </baseAddresses>  
    <timeOuts closeTimeout="TimeSpan" openTimeout="TimeSpan">  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="0e654-109">Typ</span><span class="sxs-lookup"><span data-stu-id="0e654-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e654-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e654-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0e654-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e654-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e654-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e654-112">Attributes</span></span>  
 <span data-ttu-id="0e654-113">Keine</span><span class="sxs-lookup"><span data-stu-id="0e654-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e654-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e654-114">Child Elements</span></span>  
  
|<span data-ttu-id="0e654-115">Element</span><span class="sxs-lookup"><span data-stu-id="0e654-115">Element</span></span>|<span data-ttu-id="0e654-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e654-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e654-117">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="0e654-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="0e654-118">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="0e654-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="0e654-119">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="0e654-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="0e654-120">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="0e654-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e654-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e654-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0e654-122">Element</span><span class="sxs-lookup"><span data-stu-id="0e654-122">Element</span></span>|<span data-ttu-id="0e654-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e654-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e654-124">\<service></span><span class="sxs-lookup"><span data-stu-id="0e654-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="0e654-125">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="0e654-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e654-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e654-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="0e654-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="0e654-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
