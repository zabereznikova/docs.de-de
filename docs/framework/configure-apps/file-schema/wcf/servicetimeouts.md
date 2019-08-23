---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: a1792fec4f86c9ac31107c043b976cfafcfa4c13
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937091"
---
# <a name="servicetimeouts"></a><span data-ttu-id="4f572-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="4f572-101">\<serviceTimeouts></span></span>
<span data-ttu-id="4f572-102">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="4f572-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="4f572-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4f572-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f572-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4f572-104">\<behaviors></span></span>  
<span data-ttu-id="4f572-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4f572-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4f572-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4f572-106">\<behavior></span></span>  
<span data-ttu-id="4f572-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="4f572-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f572-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f572-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="4f572-109">Typ</span><span class="sxs-lookup"><span data-stu-id="4f572-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f572-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f572-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f572-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f572-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f572-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f572-112">Attributes</span></span>  
  
|<span data-ttu-id="4f572-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="4f572-113">Attribute</span></span>|<span data-ttu-id="4f572-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f572-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="4f572-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="4f572-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="4f572-116">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="4f572-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f572-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f572-117">Child Elements</span></span>  
 <span data-ttu-id="4f572-118">Keine</span><span class="sxs-lookup"><span data-stu-id="4f572-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f572-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f572-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4f572-120">Element</span><span class="sxs-lookup"><span data-stu-id="4f572-120">Element</span></span>|<span data-ttu-id="4f572-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f572-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f572-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4f572-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4f572-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="4f572-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f572-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f572-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
