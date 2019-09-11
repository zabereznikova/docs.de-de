---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855212"
---
# <a name="host"></a><span data-ttu-id="d7458-101">\<Host ></span><span class="sxs-lookup"><span data-stu-id="d7458-101">\<host></span></span>
<span data-ttu-id="d7458-102">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="d7458-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="d7458-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d7458-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d7458-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d7458-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d7458-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienste >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="d7458-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="d7458-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienst >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="d7458-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="d7458-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Host >**</span><span class="sxs-lookup"><span data-stu-id="d7458-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7458-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7458-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="d7458-109">Typ</span><span class="sxs-lookup"><span data-stu-id="d7458-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7458-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d7458-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d7458-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7458-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7458-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d7458-112">Attributes</span></span>  
 <span data-ttu-id="d7458-113">Keine</span><span class="sxs-lookup"><span data-stu-id="d7458-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7458-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7458-114">Child Elements</span></span>  
  
|<span data-ttu-id="d7458-115">Element</span><span class="sxs-lookup"><span data-stu-id="d7458-115">Element</span></span>|<span data-ttu-id="d7458-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7458-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7458-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="d7458-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="d7458-118">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="d7458-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="d7458-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="d7458-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="d7458-120">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="d7458-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7458-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7458-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d7458-122">Element</span><span class="sxs-lookup"><span data-stu-id="d7458-122">Element</span></span>|<span data-ttu-id="d7458-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7458-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7458-124">\<service></span><span class="sxs-lookup"><span data-stu-id="d7458-124">\<service></span></span>](service.md)|<span data-ttu-id="d7458-125">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="d7458-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7458-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7458-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="d7458-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="d7458-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
