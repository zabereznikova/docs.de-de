---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 4cb4b4ae6fe01430989d9ee5f3d94b16778595aa
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148473"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="d57fd-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="d57fd-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="d57fd-103">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="d57fd-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="d57fd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d57fd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d57fd-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d57fd-105">\<behaviors></span></span>  
<span data-ttu-id="d57fd-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d57fd-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d57fd-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d57fd-107">\<behavior></span></span>  
<span data-ttu-id="d57fd-108">\<ServiceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="d57fd-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d57fd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d57fd-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="d57fd-110">Typ</span><span class="sxs-lookup"><span data-stu-id="d57fd-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d57fd-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d57fd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d57fd-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d57fd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d57fd-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="d57fd-113">Attributes</span></span>  
  
|<span data-ttu-id="d57fd-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="d57fd-114">Attribute</span></span>|<span data-ttu-id="d57fd-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d57fd-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="d57fd-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="d57fd-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="d57fd-117">Der Standardwert ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="d57fd-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d57fd-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d57fd-118">Child Elements</span></span>  
 <span data-ttu-id="d57fd-119">Keine</span><span class="sxs-lookup"><span data-stu-id="d57fd-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d57fd-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d57fd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d57fd-121">Element</span><span class="sxs-lookup"><span data-stu-id="d57fd-121">Element</span></span>|<span data-ttu-id="d57fd-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d57fd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d57fd-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d57fd-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d57fd-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="d57fd-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d57fd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d57fd-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
