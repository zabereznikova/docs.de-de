---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 07d5b66b14d9495808f972734cdce4476efaefde
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="024a4-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="024a4-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="024a4-103">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="024a4-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="024a4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="024a4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="024a4-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="024a4-105">\<behaviors></span></span>  
<span data-ttu-id="024a4-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="024a4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="024a4-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="024a4-107">\<behavior></span></span>  
<span data-ttu-id="024a4-108">\<BufferReceive ></span><span class="sxs-lookup"><span data-stu-id="024a4-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024a4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="024a4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="024a4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="024a4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="024a4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="024a4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="024a4-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="024a4-112">Attributes</span></span>  
  
|<span data-ttu-id="024a4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="024a4-113">Attribute</span></span>|<span data-ttu-id="024a4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="024a4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="024a4-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="024a4-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="024a4-116">Eine ganze Zahl, die die maximale Anzahl der für jeden Channel zugelassenen ausstehenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="024a4-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="024a4-117">Der Standardwert ist 512.</span><span class="sxs-lookup"><span data-stu-id="024a4-117">The default value is 512.</span></span> <span data-ttu-id="024a4-118">Diese Eigenschaft schränkt die Anzahl von nicht in der richtigen Reihenfolge vorliegenden Meldungen ein, die von einem Workflowdienst empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="024a4-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="024a4-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="024a4-119">Child Elements</span></span>  
 <span data-ttu-id="024a4-120">Keine</span><span class="sxs-lookup"><span data-stu-id="024a4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="024a4-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="024a4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="024a4-122">Element</span><span class="sxs-lookup"><span data-stu-id="024a4-122">Element</span></span>|<span data-ttu-id="024a4-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="024a4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="024a4-124">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="024a4-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="024a4-125">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="024a4-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="024a4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="024a4-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
