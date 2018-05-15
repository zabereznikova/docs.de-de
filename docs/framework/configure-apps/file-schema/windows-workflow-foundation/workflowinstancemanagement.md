---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: d86b0f61c6741fa156e04da75a62853f459324d1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="6ead9-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="6ead9-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="6ead9-103">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="6ead9-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="6ead9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6ead9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6ead9-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6ead9-105">\<behaviors></span></span>  
<span data-ttu-id="6ead9-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6ead9-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6ead9-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6ead9-107">\<behavior></span></span>  
<span data-ttu-id="6ead9-108">\<WorkflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="6ead9-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ead9-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ead9-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ead9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6ead9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6ead9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ead9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ead9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ead9-112">Attributes</span></span>  
  
|<span data-ttu-id="6ead9-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6ead9-113">Attribute</span></span>|<span data-ttu-id="6ead9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ead9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ead9-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="6ead9-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="6ead9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ead9-116">Child Elements</span></span>  
 <span data-ttu-id="6ead9-117">Keine</span><span class="sxs-lookup"><span data-stu-id="6ead9-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ead9-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ead9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6ead9-119">Element</span><span class="sxs-lookup"><span data-stu-id="6ead9-119">Element</span></span>|<span data-ttu-id="6ead9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ead9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ead9-121">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6ead9-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="6ead9-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="6ead9-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ead9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ead9-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
