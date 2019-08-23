---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939184"
---
# <a name="timeouts"></a><span data-ttu-id="91443-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="91443-101">\<timeOuts></span></span>
<span data-ttu-id="91443-102">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="91443-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="91443-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91443-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="91443-104">\<client></span><span class="sxs-lookup"><span data-stu-id="91443-104">\<client></span></span>  
<span data-ttu-id="91443-105">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="91443-105">\<endpoint></span></span>  
<span data-ttu-id="91443-106">\<Host ></span><span class="sxs-lookup"><span data-stu-id="91443-106">\<host></span></span>  
<span data-ttu-id="91443-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="91443-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91443-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="91443-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91443-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="91443-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91443-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91443-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91443-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="91443-111">Attributes</span></span>  
  
|<span data-ttu-id="91443-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="91443-112">Attribute</span></span>|<span data-ttu-id="91443-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91443-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="91443-114">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="91443-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="91443-115">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="91443-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91443-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91443-116">Child Elements</span></span>  
 <span data-ttu-id="91443-117">Keine</span><span class="sxs-lookup"><span data-stu-id="91443-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91443-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91443-118">Parent Elements</span></span>  
  
|<span data-ttu-id="91443-119">Element</span><span class="sxs-lookup"><span data-stu-id="91443-119">Element</span></span>|<span data-ttu-id="91443-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91443-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91443-121">\<host></span><span class="sxs-lookup"><span data-stu-id="91443-121">\<host></span></span>](host.md)|<span data-ttu-id="91443-122">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="91443-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91443-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91443-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="91443-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="91443-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
