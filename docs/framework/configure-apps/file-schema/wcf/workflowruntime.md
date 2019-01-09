---
title: '&lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: ffc4bbeb44561cbe2d809b2fb2263068fef542d1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150070"
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="0ada4-102">&lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="0ada4-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="0ada4-103">Gibt die Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosten workflowbasierter Windows Communication Foundation (WCF)-Diensten.</span><span class="sxs-lookup"><span data-stu-id="0ada4-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="0ada4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0ada4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ada4-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0ada4-105">\<behaviors></span></span>  
<span data-ttu-id="0ada4-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0ada4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0ada4-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0ada4-107">\<behavior></span></span>  
<span data-ttu-id="0ada4-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="0ada4-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ada4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ada4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ada4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0ada4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0ada4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ada4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ada4-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ada4-112">Attributes</span></span>  
  
|<span data-ttu-id="0ada4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0ada4-113">Attribute</span></span>|<span data-ttu-id="0ada4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ada4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ada4-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="0ada4-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="0ada4-116">Ein optionaler <xref:System.TimeSpan>-Wert, der die maximale Dauer angibt, die eine Workflowinstanz im Arbeitsspeicher im Leerlaufzustand verbleiben kann, bevor ihre Entladung oder ihr Abbruch erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="0ada4-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="0ada4-117">Wenn die Workflow-Laufzeit über `PersistenceService` verfügt, der unloadOnIdle ausführt, wird dieses Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0ada4-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="0ada4-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="0ada4-118">enablePerformanceCounters</span></span>|<span data-ttu-id="0ada4-119">Ein optionaler boolescher Wert, der angibt, ob Leistungsindikatoren aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="0ada4-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="0ada4-120">Leistungsindikatoren liefern Informationen zu verschiedenen workflowbezogenen Statistiken, verursachen jedoch eine Leistungseinbuße, wenn das Workflow-Laufzeitmodul gestartet wird und Workflowinstanzen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ada4-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="0ada4-121">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="0ada4-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="0ada4-122">Name</span><span class="sxs-lookup"><span data-stu-id="0ada4-122">name</span></span>|<span data-ttu-id="0ada4-123">Eine Zeichenfolge, die den Namen der Workflow-Laufzeitengine enthält.</span><span class="sxs-lookup"><span data-stu-id="0ada4-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="0ada4-124">Der Name wird in der Ausgabe verwendet, um diese Laufzeit von anderen Laufzeiten zu unterscheiden, die unter Umständen im System ausgeführt werden, beispielsweise in Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="0ada4-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="0ada4-125">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0ada4-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="0ada4-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="0ada4-126">validateOnCreate</span></span>|<span data-ttu-id="0ada4-127">Ein optionaler boolescher Wert, der angibt, ob eine Überprüfung der Workflowdefinition auftritt, wenn WorkflowServiceHost geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="0ada4-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="0ada4-128">Wenn dieses Attribut auf `true` festgelegt ist, wird die Workflowüberprüfung jedes Mal ausgeführt, wenn `WorkflowServiceHost.Open` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0ada4-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="0ada4-129">Wenn Überprüfungsfehler gefunden werden, wird ein <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>-Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0ada4-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="0ada4-130">Wenn diese Eigenschaft auf `false` festgelegt wird, findet keine Workflow-Definitionsüberprüfung statt.</span><span class="sxs-lookup"><span data-stu-id="0ada4-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="0ada4-131">Der Standardwert für diese Eigenschaft ist `true`.</span><span class="sxs-lookup"><span data-stu-id="0ada4-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ada4-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ada4-132">Child Elements</span></span>  
  
|<span data-ttu-id="0ada4-133">Element</span><span class="sxs-lookup"><span data-stu-id="0ada4-133">Element</span></span>|<span data-ttu-id="0ada4-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ada4-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ada4-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="0ada4-135">commonParameters</span></span>|<span data-ttu-id="0ada4-136">Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="0ada4-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="0ada4-137">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="0ada4-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="0ada4-138">Dienste</span><span class="sxs-lookup"><span data-stu-id="0ada4-138">services</span></span>|<span data-ttu-id="0ada4-139">Eine Auflistung von Diensten, die dem <xref:System.Workflow.Runtime.WorkflowRuntime>-Modul hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0ada4-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="0ada4-140">Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ada4-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="0ada4-141">Die in der Auflistung angegebenen Dienste werden vom Workflow-Laufzeitmodul initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0ada4-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="0ada4-142">Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0ada4-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="0ada4-143">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ada4-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ada4-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ada4-144">Parent Elements</span></span>  
  
|<span data-ttu-id="0ada4-145">Element</span><span class="sxs-lookup"><span data-stu-id="0ada4-145">Element</span></span>|<span data-ttu-id="0ada4-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ada4-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ada4-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0ada4-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0ada4-148">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="0ada4-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ada4-149">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ada4-149">Remarks</span></span>  
 <span data-ttu-id="0ada4-150">Weitere Informationen zur Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens von einem <xref:System.Workflow.Runtime.WorkflowRuntime> Objekt einer hostanwendung von Windows Workflow Foundation finden Sie unter [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0ada4-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ada4-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ada4-151">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ada4-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ada4-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="0ada4-153">[Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0ada4-153">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
