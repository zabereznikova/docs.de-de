---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 5c5dddc6d126811d7fd1eaae2f85df1e42c1cd41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700870"
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="4d806-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="4d806-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="4d806-103">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="4d806-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="4d806-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4d806-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d806-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4d806-105">\<behaviors></span></span>  
<span data-ttu-id="4d806-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4d806-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4d806-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4d806-107">\<behavior></span></span>  
<span data-ttu-id="4d806-108">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="4d806-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d806-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d806-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d806-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4d806-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d806-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d806-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d806-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="4d806-112">Attributes</span></span>  
  
|<span data-ttu-id="4d806-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="4d806-113">Attribute</span></span>|<span data-ttu-id="4d806-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d806-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d806-115">action</span><span class="sxs-lookup"><span data-stu-id="4d806-115">action</span></span>|<span data-ttu-id="4d806-116">Eine Zeichenfolge, die die Aktion angibt, die ausgeführt wird, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="4d806-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="4d806-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="4d806-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d806-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d806-118">Child Elements</span></span>  
 <span data-ttu-id="4d806-119">Keine</span><span class="sxs-lookup"><span data-stu-id="4d806-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d806-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d806-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4d806-121">Element</span><span class="sxs-lookup"><span data-stu-id="4d806-121">Element</span></span>|<span data-ttu-id="4d806-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d806-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d806-123">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4d806-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4d806-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="4d806-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d806-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d806-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
