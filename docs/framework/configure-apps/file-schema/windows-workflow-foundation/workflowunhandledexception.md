---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: d9db6ecc2e95e0d1ec5738f1d2f4a09a89c57f21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755135"
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="1c1ad-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="1c1ad-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="1c1ad-103">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="1c1ad-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="1c1ad-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1c1ad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c1ad-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1c1ad-105">\<behaviors></span></span>  
<span data-ttu-id="1c1ad-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1c1ad-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1c1ad-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="1c1ad-107">\<behavior></span></span>  
<span data-ttu-id="1c1ad-108">\<WorkflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="1c1ad-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c1ad-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c1ad-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c1ad-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1c1ad-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1c1ad-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1c1ad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c1ad-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c1ad-112">Attributes</span></span>  
  
|<span data-ttu-id="1c1ad-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1c1ad-113">Attribute</span></span>|<span data-ttu-id="1c1ad-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c1ad-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c1ad-115">action</span><span class="sxs-lookup"><span data-stu-id="1c1ad-115">action</span></span>|<span data-ttu-id="1c1ad-116">Eine Zeichenfolge, die die Aktion angibt, die ausgeführt wird, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="1c1ad-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="1c1ad-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="1c1ad-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c1ad-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c1ad-118">Child Elements</span></span>  
 <span data-ttu-id="1c1ad-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1c1ad-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c1ad-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c1ad-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1c1ad-121">Element</span><span class="sxs-lookup"><span data-stu-id="1c1ad-121">Element</span></span>|<span data-ttu-id="1c1ad-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c1ad-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c1ad-123">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1c1ad-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1c1ad-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="1c1ad-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c1ad-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c1ad-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
