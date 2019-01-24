---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 507d58f852544c0eadcefaf997b2345d5e123cfa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607513"
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="2f66c-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="2f66c-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="2f66c-103">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="2f66c-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="2f66c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2f66c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2f66c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2f66c-105">\<behaviors></span></span>  
<span data-ttu-id="2f66c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2f66c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2f66c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2f66c-107">\<behavior></span></span>  
<span data-ttu-id="2f66c-108">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="2f66c-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f66c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f66c-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f66c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f66c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2f66c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f66c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f66c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f66c-112">Attributes</span></span>  
  
|<span data-ttu-id="2f66c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2f66c-113">Attribute</span></span>|<span data-ttu-id="2f66c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f66c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f66c-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="2f66c-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="2f66c-116">Eine ganze Zahl, die die maximale Anzahl der für jeden Channel zugelassenen ausstehenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="2f66c-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="2f66c-117">Der Standardwert ist 512.</span><span class="sxs-lookup"><span data-stu-id="2f66c-117">The default value is 512.</span></span> <span data-ttu-id="2f66c-118">Diese Eigenschaft schränkt die Anzahl von nicht in der richtigen Reihenfolge vorliegenden Meldungen ein, die von einem Workflowdienst empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="2f66c-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f66c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f66c-119">Child Elements</span></span>  
 <span data-ttu-id="2f66c-120">Keine</span><span class="sxs-lookup"><span data-stu-id="2f66c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f66c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f66c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2f66c-122">Element</span><span class="sxs-lookup"><span data-stu-id="2f66c-122">Element</span></span>|<span data-ttu-id="2f66c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f66c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f66c-124">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2f66c-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2f66c-125">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2f66c-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f66c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f66c-126">See also</span></span>
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
