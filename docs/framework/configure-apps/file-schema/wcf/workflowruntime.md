---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 4a450fb6f02bbf0f1681f7b2fabea9da7b65cbea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183597"
---
# \<workflowRuntime>

<span data-ttu-id="1edd0-101">Gibt Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosting von Workflow basierten Windows Communication Foundation (WCF)-Diensten an.</span><span class="sxs-lookup"><span data-stu-id="1edd0-101">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowRuntime>**  
  
## <a name="syntax"></a><span data-ttu-id="1edd0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="1edd0-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1edd0-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1edd0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1edd0-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1edd0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1edd0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="1edd0-105">Attributes</span></span>  
  
|<span data-ttu-id="1edd0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1edd0-106">Attribute</span></span>|<span data-ttu-id="1edd0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1edd0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1edd0-108">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="1edd0-108">cachedInstanceExpiration</span></span>|<span data-ttu-id="1edd0-109">Ein optionaler <xref:System.TimeSpan>-Wert, der die maximale Dauer angibt, die eine Workflowinstanz im Arbeitsspeicher im Leerlaufzustand verbleiben kann, bevor ihre Entladung oder ihr Abbruch erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="1edd0-109">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="1edd0-110">Wenn die Workflow-Laufzeit über `PersistenceService` verfügt, der unloadOnIdle ausführt, wird dieses Attribut ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1edd0-110">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="1edd0-111">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="1edd0-111">enablePerformanceCounters</span></span>|<span data-ttu-id="1edd0-112">Ein optionaler boolescher Wert, der angibt, ob Leistungsindikatoren aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1edd0-112">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="1edd0-113">Leistungsindikatoren liefern Informationen zu verschiedenen workflowbezogenen Statistiken, verursachen jedoch eine Leistungseinbuße, wenn die Workflowruntime-Engine gestartet wird und Workflowinstanzen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1edd0-113">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="1edd0-114">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="1edd0-114">The default value is `true`.</span></span>|  
|<span data-ttu-id="1edd0-115">name</span><span class="sxs-lookup"><span data-stu-id="1edd0-115">name</span></span>|<span data-ttu-id="1edd0-116">Eine Zeichenfolge, die den Namen der Workflow-Laufzeitengine enthält.</span><span class="sxs-lookup"><span data-stu-id="1edd0-116">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="1edd0-117">Der Name wird in der Ausgabe verwendet, um diese Laufzeit von anderen Laufzeiten zu unterscheiden, die unter Umständen im System ausgeführt werden, beispielsweise in Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1edd0-117">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="1edd0-118">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1edd0-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="1edd0-119">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="1edd0-119">validateOnCreate</span></span>|<span data-ttu-id="1edd0-120">Ein optionaler boolescher Wert, der angibt, ob eine Überprüfung der Workflowdefinition auftritt, wenn WorkflowServiceHost geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="1edd0-120">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="1edd0-121">Wenn dieses Attribut auf `true` festgelegt ist, wird die Workflowüberprüfung jedes Mal ausgeführt, wenn `WorkflowServiceHost.Open` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1edd0-121">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="1edd0-122">Wenn Validierungsfehler gefunden werden, wird ein <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>-Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1edd0-122">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="1edd0-123">Wenn diese Eigenschaft auf `false` festgelegt wird, findet keine Workflow-Definitionsvalidierung statt.</span><span class="sxs-lookup"><span data-stu-id="1edd0-123">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="1edd0-124">Der Standardwert dieser Eigenschaft ist `true`.</span><span class="sxs-lookup"><span data-stu-id="1edd0-124">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1edd0-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1edd0-125">Child Elements</span></span>  
  
|<span data-ttu-id="1edd0-126">Element</span><span class="sxs-lookup"><span data-stu-id="1edd0-126">Element</span></span>|<span data-ttu-id="1edd0-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1edd0-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1edd0-128">commonParameters</span><span class="sxs-lookup"><span data-stu-id="1edd0-128">commonParameters</span></span>|<span data-ttu-id="1edd0-129">Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="1edd0-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="1edd0-130">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="1edd0-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="1edd0-131">services</span><span class="sxs-lookup"><span data-stu-id="1edd0-131">services</span></span>|<span data-ttu-id="1edd0-132">Eine Auflistung von Diensten, die der <xref:System.Workflow.Runtime.WorkflowRuntime>-Engine hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1edd0-132">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="1edd0-133">Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="1edd0-133">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="1edd0-134">Die in der Auflistung angegebenen Dienste werden von der Workflowruntime-Engine initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1edd0-134">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="1edd0-135">Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1edd0-135">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="1edd0-136">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="1edd0-136">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1edd0-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1edd0-137">Parent Elements</span></span>  
  
|<span data-ttu-id="1edd0-138">Element</span><span class="sxs-lookup"><span data-stu-id="1edd0-138">Element</span></span>|<span data-ttu-id="1edd0-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1edd0-139">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1edd0-140">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="1edd0-140">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1edd0-141">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1edd0-141">Remarks</span></span>  

 <span data-ttu-id="1edd0-142">Weitere Informationen zum Verwenden einer Konfigurationsdatei zum Steuern des Verhaltens eines- <xref:System.Workflow.Runtime.WorkflowRuntime> Objekts einer Windows Workflow Foundation Host Anwendung finden Sie unter [Workflow Konfigurationsdateien](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1edd0-142">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1edd0-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1edd0-143">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1edd0-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1edd0-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="1edd0-145">[Workflowkonfigurationsdateien](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1edd0-145">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
