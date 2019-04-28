---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: db5e1083c07d4e204eb19eaae9257ed44439132e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673146"
---
# <a name="workflowruntime"></a><span data-ttu-id="e9d5f-101">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="e9d5f-101">\<workflowRuntime></span></span>
<span data-ttu-id="e9d5f-102">Gibt die Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter Windows Communication Foundation (WCF)-Diensten.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="e9d5f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e9d5f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9d5f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e9d5f-104">\<behaviors></span></span>  
<span data-ttu-id="e9d5f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e9d5f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e9d5f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e9d5f-106">\<behavior></span></span>  
<span data-ttu-id="e9d5f-107">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="e9d5f-107">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d5f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9d5f-108">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9d5f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9d5f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9d5f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9d5f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9d5f-111">Attributes</span></span>  
  
|<span data-ttu-id="e9d5f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e9d5f-112">Attribute</span></span>|<span data-ttu-id="e9d5f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d5f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9d5f-114">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="e9d5f-114">cachedInstanceExpiration</span></span>|<span data-ttu-id="e9d5f-115">Ein optionaler <xref:System.TimeSpan>-Wert, der die maximale Dauer angibt, die eine Workflowinstanz im Arbeitsspeicher im Leerlaufzustand verbleiben kann, bevor ihre Entladung oder ihr Abbruch erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-115">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="e9d5f-116">Wenn die Workflow-Laufzeit über `PersistenceService` verfügt, der unloadOnIdle ausführt, wird dieses Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-116">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="e9d5f-117">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="e9d5f-117">enablePerformanceCounters</span></span>|<span data-ttu-id="e9d5f-118">Ein optionaler boolescher Wert, der angibt, ob Leistungsindikatoren aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-118">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="e9d5f-119">Leistungsindikatoren liefern Informationen zu verschiedenen workflowbezogenen Statistiken, verursachen jedoch eine Leistungseinbuße, wenn die Workflowruntime-Engine gestartet wird und Workflowinstanzen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-119">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="e9d5f-120">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-120">The default value is `true`.</span></span>|  
|<span data-ttu-id="e9d5f-121">Name</span><span class="sxs-lookup"><span data-stu-id="e9d5f-121">name</span></span>|<span data-ttu-id="e9d5f-122">Eine Zeichenfolge, die den Namen der Workflow-Laufzeitengine enthält.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-122">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="e9d5f-123">Der Name wird in der Ausgabe verwendet, um diese Laufzeit von anderen Laufzeiten zu unterscheiden, die unter Umständen im System ausgeführt werden, beispielsweise in Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-123">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="e9d5f-124">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-124">The default is an empty string.</span></span>|  
|<span data-ttu-id="e9d5f-125">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="e9d5f-125">validateOnCreate</span></span>|<span data-ttu-id="e9d5f-126">Ein optionaler boolescher Wert, der angibt, ob eine Überprüfung der Workflowdefinition auftritt, wenn WorkflowServiceHost geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-126">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="e9d5f-127">Wenn dieses Attribut auf `true` festgelegt ist, wird die Workflowüberprüfung jedes Mal ausgeführt, wenn `WorkflowServiceHost.Open` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-127">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="e9d5f-128">Wenn Validierungsfehler gefunden werden, wird ein <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>-Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-128">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="e9d5f-129">Wenn diese Eigenschaft auf `false` festgelegt wird, findet keine Workflow-Definitionsvalidierung statt.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-129">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="e9d5f-130">Der Standardwert für diese Eigenschaft ist `true`.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-130">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9d5f-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9d5f-131">Child Elements</span></span>  
  
|<span data-ttu-id="e9d5f-132">Element</span><span class="sxs-lookup"><span data-stu-id="e9d5f-132">Element</span></span>|<span data-ttu-id="e9d5f-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d5f-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9d5f-134">commonParameters</span><span class="sxs-lookup"><span data-stu-id="e9d5f-134">commonParameters</span></span>|<span data-ttu-id="e9d5f-135">Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-135">A collection of common parameters used by services.</span></span> <span data-ttu-id="e9d5f-136">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-136">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="e9d5f-137">Dienste</span><span class="sxs-lookup"><span data-stu-id="e9d5f-137">services</span></span>|<span data-ttu-id="e9d5f-138">Eine Auflistung von Diensten, die der <xref:System.Workflow.Runtime.WorkflowRuntime>-Engine hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-138">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="e9d5f-139">Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-139">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="e9d5f-140">Die in der Auflistung angegebenen Dienste werden von der Workflowruntime-Engine initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-140">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="e9d5f-141">Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-141">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="e9d5f-142">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-142">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9d5f-143">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9d5f-143">Parent Elements</span></span>  
  
|<span data-ttu-id="e9d5f-144">Element</span><span class="sxs-lookup"><span data-stu-id="e9d5f-144">Element</span></span>|<span data-ttu-id="e9d5f-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d5f-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9d5f-146">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e9d5f-146">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e9d5f-147">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="e9d5f-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d5f-148">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9d5f-148">Remarks</span></span>  
 <span data-ttu-id="e9d5f-149">Weitere Informationen zur Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens von einem <xref:System.Workflow.Runtime.WorkflowRuntime> Objekt einer hostanwendung von Windows Workflow Foundation finden Sie unter [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e9d5f-149">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9d5f-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9d5f-150">Example</span></span>  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="e9d5f-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d5f-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="e9d5f-152">[Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e9d5f-152">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
