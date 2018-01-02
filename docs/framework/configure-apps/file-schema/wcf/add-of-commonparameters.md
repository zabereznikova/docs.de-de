---
title: '&lt;add&gt; von &lt;commonParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb11f83ed2b7d3d371d7dc5475f4ce3672bb8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="4ad20-102">&lt;add&gt; von &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="4ad20-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="4ad20-103">Gibt ein Name-Wert-Paar von Parametern an, die global in mehreren Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ad20-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="4ad20-104">In der Regel umfasst dieser Parameter die Datenbank-Verbindungszeichenfolge, die von permanenten Diensten freigegeben werden könnte.</span><span class="sxs-lookup"><span data-stu-id="4ad20-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="4ad20-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4ad20-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4ad20-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="4ad20-106">\<behaviors></span></span>  
<span data-ttu-id="4ad20-107">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4ad20-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="4ad20-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="4ad20-108">\<behavior></span></span>  
<span data-ttu-id="4ad20-109">\<WorkflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="4ad20-109">\<workflowRuntime></span></span>  
<span data-ttu-id="4ad20-110">\<Allgemeine Parameter ></span><span class="sxs-lookup"><span data-stu-id="4ad20-110">\<commonParameters></span></span>  
<span data-ttu-id="4ad20-111">\<add></span><span class="sxs-lookup"><span data-stu-id="4ad20-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad20-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ad20-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ad20-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ad20-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4ad20-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ad20-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ad20-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ad20-115">Attributes</span></span>  
  
|<span data-ttu-id="4ad20-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="4ad20-116">Attribute</span></span>|<span data-ttu-id="4ad20-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ad20-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ad20-118">Name</span><span class="sxs-lookup"><span data-stu-id="4ad20-118">name</span></span>|<span data-ttu-id="4ad20-119">Der Name des für einen Dienst angegebenen Parameters.</span><span class="sxs-lookup"><span data-stu-id="4ad20-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="4ad20-120">Wert</span><span class="sxs-lookup"><span data-stu-id="4ad20-120">value</span></span>|<span data-ttu-id="4ad20-121">Der Wert des für einen Dienst angegebenen Parameters.</span><span class="sxs-lookup"><span data-stu-id="4ad20-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ad20-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ad20-122">Child Elements</span></span>  
 <span data-ttu-id="4ad20-123">Keine</span><span class="sxs-lookup"><span data-stu-id="4ad20-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ad20-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ad20-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4ad20-125">Element</span><span class="sxs-lookup"><span data-stu-id="4ad20-125">Element</span></span>|<span data-ttu-id="4ad20-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ad20-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ad20-127">\<Allgemeine Parameter ></span><span class="sxs-lookup"><span data-stu-id="4ad20-127">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="4ad20-128">Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="4ad20-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="4ad20-129">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="4ad20-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ad20-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ad20-130">Remarks</span></span>  
 <span data-ttu-id="4ad20-131">Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="4ad20-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="4ad20-132">Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4ad20-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="4ad20-133">Beachten Sie, dass die `EnableRetries` Parameter kann festgelegt werden auf globalen Ebene (entsprechend der *CommonParameters* Abschnitt) oder für einzelne Dienste, unterstützen `EnableRetries` (entsprechend der *Services*Abschnitt).</span><span class="sxs-lookup"><span data-stu-id="4ad20-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="4ad20-134">Weitere Informationen zur Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens von einer <xref:System.Workflow.Runtime.WorkflowRuntime> Objekt einer Windows Workflow Foundation-Host-Anwendung finden Sie unter [Workflow-Konfigurationsdateien](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="4ad20-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ad20-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ad20-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ad20-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ad20-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="4ad20-137">Workflow-Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="4ad20-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="4ad20-138">\<Allgemeine Parameter ></span><span class="sxs-lookup"><span data-stu-id="4ad20-138">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
