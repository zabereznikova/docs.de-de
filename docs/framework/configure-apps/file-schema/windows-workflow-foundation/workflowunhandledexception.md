---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398570"
---
# \<workflowUnhandledException>
<span data-ttu-id="15127-101">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="15127-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="15127-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="15127-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15127-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15127-103">Attributes and Elements</span></span>  
 <span data-ttu-id="15127-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15127-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15127-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="15127-105">Attributes</span></span>  
  
|<span data-ttu-id="15127-106">attribute</span><span class="sxs-lookup"><span data-stu-id="15127-106">Attribute</span></span>|<span data-ttu-id="15127-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="15127-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15127-108">action</span><span class="sxs-lookup"><span data-stu-id="15127-108">action</span></span>|<span data-ttu-id="15127-109">Eine Zeichenfolge, die die Aktion angibt, die ausgeführt wird, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="15127-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="15127-110">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="15127-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15127-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15127-111">Child Elements</span></span>  
 <span data-ttu-id="15127-112">Keine</span><span class="sxs-lookup"><span data-stu-id="15127-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15127-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15127-113">Parent Elements</span></span>  
  
|<span data-ttu-id="15127-114">Element</span><span class="sxs-lookup"><span data-stu-id="15127-114">Element</span></span>|<span data-ttu-id="15127-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15127-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15127-116">\<behavior>Natürlich\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="15127-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="15127-117">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="15127-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15127-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15127-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
