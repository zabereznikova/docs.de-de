---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 6e3993e43aac746f380a30341fe4ebffcd257c5f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148515"
---
# \<workflowUnhandledException>

<span data-ttu-id="0e6d5-101">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="0e6d5-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="0e6d5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e6d5-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e6d5-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e6d5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0e6d5-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e6d5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e6d5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e6d5-105">Attributes</span></span>  
  
|<span data-ttu-id="0e6d5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0e6d5-106">Attribute</span></span>|<span data-ttu-id="0e6d5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e6d5-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e6d5-108">action</span><span class="sxs-lookup"><span data-stu-id="0e6d5-108">action</span></span>|<span data-ttu-id="0e6d5-109">Eine Zeichenfolge, die die Aktion angibt, die ausgeführt wird, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="0e6d5-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="0e6d5-110">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="0e6d5-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e6d5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e6d5-111">Child Elements</span></span>  

 <span data-ttu-id="0e6d5-112">Keine</span><span class="sxs-lookup"><span data-stu-id="0e6d5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e6d5-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e6d5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0e6d5-114">Element</span><span class="sxs-lookup"><span data-stu-id="0e6d5-114">Element</span></span>|<span data-ttu-id="0e6d5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e6d5-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e6d5-116">\<behavior> von \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0e6d5-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0e6d5-117">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="0e6d5-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e6d5-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e6d5-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
