---
title: '&lt;add&gt; von &lt;services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7e58638ba4a964a1780606e2f75c0fd453638eb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="dda5b-102">&lt;add&gt; von &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="dda5b-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="dda5b-103">Legt Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste fest.</span><span class="sxs-lookup"><span data-stu-id="dda5b-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="dda5b-104">Dieses Element ist vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="dda5b-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="dda5b-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dda5b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="dda5b-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="dda5b-106">\<behaviors></span></span>  
<span data-ttu-id="dda5b-107">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dda5b-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="dda5b-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="dda5b-108">\<behavior></span></span>  
<span data-ttu-id="dda5b-109">\<Services ></span><span class="sxs-lookup"><span data-stu-id="dda5b-109">\<services></span></span>  
<span data-ttu-id="dda5b-110">\<add></span><span class="sxs-lookup"><span data-stu-id="dda5b-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda5b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="dda5b-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dda5b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dda5b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dda5b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dda5b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dda5b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="dda5b-114">Attributes</span></span>  
  
|<span data-ttu-id="dda5b-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="dda5b-115">Attribute</span></span>|<span data-ttu-id="dda5b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dda5b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dda5b-117">Typ</span><span class="sxs-lookup"><span data-stu-id="dda5b-117">type</span></span>|<span data-ttu-id="dda5b-118">Eine Zeichenfolge, die den durch die Assembly bezeichneten Typnamen des zu initialisierenden Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="dda5b-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="dda5b-119">Der angegebene Dienst muss bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen.</span><span class="sxs-lookup"><span data-stu-id="dda5b-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="dda5b-120">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="dda5b-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dda5b-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dda5b-121">Child Elements</span></span>  
 <span data-ttu-id="dda5b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="dda5b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dda5b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dda5b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dda5b-124">Element</span><span class="sxs-lookup"><span data-stu-id="dda5b-124">Element</span></span>|<span data-ttu-id="dda5b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dda5b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dda5b-126">\<Services ></span><span class="sxs-lookup"><span data-stu-id="dda5b-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="dda5b-127">Eine Auflistung von Diensten, die dem <xref:System.Workflow.Runtime.WorkflowRuntime>-Modul hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dda5b-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="dda5b-128">Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="dda5b-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="dda5b-129">Die in der Auflistung angegebenen Dienste werden vom Workflow-Laufzeitmodul initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dda5b-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="dda5b-130">Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen.</span><span class="sxs-lookup"><span data-stu-id="dda5b-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="dda5b-131">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="dda5b-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dda5b-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dda5b-132">Remarks</span></span>  
 <span data-ttu-id="dda5b-133">Der in diesem Element angegebene Dienst wird vom Workflow-Lauftzeitmodul initialisiert und seinen Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dda5b-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="dda5b-134">Deshalb muss der in der Auflistung angegebenen Dienst bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen.</span><span class="sxs-lookup"><span data-stu-id="dda5b-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="dda5b-135">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="dda5b-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dda5b-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dda5b-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dda5b-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dda5b-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="dda5b-138">Workflow-Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="dda5b-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
