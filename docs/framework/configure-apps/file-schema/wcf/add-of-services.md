---
title: <add> von <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 31a4d2a5a3baf3d53cf18ab6e37edfaf7acb8540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204982"
---
# <a name="add-of-services"></a><span data-ttu-id="8e6f0-102">\<add> von \<services></span><span class="sxs-lookup"><span data-stu-id="8e6f0-102">\<add> of \<services></span></span>

<span data-ttu-id="8e6f0-103">Gibt Einstellungen für eine Instanz von <xref:System.Workflow.Runtime.WorkflowRuntime> zum Hosting von Workflow basierten Windows Communication Foundation (WCF)-Diensten an.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="8e6f0-104">Dieses Element ist vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8e6f0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e6f0-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e6f0-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e6f0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8e6f0-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e6f0-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e6f0-108">Attributes</span></span>  
  
|<span data-ttu-id="8e6f0-109">attribute</span><span class="sxs-lookup"><span data-stu-id="8e6f0-109">Attribute</span></span>|<span data-ttu-id="8e6f0-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e6f0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e6f0-111">type</span><span class="sxs-lookup"><span data-stu-id="8e6f0-111">type</span></span>|<span data-ttu-id="8e6f0-112">Eine Zeichenfolge, die den durch die Assembly bezeichneten Typnamen des zu initialisierenden Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-112">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="8e6f0-113">Der angegebene Dienst muss bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-113">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="8e6f0-114">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-114">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e6f0-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e6f0-115">Child Elements</span></span>  

 <span data-ttu-id="8e6f0-116">Keine</span><span class="sxs-lookup"><span data-stu-id="8e6f0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e6f0-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e6f0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8e6f0-118">Element</span><span class="sxs-lookup"><span data-stu-id="8e6f0-118">Element</span></span>|<span data-ttu-id="8e6f0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e6f0-119">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="8e6f0-120">Eine Auflistung von Diensten, die der <xref:System.Workflow.Runtime.WorkflowRuntime>-Engine hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-120">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="8e6f0-121">Die Elemente sind vom Typ <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-121">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="8e6f0-122">Die in der Auflistung angegebenen Dienste werden von der Workflowruntime-Engine initialisiert und den Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-122">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="8e6f0-123">Aus diesem Grund müssen die in der Auflistung angegebenen Dienste bestimmte Regeln bezüglich der Signaturen ihrer Konstruktoren erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-123">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="8e6f0-124">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-124">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e6f0-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8e6f0-125">Remarks</span></span>  

 <span data-ttu-id="8e6f0-126">Der in diesem Element angegebene Dienst wird von der Workflowruntime-Engine initialisiert und seinen Diensten hinzugefügt, wenn der entsprechende <xref:System.Workflow.Runtime.WorkflowRuntime>-Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-126">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="8e6f0-127">Deshalb muss der in der Auflistung angegebenen Dienst bestimmten Regeln über die Signaturen ihrer Konstruktoren folgen.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-127">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="8e6f0-128">Weitere Informationen finden Sie unter <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="8e6f0-128">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e6f0-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e6f0-129">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e6f0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e6f0-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="8e6f0-131">[Workflowkonfigurationsdateien](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8e6f0-131">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
