---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 8a8a352380fe6eedb41ead089405e7b79fad29fe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272774"
---
# <a name="timeouts"></a><span data-ttu-id="e031a-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="e031a-101">\<timeOuts></span></span>
<span data-ttu-id="e031a-102">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="e031a-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="e031a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e031a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e031a-104">\<client></span><span class="sxs-lookup"><span data-stu-id="e031a-104">\<client></span></span>  
<span data-ttu-id="e031a-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e031a-105">\<endpoint></span></span>  
<span data-ttu-id="e031a-106">\<host></span><span class="sxs-lookup"><span data-stu-id="e031a-106">\<host></span></span>  
<span data-ttu-id="e031a-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="e031a-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e031a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e031a-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e031a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e031a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e031a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e031a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e031a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e031a-111">Attributes</span></span>  
  
|<span data-ttu-id="e031a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e031a-112">Attribute</span></span>|<span data-ttu-id="e031a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e031a-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e031a-114">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="e031a-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="e031a-115">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="e031a-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e031a-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e031a-116">Child Elements</span></span>  
 <span data-ttu-id="e031a-117">Keine</span><span class="sxs-lookup"><span data-stu-id="e031a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e031a-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e031a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e031a-119">Element</span><span class="sxs-lookup"><span data-stu-id="e031a-119">Element</span></span>|<span data-ttu-id="e031a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e031a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e031a-121">\<host></span><span class="sxs-lookup"><span data-stu-id="e031a-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e031a-122">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="e031a-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e031a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e031a-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="e031a-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="e031a-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
