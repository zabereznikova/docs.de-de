---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398832"
---
# <a name="bufferreceive"></a><span data-ttu-id="5d5a2-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="5d5a2-101">\<bufferReceive></span></span>
<span data-ttu-id="5d5a2-102">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="5d5a2-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="5d5a2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d5a2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d5a2-104">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d5a2-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5d5a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d5a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="5d5a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d5a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="5d5a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d5a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="5d5a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bufferreceive->**</span><span class="sxs-lookup"><span data-stu-id="5d5a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5a2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d5a2-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d5a2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d5a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d5a2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d5a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d5a2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5d5a2-112">Attributes</span></span>  
  
|<span data-ttu-id="5d5a2-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5d5a2-113">Attribute</span></span>|<span data-ttu-id="5d5a2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d5a2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d5a2-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="5d5a2-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="5d5a2-116">Eine ganze Zahl, die die maximale Anzahl der für jeden Channel zugelassenen ausstehenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="5d5a2-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="5d5a2-117">Der Standardwert ist 512.</span><span class="sxs-lookup"><span data-stu-id="5d5a2-117">The default value is 512.</span></span> <span data-ttu-id="5d5a2-118">Diese Eigenschaft schränkt die Anzahl von nicht in der richtigen Reihenfolge vorliegenden Meldungen ein, die von einem Workflowdienst empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="5d5a2-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d5a2-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d5a2-119">Child Elements</span></span>  
 <span data-ttu-id="5d5a2-120">Keine</span><span class="sxs-lookup"><span data-stu-id="5d5a2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d5a2-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d5a2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5d5a2-122">Element</span><span class="sxs-lookup"><span data-stu-id="5d5a2-122">Element</span></span>|<span data-ttu-id="5d5a2-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d5a2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d5a2-124">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="5d5a2-124">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5d5a2-125">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="5d5a2-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d5a2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d5a2-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
