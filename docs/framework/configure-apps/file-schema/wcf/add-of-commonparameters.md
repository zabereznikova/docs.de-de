---
title: <add> von <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400667"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="bb705-102">\<add> von \<commonParameters></span><span class="sxs-lookup"><span data-stu-id="bb705-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="bb705-103">Gibt ein Name-Wert-Paar von Parametern an, die global in mehreren Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb705-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="bb705-104">In der Regel umfasst dieser Parameter die Datenbank-Verbindungszeichenfolge, die von permanenten Diensten freigegeben werden könnte.</span><span class="sxs-lookup"><span data-stu-id="bb705-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="bb705-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb705-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb705-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb705-106">Attributes and Elements</span></span>  
 <span data-ttu-id="bb705-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb705-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb705-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb705-108">Attributes</span></span>  
  
|<span data-ttu-id="bb705-109">attribute</span><span class="sxs-lookup"><span data-stu-id="bb705-109">Attribute</span></span>|<span data-ttu-id="bb705-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bb705-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb705-111">name</span><span class="sxs-lookup"><span data-stu-id="bb705-111">name</span></span>|<span data-ttu-id="bb705-112">Der Name des für einen Dienst angegebenen Parameters.</span><span class="sxs-lookup"><span data-stu-id="bb705-112">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="bb705-113">value</span><span class="sxs-lookup"><span data-stu-id="bb705-113">value</span></span>|<span data-ttu-id="bb705-114">Der Wert des für einen Dienst angegebenen Parameters.</span><span class="sxs-lookup"><span data-stu-id="bb705-114">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb705-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb705-115">Child Elements</span></span>  
 <span data-ttu-id="bb705-116">Keine</span><span class="sxs-lookup"><span data-stu-id="bb705-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb705-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb705-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bb705-118">Element</span><span class="sxs-lookup"><span data-stu-id="bb705-118">Element</span></span>|<span data-ttu-id="bb705-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb705-119">Description</span></span>|  
|-------------|-----------------|  
|[\<commonParameters>](commonparameters.md)|<span data-ttu-id="bb705-120">Eine Auflistung der allgemeinen, von Diensten verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="bb705-120">A collection of common parameters used by services.</span></span> <span data-ttu-id="bb705-121">Diese Auflistung schließt in der Regel die Datenbankverbindungszeichenfolge ein, die ggf. von permanenten Diensten gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="bb705-121">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb705-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bb705-122">Remarks</span></span>  
 <span data-ttu-id="bb705-123">Mit dem `<commonParameters>`-Element werden alle Parameter definiert, die global in mehreren Diensten verwendet werden, beispielsweise `ConnectionString` bei der Verwendung von <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="bb705-123">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="bb705-124">Dienste, die Commits für Arbeitsbatches in Persistenzspeichern ausführen, z. B. <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> und <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, können mit dem `EnableRetries`-Parameter so konfiguriert werden, dass sie ihre Transaktion wiederholen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bb705-124">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="bb705-125">Beachten Sie, dass der- `EnableRetries` Parameter entweder auf globaler Ebene (wie im Abschnitt " *CommonParameters* " gezeigt) oder für einzelne Dienste, die unterstützen (siehe Abschnitt "Dienste"), festgelegt werden kann `EnableRetries` . *Services*</span><span class="sxs-lookup"><span data-stu-id="bb705-125">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="bb705-126">Weitere Informationen zum Verwenden einer Konfigurationsdatei zum Steuern des Verhaltens eines- <xref:System.Workflow.Runtime.WorkflowRuntime> Objekts einer Windows Workflow Foundation Host Anwendung finden Sie unter [Workflow Konfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="bb705-126">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb705-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb705-127">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="bb705-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb705-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="bb705-129">[Workflowkonfigurationsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bb705-129">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [\<commonParameters>](commonparameters.md)
