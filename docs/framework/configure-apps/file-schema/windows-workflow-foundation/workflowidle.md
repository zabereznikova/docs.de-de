---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947162"
---
# <a name="workflowidle"></a><span data-ttu-id="5c833-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="5c833-101">\<workflowIdle></span></span>
<span data-ttu-id="5c833-102">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="5c833-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="5c833-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5c833-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c833-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5c833-104">\<behaviors></span></span>  
<span data-ttu-id="5c833-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5c833-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5c833-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5c833-106">\<behavior></span></span>  
<span data-ttu-id="5c833-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="5c833-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c833-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c833-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c833-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c833-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5c833-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c833-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c833-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c833-111">Attributes</span></span>  
  
|<span data-ttu-id="5c833-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="5c833-112">Attribute</span></span>|<span data-ttu-id="5c833-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c833-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c833-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="5c833-114">timeToPersist</span></span>|<span data-ttu-id="5c833-115">Ein TimeSpan-Wert, der die Dauer zwischen dem Zeitpunkt, zu dem der Workflow in den Leerlauf wechselt und persistent ist, angibt.</span><span class="sxs-lookup"><span data-stu-id="5c833-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="5c833-116">Der Standardwert ist TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="5c833-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="5c833-117">Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="5c833-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="5c833-118">Dieses Attribut ist nützlich, wenn Sie eine Workflow Instanz aggressiver beibehalten möchten, während die Instanz so lange wie möglich im Arbeitsspeicher beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="5c833-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="5c833-119">Dieses Attribut ist nur gültig, wenn der Wert kleiner als das **Timeto** -Attribut ist.</span><span class="sxs-lookup"><span data-stu-id="5c833-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="5c833-120">Ist er größer, wird das Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5c833-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="5c833-121">Wenn dieses Attribut vor dem durch das **Timeto** -Attribut angegebenen Wert abläuft, muss die Persistenz vor dem Entladen des Workflows fertiggestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5c833-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="5c833-122">Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="5c833-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="5c833-123">Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="5c833-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="5c833-124">Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5c833-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="5c833-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="5c833-125">timeToUnload</span></span>|<span data-ttu-id="5c833-126">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="5c833-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="5c833-127">Der Standardwert beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="5c833-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="5c833-128">Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="5c833-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="5c833-129">Wenn dieses Attribut auf 0 (null) festgelegt ist, wird die Workflow Instanz permanent gespeichert und entladen, sobald der Workflow in den Leerlauf wechselt.</span><span class="sxs-lookup"><span data-stu-id="5c833-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="5c833-130">Wenn dieses Attribut auf TimeSpan. MaxValue festgelegt wird, wird der Entladevorgang effektiv deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5c833-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="5c833-131">Workflowinstanzen im Leerlauf werden nie entladen.</span><span class="sxs-lookup"><span data-stu-id="5c833-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c833-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c833-132">Child Elements</span></span>  
 <span data-ttu-id="5c833-133">Keine</span><span class="sxs-lookup"><span data-stu-id="5c833-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c833-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c833-134">Parent Elements</span></span>  
  
|<span data-ttu-id="5c833-135">Element</span><span class="sxs-lookup"><span data-stu-id="5c833-135">Element</span></span>|<span data-ttu-id="5c833-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c833-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c833-137">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="5c833-137">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5c833-138">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="5c833-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c833-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c833-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
