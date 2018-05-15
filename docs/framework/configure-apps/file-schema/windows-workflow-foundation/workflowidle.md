---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 65bcc1ccd357fb7f331665aefbd975b11a2378cd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="30408-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="30408-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="30408-103">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="30408-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="30408-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="30408-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="30408-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="30408-105">\<behaviors></span></span>  
<span data-ttu-id="30408-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="30408-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="30408-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="30408-107">\<behavior></span></span>  
<span data-ttu-id="30408-108">\<WorkflowIdle ></span><span class="sxs-lookup"><span data-stu-id="30408-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30408-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="30408-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30408-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30408-110">Attributes and Elements</span></span>  
 <span data-ttu-id="30408-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30408-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30408-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="30408-112">Attributes</span></span>  
  
|<span data-ttu-id="30408-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="30408-113">Attribute</span></span>|<span data-ttu-id="30408-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30408-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30408-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="30408-115">timeToPersist</span></span>|<span data-ttu-id="30408-116">Ein Timespan-Wert, der die Dauer zwischen dem Zeitpunkt angibt, der Workflow in den Leerlauf und wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="30408-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="30408-117">Der Standardwert ist TimeSpan.MaxValue an.</span><span class="sxs-lookup"><span data-stu-id="30408-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="30408-118">Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="30408-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="30408-119">Dieses Attribut ist hilfreich, wenn eine Workflowinstanz, die genauer gleichzeitig die Instanz für solange wie möglich im Arbeitsspeicher beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="30408-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="30408-120">Dieses Attribut ist nur gültig, wenn der Wert ist kleiner als das **TimeToUnload** Attribut.</span><span class="sxs-lookup"><span data-stu-id="30408-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="30408-121">Ist er größer, wird das Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="30408-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="30408-122">Wenn dieses Attribut, bevor der Wert verstreicht von der **TimeToUnload** -Attribut, Persistenz muss abgeschlossen werden, bevor der Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="30408-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="30408-123">Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="30408-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="30408-124">Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="30408-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="30408-125">Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="30408-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="30408-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="30408-126">timeToUnload</span></span>|<span data-ttu-id="30408-127">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="30408-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="30408-128">Der Standardwert beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="30408-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="30408-129">Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="30408-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="30408-130">Wenn dieses Attribut auf 0 (null) festgelegt ist, die Workflowinstanz beibehalten und entladen, unmittelbar nach, wird der Workflow im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="30408-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="30408-131">Durch Festlegen dieses Attributs auf TimeSpan.MaxValue effektiv deaktiviert der Entladevorgang.</span><span class="sxs-lookup"><span data-stu-id="30408-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="30408-132">Workflowinstanzen im Leerlauf werden nie entladen.</span><span class="sxs-lookup"><span data-stu-id="30408-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30408-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30408-133">Child Elements</span></span>  
 <span data-ttu-id="30408-134">Keine</span><span class="sxs-lookup"><span data-stu-id="30408-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30408-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30408-135">Parent Elements</span></span>  
  
|<span data-ttu-id="30408-136">Element</span><span class="sxs-lookup"><span data-stu-id="30408-136">Element</span></span>|<span data-ttu-id="30408-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30408-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30408-138">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="30408-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="30408-139">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="30408-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30408-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30408-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
