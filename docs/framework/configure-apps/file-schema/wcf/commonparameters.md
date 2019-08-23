---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: a92a81062e92f832be78af2bfd75270390eaac3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919494"
---
# <a name="commonparameters"></a><span data-ttu-id="654f5-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="654f5-101">\<commonParameters></span></span>
<span data-ttu-id="654f5-102">Stellt eine Auflistung von Parametern dar, die global in mehreren Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="654f5-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="654f5-103">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="654f5-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="654f5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="654f5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="654f5-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="654f5-105">\<behaviors></span></span>  
<span data-ttu-id="654f5-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="654f5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="654f5-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="654f5-107">\<behavior></span></span>  
<span data-ttu-id="654f5-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="654f5-108">\<workflowRuntime></span></span>  
<span data-ttu-id="654f5-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="654f5-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="654f5-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="654f5-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="654f5-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="654f5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="654f5-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="654f5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="654f5-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="654f5-113">Attributes</span></span>  
 <span data-ttu-id="654f5-114">Keine</span><span class="sxs-lookup"><span data-stu-id="654f5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="654f5-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="654f5-115">Child Elements</span></span>  
  
|<span data-ttu-id="654f5-116">Element</span><span class="sxs-lookup"><span data-stu-id="654f5-116">Element</span></span>|<span data-ttu-id="654f5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="654f5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="654f5-118">\<add></span><span class="sxs-lookup"><span data-stu-id="654f5-118">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="654f5-119">Fügt ein Name-Wert-Paar von allgemeinen von Diensten verwendeten Parametern zur Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="654f5-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="654f5-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="654f5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="654f5-121">Element</span><span class="sxs-lookup"><span data-stu-id="654f5-121">Element</span></span>|<span data-ttu-id="654f5-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="654f5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="654f5-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="654f5-123">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="654f5-124">Gibt Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosting von Workflow basierten Windows Communication Foundation (WCF)-Diensten an.</span><span class="sxs-lookup"><span data-stu-id="654f5-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="654f5-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="654f5-125">Remarks</span></span>  
 <span data-ttu-id="654f5-126">Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="654f5-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="654f5-127">Der SQL-Überwachungsdienst verwendet den `ConnectionString`-Wert nicht auf einheitliche Weise, wenn er im `<commonParameters>`-Abschnitt angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="654f5-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="654f5-128">Einige der Vorgänge wie das Abrufen der `StateMachineWorkflowInstance.StateHistory`-Eigenschaft schlagen möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="654f5-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="654f5-129">Um dies zu umgehen, geben Sie das `ConnectionString`-Attribut im Konfigurationsabschnitt für Überwachungsprovider an, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="654f5-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="654f5-130">Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="654f5-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="654f5-131">Beachten Sie, `EnableRetries` dass der-Parameter entweder auf globaler Ebene (siehe Abschnitt *CommonParameters* ) oder für einzelne Dienste, die unterstützen `EnableRetries` (siehe Abschnitt *Dienste* ), festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="654f5-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="654f5-132">Im folgenden Beispielcode wird veranschaulicht, wie die allgemeinen Parameter programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="654f5-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="654f5-133">Weitere Informationen zum Verwenden einer Konfigurationsdatei zum Steuern des Verhaltens <xref:System.Workflow.Runtime.WorkflowRuntime> eines-Objekts einer Windows Workflow Foundation Host Anwendung finden Sie unter [Workflow Konfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="654f5-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="654f5-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="654f5-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="654f5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="654f5-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="654f5-136">[Workflow Konfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="654f5-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="654f5-137">\<add></span><span class="sxs-lookup"><span data-stu-id="654f5-137">\<add></span></span>](add-of-commonparameters.md)
