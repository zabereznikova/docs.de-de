---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151844"
---
# <a name="workflowidle"></a><span data-ttu-id="47b21-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="47b21-101">\<workflowIdle></span></span>
<span data-ttu-id="47b21-102">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="47b21-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="47b21-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47b21-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47b21-104">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="47b21-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="47b21-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="47b21-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="47b21-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="47b21-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="47b21-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="47b21-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="47b21-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span><span class="sxs-lookup"><span data-stu-id="47b21-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47b21-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="47b21-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47b21-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="47b21-110">Attributes and Elements</span></span>  
 <span data-ttu-id="47b21-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="47b21-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47b21-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="47b21-112">Attributes</span></span>  
  
|<span data-ttu-id="47b21-113">attribute</span><span class="sxs-lookup"><span data-stu-id="47b21-113">Attribute</span></span>|<span data-ttu-id="47b21-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47b21-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47b21-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="47b21-115">timeToPersist</span></span>|<span data-ttu-id="47b21-116">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="47b21-117">Der Standardwert ist TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="47b21-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="47b21-118">Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="47b21-119">Dieses Attribut ist nützlich, wenn eine Workflowinstanz auf aggressivere Weise beibehalten werden soll, während die Instanz solange als möglich im Speicher verbleiben soll.</span><span class="sxs-lookup"><span data-stu-id="47b21-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="47b21-120">Dieses Attribut ist nur gültig, wenn sein Wert kleiner als das **timeToUnload-Attribut** ist.</span><span class="sxs-lookup"><span data-stu-id="47b21-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="47b21-121">Ist er größer, wird das Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="47b21-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="47b21-122">Wenn dieses Attribut vor dem vom **TimeToUnload-Attribut** angegebenen Wert verstreicht, muss die Persistenz abgeschlossen sein, bevor der Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="47b21-123">Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="47b21-124">Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="47b21-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="47b21-125">Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="47b21-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="47b21-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="47b21-126">timeToUnload</span></span>|<span data-ttu-id="47b21-127">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="47b21-128">Der Standardwert beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="47b21-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="47b21-129">Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="47b21-130">Ist dieses Attribut auf 0 (null) festgelegt, wird die Workflowinstanz sofort beibehalten und entladen, nachdem der Workflow in den Leerlauf versetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="47b21-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="47b21-131">Der Entladevorgang wird deaktiviert, wenn dieses Attribut auf TimeSpan.MaxValue festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="47b21-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="47b21-132">Workflowinstanzen im Leerlauf werden nie entladen.</span><span class="sxs-lookup"><span data-stu-id="47b21-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47b21-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47b21-133">Child Elements</span></span>  
 <span data-ttu-id="47b21-134">Keine.</span><span class="sxs-lookup"><span data-stu-id="47b21-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47b21-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47b21-135">Parent Elements</span></span>  
  
|<span data-ttu-id="47b21-136">Element</span><span class="sxs-lookup"><span data-stu-id="47b21-136">Element</span></span>|<span data-ttu-id="47b21-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47b21-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47b21-138">\<Verhalten> \<von serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="47b21-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="47b21-139">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="47b21-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47b21-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47b21-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
