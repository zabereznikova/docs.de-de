---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191613"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="b6595-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="b6595-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="b6595-102">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="b6595-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="b6595-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b6595-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6595-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b6595-104">\<behaviors></span></span>  
<span data-ttu-id="b6595-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b6595-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="b6595-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b6595-106">\<behavior></span></span>  
<span data-ttu-id="b6595-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="b6595-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6595-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6595-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6595-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6595-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b6595-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6595-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6595-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6595-111">Attributes</span></span>  
  
|<span data-ttu-id="b6595-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="b6595-112">Attribute</span></span>|<span data-ttu-id="b6595-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6595-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6595-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="b6595-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="b6595-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6595-115">Child Elements</span></span>  
 <span data-ttu-id="b6595-116">Keine</span><span class="sxs-lookup"><span data-stu-id="b6595-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6595-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6595-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b6595-118">Element</span><span class="sxs-lookup"><span data-stu-id="b6595-118">Element</span></span>|<span data-ttu-id="b6595-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6595-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6595-120">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b6595-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b6595-121">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="b6595-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6595-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6595-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
