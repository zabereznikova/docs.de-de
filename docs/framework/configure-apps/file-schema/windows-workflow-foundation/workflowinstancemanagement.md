---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: ba3d9415efc21012b470fd2e9a7f426ca8f3aad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662061"
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="e8e29-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="e8e29-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="e8e29-103">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="e8e29-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="e8e29-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8e29-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8e29-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e8e29-105">\<behaviors></span></span>  
<span data-ttu-id="e8e29-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e8e29-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e8e29-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e8e29-107">\<behavior></span></span>  
<span data-ttu-id="e8e29-108">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="e8e29-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e29-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8e29-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8e29-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e8e29-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e8e29-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8e29-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8e29-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e8e29-112">Attributes</span></span>  
  
|<span data-ttu-id="e8e29-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e8e29-113">Attribute</span></span>|<span data-ttu-id="e8e29-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8e29-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8e29-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="e8e29-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="e8e29-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8e29-116">Child Elements</span></span>  
 <span data-ttu-id="e8e29-117">Keine</span><span class="sxs-lookup"><span data-stu-id="e8e29-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8e29-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8e29-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e8e29-119">Element</span><span class="sxs-lookup"><span data-stu-id="e8e29-119">Element</span></span>|<span data-ttu-id="e8e29-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8e29-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8e29-121">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e8e29-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e8e29-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="e8e29-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8e29-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8e29-123">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
