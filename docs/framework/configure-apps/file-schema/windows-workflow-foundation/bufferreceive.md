---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 16d4546bce461b55695e0deed093396ce1c2b0b6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189564"
---
# \<bufferReceive>

<span data-ttu-id="616c0-101">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="616c0-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="616c0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="616c0-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="616c0-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="616c0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="616c0-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="616c0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="616c0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="616c0-105">Attributes</span></span>  
  
|<span data-ttu-id="616c0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="616c0-106">Attribute</span></span>|<span data-ttu-id="616c0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="616c0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="616c0-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="616c0-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="616c0-109">Eine ganze Zahl, die die maximale Anzahl der für jeden Channel zugelassenen ausstehenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="616c0-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="616c0-110">Der Standardwert ist 512.</span><span class="sxs-lookup"><span data-stu-id="616c0-110">The default value is 512.</span></span> <span data-ttu-id="616c0-111">Diese Eigenschaft schränkt die Anzahl von nicht in der richtigen Reihenfolge vorliegenden Meldungen ein, die von einem Workflowdienst empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="616c0-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="616c0-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="616c0-112">Child Elements</span></span>  

 <span data-ttu-id="616c0-113">Keine</span><span class="sxs-lookup"><span data-stu-id="616c0-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="616c0-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="616c0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="616c0-115">Element</span><span class="sxs-lookup"><span data-stu-id="616c0-115">Element</span></span>|<span data-ttu-id="616c0-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="616c0-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="616c0-117">\<behavior> von \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="616c0-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="616c0-118">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="616c0-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="616c0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="616c0-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
