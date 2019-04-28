---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758222"
---
# <a name="timeouts"></a><span data-ttu-id="f98f8-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="f98f8-101">\<timeOuts></span></span>
<span data-ttu-id="f98f8-102">Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="f98f8-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="f98f8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f98f8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f98f8-104">\<client></span><span class="sxs-lookup"><span data-stu-id="f98f8-104">\<client></span></span>  
<span data-ttu-id="f98f8-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="f98f8-105">\<endpoint></span></span>  
<span data-ttu-id="f98f8-106">\<host></span><span class="sxs-lookup"><span data-stu-id="f98f8-106">\<host></span></span>  
<span data-ttu-id="f98f8-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="f98f8-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98f8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f98f8-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f98f8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f98f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f98f8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f98f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f98f8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f98f8-111">Attributes</span></span>  
  
|<span data-ttu-id="f98f8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="f98f8-112">Attribute</span></span>|<span data-ttu-id="f98f8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f98f8-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f98f8-114">Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="f98f8-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="f98f8-115">Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="f98f8-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f98f8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f98f8-116">Child Elements</span></span>  
 <span data-ttu-id="f98f8-117">Keine</span><span class="sxs-lookup"><span data-stu-id="f98f8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f98f8-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f98f8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f98f8-119">Element</span><span class="sxs-lookup"><span data-stu-id="f98f8-119">Element</span></span>|<span data-ttu-id="f98f8-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f98f8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f98f8-121">\<host></span><span class="sxs-lookup"><span data-stu-id="f98f8-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="f98f8-122">Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.</span><span class="sxs-lookup"><span data-stu-id="f98f8-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f98f8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f98f8-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="f98f8-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="f98f8-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
