---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 73d8549f68e8ca77115619431c857c4a2aac3fdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153021"
---
# <a name="commonparameters"></a><span data-ttu-id="c8310-101">\<CommonParameters></span><span class="sxs-lookup"><span data-stu-id="c8310-101">\<commonParameters></span></span>
<span data-ttu-id="c8310-102">Stellt eine Auflistung von Parametern dar, die global in mehreren Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8310-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="c8310-103">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="c8310-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="c8310-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8310-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8310-105">&nbsp;&nbsp;[**\<system.serviceModell>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8310-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c8310-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c8310-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c8310-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c8310-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="c8310-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c8310-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="c8310-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="c8310-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="c8310-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<CommonParameters>**</span><span class="sxs-lookup"><span data-stu-id="c8310-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8310-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8310-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8310-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8310-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c8310-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8310-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8310-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="c8310-114">Attributes</span></span>  
 <span data-ttu-id="c8310-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="c8310-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8310-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8310-116">Child Elements</span></span>  
  
|<span data-ttu-id="c8310-117">Element</span><span class="sxs-lookup"><span data-stu-id="c8310-117">Element</span></span>|<span data-ttu-id="c8310-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8310-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8310-119">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="c8310-119">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="c8310-120">Fügt ein Name-Wert-Paar von allgemeinen von Diensten verwendeten Parametern zur Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c8310-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8310-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8310-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c8310-122">Element</span><span class="sxs-lookup"><span data-stu-id="c8310-122">Element</span></span>|<span data-ttu-id="c8310-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8310-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8310-124">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="c8310-124">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="c8310-125">Gibt Einstellungen für eine <xref:System.Workflow.Runtime.WorkflowRuntime> Instanz von für das Hosten von Workflow-basierten Windows Communication Foundation (WCF)-Diensten an.</span><span class="sxs-lookup"><span data-stu-id="c8310-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8310-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c8310-126">Remarks</span></span>  
 <span data-ttu-id="c8310-127">Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="c8310-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8310-128">Der SQL-Überwachungsdienst verwendet den `ConnectionString`-Wert nicht auf einheitliche Weise, wenn er im `<commonParameters>`-Abschnitt angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c8310-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="c8310-129">Einige der Vorgänge wie das Abrufen der `StateMachineWorkflowInstance.StateHistory`-Eigenschaft schlagen möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="c8310-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="c8310-130">Um dies zu umgehen, geben Sie das `ConnectionString`-Attribut im Konfigurationsabschnitt für Überwachungsprovider an, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c8310-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  

```xml  
<add
type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />
```  
  
 <span data-ttu-id="c8310-131">Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c8310-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="c8310-132">Beachten Sie, dass `EnableRetries` der Parameter entweder auf globaler Ebene (wie im Abschnitt *CommonParameters* gezeigt) oder für einzelne Dienste festgelegt werden kann, die unterstützen `EnableRetries` (wie im Abschnitt *Dienste* gezeigt).</span><span class="sxs-lookup"><span data-stu-id="c8310-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="c8310-133">Der folgende Beispielcode zeigt, wie Sie die allgemeinen Parameter programmgesteuert ändern:</span><span class="sxs-lookup"><span data-stu-id="c8310-133">The following sample code shows how to change the common parameters programmatically:</span></span>
  
```csharp  
Configuration config = WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");
var wfruntime = config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters = wfruntime.CommonParameters;
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="c8310-134">Weitere Informationen zum Verwenden einer Konfigurationsdatei zum <xref:System.Workflow.Runtime.WorkflowRuntime> Steuern des Verhaltens eines Objekts einer Windows Workflow Foundation-Hostanwendung finden Sie unter [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c8310-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8310-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8310-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="c8310-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8310-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="c8310-137">[Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8310-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="c8310-138">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="c8310-138">\<add></span></span>](add-of-commonparameters.md)
