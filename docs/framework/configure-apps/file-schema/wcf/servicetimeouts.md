---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: f7aa623ee387f67f3bbff32249d3695049359cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524467"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="a2302-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="a2302-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="a2302-103">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="a2302-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="a2302-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a2302-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2302-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a2302-105">\<behaviors></span></span>  
<span data-ttu-id="a2302-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a2302-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a2302-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a2302-107">\<behavior></span></span>  
<span data-ttu-id="a2302-108">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="a2302-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2302-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2302-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="a2302-110">Typ</span><span class="sxs-lookup"><span data-stu-id="a2302-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2302-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2302-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a2302-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2302-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2302-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2302-113">Attributes</span></span>  
  
|<span data-ttu-id="a2302-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="a2302-114">Attribute</span></span>|<span data-ttu-id="a2302-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2302-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="a2302-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="a2302-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="a2302-117">Der Standardwert ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="a2302-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2302-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2302-118">Child Elements</span></span>  
 <span data-ttu-id="a2302-119">Keine</span><span class="sxs-lookup"><span data-stu-id="a2302-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2302-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2302-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a2302-121">Element</span><span class="sxs-lookup"><span data-stu-id="a2302-121">Element</span></span>|<span data-ttu-id="a2302-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2302-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2302-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a2302-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a2302-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="a2302-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2302-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2302-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
