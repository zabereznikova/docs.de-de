---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 532d4c31a582b2b0cd90f6f42b20e00790f9ab02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148658"
---
# \<workflowInstanceManagement>

<span data-ttu-id="9a879-101">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="9a879-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="9a879-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a879-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a879-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a879-103">Attributes and Elements</span></span>  

 <span data-ttu-id="9a879-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a879-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a879-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a879-105">Attributes</span></span>  
  
|<span data-ttu-id="9a879-106">attribute</span><span class="sxs-lookup"><span data-stu-id="9a879-106">Attribute</span></span>|<span data-ttu-id="9a879-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a879-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a879-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="9a879-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="9a879-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a879-109">Child Elements</span></span>  

 <span data-ttu-id="9a879-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9a879-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a879-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a879-111">Parent Elements</span></span>  
  
|<span data-ttu-id="9a879-112">Element</span><span class="sxs-lookup"><span data-stu-id="9a879-112">Element</span></span>|<span data-ttu-id="9a879-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a879-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a879-114">\<behavior> von \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9a879-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="9a879-115">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="9a879-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a879-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a879-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
