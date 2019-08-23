---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 1d4611d6fee9dad057985f7d8f5ef961d384efcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945975"
---
# <a name="bufferreceive"></a><span data-ttu-id="2be01-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="2be01-101">\<bufferReceive></span></span>
<span data-ttu-id="2be01-102">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="2be01-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="2be01-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2be01-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2be01-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2be01-104">\<behaviors></span></span>  
<span data-ttu-id="2be01-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2be01-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2be01-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2be01-106">\<behavior></span></span>  
<span data-ttu-id="2be01-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="2be01-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be01-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2be01-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2be01-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2be01-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2be01-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2be01-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2be01-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2be01-111">Attributes</span></span>  
  
|<span data-ttu-id="2be01-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2be01-112">Attribute</span></span>|<span data-ttu-id="2be01-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2be01-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2be01-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="2be01-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="2be01-115">Eine ganze Zahl, die die maximale Anzahl der für jeden Channel zugelassenen ausstehenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="2be01-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="2be01-116">Der Standardwert ist 512.</span><span class="sxs-lookup"><span data-stu-id="2be01-116">The default value is 512.</span></span> <span data-ttu-id="2be01-117">Diese Eigenschaft schränkt die Anzahl von nicht in der richtigen Reihenfolge vorliegenden Meldungen ein, die von einem Workflowdienst empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="2be01-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2be01-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2be01-118">Child Elements</span></span>  
 <span data-ttu-id="2be01-119">Keine</span><span class="sxs-lookup"><span data-stu-id="2be01-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2be01-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2be01-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2be01-121">Element</span><span class="sxs-lookup"><span data-stu-id="2be01-121">Element</span></span>|<span data-ttu-id="2be01-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2be01-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2be01-123">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="2be01-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2be01-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2be01-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2be01-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2be01-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
