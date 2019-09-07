---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398570"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="7a5b3-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="7a5b3-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="7a5b3-102">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="7a5b3-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="7a5b3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a5b3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a5b3-104">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7a5b3-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="7a5b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7a5b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="7a5b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7a5b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="7a5b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7a5b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="7a5b3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowunlenker dexception->**</span><span class="sxs-lookup"><span data-stu-id="7a5b3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a5b3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a5b3-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a5b3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7a5b3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7a5b3-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a5b3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a5b3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7a5b3-112">Attributes</span></span>  
  
|<span data-ttu-id="7a5b3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7a5b3-113">Attribute</span></span>|<span data-ttu-id="7a5b3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a5b3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a5b3-115">action</span><span class="sxs-lookup"><span data-stu-id="7a5b3-115">action</span></span>|<span data-ttu-id="7a5b3-116">Eine Zeichenfolge, die die Aktion angibt, die ausgeführt wird, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="7a5b3-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="7a5b3-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="7a5b3-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a5b3-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7a5b3-118">Child Elements</span></span>  
 <span data-ttu-id="7a5b3-119">Keine</span><span class="sxs-lookup"><span data-stu-id="7a5b3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a5b3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7a5b3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a5b3-121">Element</span><span class="sxs-lookup"><span data-stu-id="7a5b3-121">Element</span></span>|<span data-ttu-id="7a5b3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a5b3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a5b3-123">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="7a5b3-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="7a5b3-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="7a5b3-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a5b3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a5b3-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
