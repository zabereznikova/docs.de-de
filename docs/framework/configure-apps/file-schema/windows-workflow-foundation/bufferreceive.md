---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398832"
---
# \<bufferReceive>
<span data-ttu-id="65d15-101">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="65d15-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="65d15-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="65d15-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65d15-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="65d15-103">Attributes and Elements</span></span>  
 <span data-ttu-id="65d15-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65d15-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65d15-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="65d15-105">Attributes</span></span>  
  
|<span data-ttu-id="65d15-106">attribute</span><span class="sxs-lookup"><span data-stu-id="65d15-106">Attribute</span></span>|<span data-ttu-id="65d15-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="65d15-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65d15-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="65d15-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="65d15-109">Eine ganze Zahl, die die maximale Anzahl der für jeden Channel zugelassenen ausstehenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="65d15-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="65d15-110">Der Standardwert ist 512.</span><span class="sxs-lookup"><span data-stu-id="65d15-110">The default value is 512.</span></span> <span data-ttu-id="65d15-111">Diese Eigenschaft schränkt die Anzahl von nicht in der richtigen Reihenfolge vorliegenden Meldungen ein, die von einem Workflowdienst empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="65d15-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65d15-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65d15-112">Child Elements</span></span>  
 <span data-ttu-id="65d15-113">Keine</span><span class="sxs-lookup"><span data-stu-id="65d15-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65d15-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65d15-114">Parent Elements</span></span>  
  
|<span data-ttu-id="65d15-115">Element</span><span class="sxs-lookup"><span data-stu-id="65d15-115">Element</span></span>|<span data-ttu-id="65d15-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65d15-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65d15-117">\<behavior>Natürlich\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="65d15-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="65d15-118">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="65d15-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65d15-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65d15-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
