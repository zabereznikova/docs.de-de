---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 790e852eb515e19afc324f6e1c25db81ed22999c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148671"
---
# \<workflowIdle>

<span data-ttu-id="4c07e-101">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="4c07e-101">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**  
  
## <a name="syntax"></a><span data-ttu-id="4c07e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c07e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c07e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4c07e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4c07e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c07e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c07e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="4c07e-105">Attributes</span></span>  
  
|<span data-ttu-id="4c07e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="4c07e-106">Attribute</span></span>|<span data-ttu-id="4c07e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c07e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c07e-108">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="4c07e-108">timeToPersist</span></span>|<span data-ttu-id="4c07e-109">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4c07e-109">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="4c07e-110">Der Standardwert ist TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="4c07e-110">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="4c07e-111">Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="4c07e-111">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="4c07e-112">Dieses Attribut ist nützlich, wenn eine Workflowinstanz auf aggressivere Weise beibehalten werden soll, während die Instanz solange als möglich im Speicher verbleiben soll.</span><span class="sxs-lookup"><span data-stu-id="4c07e-112">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="4c07e-113">Dieses Attribut ist nur gültig, wenn der Wert kleiner als das **Timeto** -Attribut ist.</span><span class="sxs-lookup"><span data-stu-id="4c07e-113">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="4c07e-114">Ist er größer, wird das Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4c07e-114">If it is greater, it is ignored.</span></span> <span data-ttu-id="4c07e-115">Wenn dieses Attribut vor dem durch das **Timeto** -Attribut angegebenen Wert abläuft, muss die Persistenz vor dem Entladen des Workflows fertiggestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c07e-115">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="4c07e-116">Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4c07e-116">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="4c07e-117">Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="4c07e-117">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="4c07e-118">Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4c07e-118">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="4c07e-119">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="4c07e-119">timeToUnload</span></span>|<span data-ttu-id="4c07e-120">Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird.</span><span class="sxs-lookup"><span data-stu-id="4c07e-120">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="4c07e-121">Der Standardwert beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="4c07e-121">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="4c07e-122">Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4c07e-122">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="4c07e-123">Ist dieses Attribut auf 0 (null) festgelegt, wird die Workflowinstanz sofort beibehalten und entladen, nachdem der Workflow in den Leerlauf versetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="4c07e-123">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="4c07e-124">Der Entladevorgang wird deaktiviert, wenn dieses Attribut auf TimeSpan.MaxValue festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4c07e-124">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="4c07e-125">Workflowinstanzen im Leerlauf werden nie entladen.</span><span class="sxs-lookup"><span data-stu-id="4c07e-125">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c07e-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c07e-126">Child Elements</span></span>  

 <span data-ttu-id="4c07e-127">Keine</span><span class="sxs-lookup"><span data-stu-id="4c07e-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c07e-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c07e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="4c07e-129">Element</span><span class="sxs-lookup"><span data-stu-id="4c07e-129">Element</span></span>|<span data-ttu-id="4c07e-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c07e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c07e-131">\<behavior> von \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4c07e-131">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4c07e-132">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="4c07e-132">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c07e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c07e-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
