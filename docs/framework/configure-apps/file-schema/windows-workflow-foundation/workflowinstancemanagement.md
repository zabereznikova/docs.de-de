---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397518"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="13a79-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="13a79-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="13a79-102">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="13a79-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="13a79-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13a79-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="13a79-104">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="13a79-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="13a79-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="13a79-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="13a79-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="13a79-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="13a79-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="13a79-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="13a79-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowinstancemanagement->**</span><span class="sxs-lookup"><span data-stu-id="13a79-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a79-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="13a79-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13a79-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="13a79-110">Attributes and Elements</span></span>  
 <span data-ttu-id="13a79-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13a79-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13a79-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="13a79-112">Attributes</span></span>  
  
|<span data-ttu-id="13a79-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="13a79-113">Attribute</span></span>|<span data-ttu-id="13a79-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13a79-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13a79-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="13a79-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="13a79-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13a79-116">Child Elements</span></span>  
 <span data-ttu-id="13a79-117">Keine</span><span class="sxs-lookup"><span data-stu-id="13a79-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13a79-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13a79-118">Parent Elements</span></span>  
  
|<span data-ttu-id="13a79-119">Element</span><span class="sxs-lookup"><span data-stu-id="13a79-119">Element</span></span>|<span data-ttu-id="13a79-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13a79-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13a79-121">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="13a79-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="13a79-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="13a79-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13a79-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13a79-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
