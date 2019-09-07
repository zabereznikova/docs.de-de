---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1d8ddaf5d69d87ff6112b5cbb285f0ccfda724e2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397537"
---
# <a name="workflowidle"></a><span data-ttu-id="6928c-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="6928c-101">\<workflowIdle></span></span>
<span data-ttu-id="6928c-102">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="6928c-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="6928c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6928c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6928c-104">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6928c-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="6928c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6928c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="6928c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6928c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="6928c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6928c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="6928c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowidle->**</span><span class="sxs-lookup"><span data-stu-id="6928c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6928c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6928c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6928c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6928c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6928c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6928c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6928c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6928c-112">Attributes</span></span>  
  
|<span data-ttu-id="6928c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6928c-113">Attribute</span></span>|<span data-ttu-id="6928c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6928c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6928c-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="6928c-115">timeToPersist</span></span>|<span data-ttu-id="6928c-116">Ein TimeSpan-Wert, der die Dauer zwischen dem Zeitpunkt, zu dem der Workflow in den Leerlauf wechselt und persistent ist, angibt.</span><span class="sxs-lookup"><span data-stu-id="6928c-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="6928c-117">Der Standardwert ist TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="6928c-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="6928c-118">Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6928c-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="6928c-119">Dieses Attribut ist nützlich, wenn Sie eine Workflow Instanz aggressiver beibehalten möchten, während die Instanz so lange wie möglich im Arbeitsspeicher beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="6928c-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="6928c-120">Dieses Attribut ist nur gültig, wenn der Wert kleiner als das **Timeto** -Attribut ist.</span><span class="sxs-lookup"><span data-stu-id="6928c-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="6928c-121">Ist er größer, wird das Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6928c-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="6928c-122">Wenn dieses Attribut vor dem durch das **Timeto** -Attribut angegebenen Wert abläuft, muss die Persistenz vor dem Entladen des Workflows fertiggestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6928c-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="6928c-123">Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="6928c-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="6928c-124">Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="6928c-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="6928c-125">Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="6928c-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="6928c-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="6928c-126">timeToUnload</span></span>|<span data-ttu-id="6928c-127">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="6928c-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="6928c-128">Der Standardwert beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="6928c-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="6928c-129">Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="6928c-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="6928c-130">Wenn dieses Attribut auf 0 (null) festgelegt ist, wird die Workflow Instanz permanent gespeichert und entladen, sobald der Workflow in den Leerlauf wechselt.</span><span class="sxs-lookup"><span data-stu-id="6928c-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="6928c-131">Wenn dieses Attribut auf TimeSpan. MaxValue festgelegt wird, wird der Entladevorgang effektiv deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6928c-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="6928c-132">Workflowinstanzen im Leerlauf werden nie entladen.</span><span class="sxs-lookup"><span data-stu-id="6928c-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6928c-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6928c-133">Child Elements</span></span>  
 <span data-ttu-id="6928c-134">Keine</span><span class="sxs-lookup"><span data-stu-id="6928c-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6928c-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6928c-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6928c-136">Element</span><span class="sxs-lookup"><span data-stu-id="6928c-136">Element</span></span>|<span data-ttu-id="6928c-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6928c-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6928c-138">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="6928c-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="6928c-139">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="6928c-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6928c-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6928c-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
