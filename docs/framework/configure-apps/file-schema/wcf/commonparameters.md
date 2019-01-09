---
title: '&lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: d16807d9faae427d8c22aafc1e1f4f04e5cb13b7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149461"
---
# <a name="ltcommonparametersgt"></a><span data-ttu-id="411cb-102">&lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="411cb-102">&lt;commonParameters&gt;</span></span>
<span data-ttu-id="411cb-103">Stellt eine Auflistung von Parametern dar, die global in mehreren Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="411cb-103">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="411cb-104">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="411cb-104">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="411cb-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="411cb-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="411cb-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="411cb-106">\<behaviors></span></span>  
<span data-ttu-id="411cb-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="411cb-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="411cb-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="411cb-108">\<behavior></span></span>  
<span data-ttu-id="411cb-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="411cb-109">\<workflowRuntime></span></span>  
<span data-ttu-id="411cb-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="411cb-110">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411cb-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="411cb-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="411cb-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="411cb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="411cb-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="411cb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="411cb-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="411cb-114">Attributes</span></span>  
 <span data-ttu-id="411cb-115">Keine</span><span class="sxs-lookup"><span data-stu-id="411cb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="411cb-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="411cb-116">Child Elements</span></span>  
  
|<span data-ttu-id="411cb-117">Element</span><span class="sxs-lookup"><span data-stu-id="411cb-117">Element</span></span>|<span data-ttu-id="411cb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411cb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="411cb-119">\<add></span><span class="sxs-lookup"><span data-stu-id="411cb-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="411cb-120">Fügt ein Name-Wert-Paar von allgemeinen von Diensten verwendeten Parametern zur Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="411cb-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="411cb-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="411cb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="411cb-122">Element</span><span class="sxs-lookup"><span data-stu-id="411cb-122">Element</span></span>|<span data-ttu-id="411cb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411cb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="411cb-124">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="411cb-124">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="411cb-125">Gibt die Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter Windows Communication Foundation (WCF)-Diensten.</span><span class="sxs-lookup"><span data-stu-id="411cb-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="411cb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="411cb-126">Remarks</span></span>  
 <span data-ttu-id="411cb-127">Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="411cb-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="411cb-128">Der SQL-Überwachungsdienst verwendet den `ConnectionString`-Wert nicht auf einheitliche Weise, wenn er im `<commonParameters>`-Abschnitt angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="411cb-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="411cb-129">Einige der Vorgänge wie das Abrufen der `StateMachineWorkflowInstance.StateHistory`-Eigenschaft schlagen möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="411cb-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="411cb-130">Um dies zu umgehen, geben Sie das `ConnectionString`-Attribut im Konfigurationsabschnitt für Überwachungsprovider an, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="411cb-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="411cb-131">Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="411cb-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="411cb-132">Beachten Sie, dass die `EnableRetries` Parameter kann festgelegt werden, entweder auf globaler Ebene (siehe die *CommonParameters* Abschnitt) oder für einzelne Dienste, die unterstützen `EnableRetries` (siehe die *Services*Abschnitt).</span><span class="sxs-lookup"><span data-stu-id="411cb-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="411cb-133">Im folgenden Beispielcode wird veranschaulicht, wie die allgemeinen Parameter programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="411cb-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="411cb-134">Weitere Informationen zur Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens von einem <xref:System.Workflow.Runtime.WorkflowRuntime> Objekt einer hostanwendung von Windows Workflow Foundation finden Sie unter [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="411cb-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="411cb-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="411cb-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="411cb-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="411cb-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="411cb-137">[Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="411cb-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="411cb-138">\<add></span><span class="sxs-lookup"><span data-stu-id="411cb-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
