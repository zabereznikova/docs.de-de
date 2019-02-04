---
title: <add> von <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: e0ca00911577f9f210def9326df261f772f9c26d
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674424"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="be001-102">\<add> of \<commonParameters></span><span class="sxs-lookup"><span data-stu-id="be001-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="be001-103">Gibt ein Name-Wert-Paar von Parametern an, die global in mehreren Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be001-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="be001-104">In der Regel umfasst dieser Parameter die Datenbank-Verbindungszeichenfolge, die von permanenten Diensten freigegeben werden könnte.</span><span class="sxs-lookup"><span data-stu-id="be001-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="be001-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="be001-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="be001-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="be001-106">\<behaviors></span></span>  
<span data-ttu-id="be001-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="be001-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="be001-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="be001-108">\<behavior></span></span>  
<span data-ttu-id="be001-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="be001-109">\<workflowRuntime></span></span>  
<span data-ttu-id="be001-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="be001-110">\<commonParameters></span></span>  
<span data-ttu-id="be001-111">\<add></span><span class="sxs-lookup"><span data-stu-id="be001-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be001-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="be001-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be001-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="be001-113">Attributes and Elements</span></span>  
 <span data-ttu-id="be001-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be001-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be001-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="be001-115">Attributes</span></span>  
  
|<span data-ttu-id="be001-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="be001-116">Attribute</span></span>|<span data-ttu-id="be001-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be001-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be001-118">Name</span><span class="sxs-lookup"><span data-stu-id="be001-118">name</span></span>|<span data-ttu-id="be001-119">Der Name des für einen Dienst angegebenen Parameters.</span><span class="sxs-lookup"><span data-stu-id="be001-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="be001-120">Wert</span><span class="sxs-lookup"><span data-stu-id="be001-120">value</span></span>|<span data-ttu-id="be001-121">Der Wert des für einen Dienst angegebenen Parameters.</span><span class="sxs-lookup"><span data-stu-id="be001-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be001-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be001-122">Child Elements</span></span>  
 <span data-ttu-id="be001-123">Keine</span><span class="sxs-lookup"><span data-stu-id="be001-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be001-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be001-124">Parent Elements</span></span>  
  
|<span data-ttu-id="be001-125">Element</span><span class="sxs-lookup"><span data-stu-id="be001-125">Element</span></span>|<span data-ttu-id="be001-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be001-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be001-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="be001-127">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="be001-128">Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="be001-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="be001-129">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="be001-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be001-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be001-130">Remarks</span></span>  
 <span data-ttu-id="be001-131">Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="be001-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="be001-132">Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="be001-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="be001-133">Beachten Sie, dass die `EnableRetries` Parameter kann festgelegt werden auf globalen Ebene (siehe die *CommonParameters* Abschnitt) oder für einzelne Dienste, die unterstützen `EnableRetries` (siehe die *Services*Abschnitt).</span><span class="sxs-lookup"><span data-stu-id="be001-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="be001-134">Weitere Informationen zur Verwendung einer Konfigurationsdatei zum Steuern des Verhaltens von einem <xref:System.Workflow.Runtime.WorkflowRuntime> Objekt einer hostanwendung von Windows Workflow Foundation finden Sie unter [Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="be001-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be001-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be001-135">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="be001-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be001-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="be001-137">[Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="be001-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="be001-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="be001-138">\<commonParameters></span></span>](commonparameters.md)
