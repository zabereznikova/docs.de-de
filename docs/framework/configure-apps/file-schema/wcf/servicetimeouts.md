---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075521"
---
# <a name="servicetimeouts"></a><span data-ttu-id="7236c-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="7236c-101">\<serviceTimeouts></span></span>
<span data-ttu-id="7236c-102">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="7236c-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="7236c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7236c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7236c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7236c-104">\<behaviors></span></span>  
<span data-ttu-id="7236c-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7236c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="7236c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7236c-106">\<behavior></span></span>  
<span data-ttu-id="7236c-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="7236c-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7236c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7236c-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="7236c-109">Typ</span><span class="sxs-lookup"><span data-stu-id="7236c-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7236c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7236c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7236c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7236c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7236c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7236c-112">Attributes</span></span>  
  
|<span data-ttu-id="7236c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7236c-113">Attribute</span></span>|<span data-ttu-id="7236c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7236c-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="7236c-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="7236c-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="7236c-116">Der Standardwert ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="7236c-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7236c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7236c-117">Child Elements</span></span>  
 <span data-ttu-id="7236c-118">Keine</span><span class="sxs-lookup"><span data-stu-id="7236c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7236c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7236c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7236c-120">Element</span><span class="sxs-lookup"><span data-stu-id="7236c-120">Element</span></span>|<span data-ttu-id="7236c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7236c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7236c-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7236c-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7236c-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="7236c-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7236c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7236c-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
