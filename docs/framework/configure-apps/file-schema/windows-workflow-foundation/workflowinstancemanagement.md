---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: a22c72b7a683e3ecab4344c92e7d835a184a58d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947160"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="596c8-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="596c8-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="596c8-102">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="596c8-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="596c8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="596c8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="596c8-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="596c8-104">\<behaviors></span></span>  
<span data-ttu-id="596c8-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="596c8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="596c8-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="596c8-106">\<behavior></span></span>  
<span data-ttu-id="596c8-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="596c8-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596c8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="596c8-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="596c8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="596c8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="596c8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="596c8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="596c8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="596c8-111">Attributes</span></span>  
  
|<span data-ttu-id="596c8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="596c8-112">Attribute</span></span>|<span data-ttu-id="596c8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="596c8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="596c8-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="596c8-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="596c8-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="596c8-115">Child Elements</span></span>  
 <span data-ttu-id="596c8-116">Keine</span><span class="sxs-lookup"><span data-stu-id="596c8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="596c8-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="596c8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="596c8-118">Element</span><span class="sxs-lookup"><span data-stu-id="596c8-118">Element</span></span>|<span data-ttu-id="596c8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="596c8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="596c8-120">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="596c8-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="596c8-121">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="596c8-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="596c8-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="596c8-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
