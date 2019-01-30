---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: caf5be7aaff0df436be3a1d618a9f89bb32e6bb7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254846"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="26d3a-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="26d3a-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="26d3a-102">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="26d3a-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="26d3a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26d3a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="26d3a-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="26d3a-104">\<behaviors></span></span>  
<span data-ttu-id="26d3a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="26d3a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="26d3a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="26d3a-106">\<behavior></span></span>  
<span data-ttu-id="26d3a-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="26d3a-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d3a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="26d3a-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26d3a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26d3a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26d3a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26d3a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26d3a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="26d3a-111">Attributes</span></span>  
  
|<span data-ttu-id="26d3a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="26d3a-112">Attribute</span></span>|<span data-ttu-id="26d3a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26d3a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26d3a-114">action</span><span class="sxs-lookup"><span data-stu-id="26d3a-114">action</span></span>|<span data-ttu-id="26d3a-115">Eine Zeichenfolge, die die Aktion angibt, die ausgeführt wird, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="26d3a-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="26d3a-116">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="26d3a-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26d3a-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26d3a-117">Child Elements</span></span>  
 <span data-ttu-id="26d3a-118">Keine</span><span class="sxs-lookup"><span data-stu-id="26d3a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26d3a-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26d3a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="26d3a-120">Element</span><span class="sxs-lookup"><span data-stu-id="26d3a-120">Element</span></span>|<span data-ttu-id="26d3a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26d3a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26d3a-122">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="26d3a-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="26d3a-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="26d3a-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26d3a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26d3a-124">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
