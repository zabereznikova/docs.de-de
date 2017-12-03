---
title: '&lt;workflowInstanceManagement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e0f2b0ed88ee73edb52a8c18346746beb34771
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="bf778-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="bf778-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="bf778-103">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="bf778-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="bf778-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bf778-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bf778-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="bf778-105">\<behaviors></span></span>  
<span data-ttu-id="bf778-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bf778-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bf778-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="bf778-107">\<behavior></span></span>  
<span data-ttu-id="bf778-108">\<WorkflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="bf778-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf778-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf778-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf778-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf778-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bf778-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf778-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf778-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf778-112">Attributes</span></span>  
  
|<span data-ttu-id="bf778-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="bf778-113">Attribute</span></span>|<span data-ttu-id="bf778-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf778-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf778-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="bf778-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="bf778-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf778-116">Child Elements</span></span>  
 <span data-ttu-id="bf778-117">Keine</span><span class="sxs-lookup"><span data-stu-id="bf778-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf778-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf778-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bf778-119">Element</span><span class="sxs-lookup"><span data-stu-id="bf778-119">Element</span></span>|<span data-ttu-id="bf778-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf778-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf778-121">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bf778-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="bf778-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="bf778-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf778-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf778-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
