---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854966"
---
# <a name="timeouts"></a><span data-ttu-id="a814c-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="a814c-101">\<timeOuts></span></span>
<span data-ttu-id="a814c-102">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="a814c-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="a814c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a814c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a814c-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a814c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a814c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienste >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="a814c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="a814c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Dienst >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="a814c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="a814c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Host >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="a814c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="a814c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Timeouts >**</span><span class="sxs-lookup"><span data-stu-id="a814c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a814c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a814c-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a814c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a814c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a814c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a814c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a814c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a814c-112">Attributes</span></span>  
  
|<span data-ttu-id="a814c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a814c-113">Attribute</span></span>|<span data-ttu-id="a814c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a814c-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a814c-115">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="a814c-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="a814c-116">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="a814c-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a814c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a814c-117">Child Elements</span></span>  
 <span data-ttu-id="a814c-118">Keine</span><span class="sxs-lookup"><span data-stu-id="a814c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a814c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a814c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a814c-120">Element</span><span class="sxs-lookup"><span data-stu-id="a814c-120">Element</span></span>|<span data-ttu-id="a814c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a814c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a814c-122">\<host></span><span class="sxs-lookup"><span data-stu-id="a814c-122">\<host></span></span>](host.md)|<span data-ttu-id="a814c-123">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="a814c-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a814c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a814c-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="a814c-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="a814c-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
