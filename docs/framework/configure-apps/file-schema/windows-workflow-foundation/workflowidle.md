---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1dc186f5899935dab43c0d33894e659c4b19748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201116"
---
# <a name="workflowidle"></a><span data-ttu-id="06290-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="06290-101">\<workflowIdle></span></span>
<span data-ttu-id="06290-102">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="06290-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="06290-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06290-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="06290-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="06290-104">\<behaviors></span></span>  
<span data-ttu-id="06290-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="06290-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="06290-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="06290-106">\<behavior></span></span>  
<span data-ttu-id="06290-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="06290-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06290-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="06290-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06290-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="06290-109">Attributes and Elements</span></span>  
 <span data-ttu-id="06290-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06290-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06290-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="06290-111">Attributes</span></span>  
  
|<span data-ttu-id="06290-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="06290-112">Attribute</span></span>|<span data-ttu-id="06290-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06290-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06290-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="06290-114">timeToPersist</span></span>|<span data-ttu-id="06290-115">Ein Timespan-Wert gibt an, dass die Dauer zwischen dem Zeitpunkt der Workflow in den Leerlauf und wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="06290-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="06290-116">Der Standardwert ist TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="06290-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="06290-117">Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="06290-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="06290-118">Dieses Attribut ist nützlich, wenn eine Workflowinstanz, die aggressiver und dennoch die Sicherheit der Instanz für die so lange wie möglich im Arbeitsspeicher beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="06290-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="06290-119">Dieses Attribut ist nur gültig, wenn der Wert ist kleiner als der **TimeToUnload** Attribut.</span><span class="sxs-lookup"><span data-stu-id="06290-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="06290-120">Ist er größer, wird das Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="06290-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="06290-121">Wenn dieses Attribut, bevor der Wert abläuft von der **TimeToUnload** -Attribut muss die Beibehaltung abgeschlossen, bevor der Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="06290-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="06290-122">Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="06290-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="06290-123">Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="06290-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="06290-124">Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="06290-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="06290-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="06290-125">timeToUnload</span></span>|<span data-ttu-id="06290-126">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="06290-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="06290-127">Der Standardwert beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="06290-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="06290-128">Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="06290-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="06290-129">Wenn dieses Attribut auf 0 (null) festgelegt ist, die Workflowinstanz beibehalten und entladen, unmittelbar, in den Leerlauf des Workflows.</span><span class="sxs-lookup"><span data-stu-id="06290-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="06290-130">Wenn dieses Attribut auf TimeSpan.MaxValue festgelegt effektiv deaktiviert der Entladevorgang.</span><span class="sxs-lookup"><span data-stu-id="06290-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="06290-131">Workflowinstanzen im Leerlauf werden nie entladen.</span><span class="sxs-lookup"><span data-stu-id="06290-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06290-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06290-132">Child Elements</span></span>  
 <span data-ttu-id="06290-133">Keine</span><span class="sxs-lookup"><span data-stu-id="06290-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06290-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06290-134">Parent Elements</span></span>  
  
|<span data-ttu-id="06290-135">Element</span><span class="sxs-lookup"><span data-stu-id="06290-135">Element</span></span>|<span data-ttu-id="06290-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06290-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06290-137">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="06290-137">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="06290-138">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="06290-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06290-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06290-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
