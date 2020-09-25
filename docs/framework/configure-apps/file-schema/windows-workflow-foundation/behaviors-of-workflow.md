---
title: <behaviors> des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 21974f77526f55a47c014a285efd3bbac6fc1f7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189603"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="4e97e-102">\<behaviors> des Workflows</span><span class="sxs-lookup"><span data-stu-id="4e97e-102">\<behaviors> of workflow</span></span>

<span data-ttu-id="4e97e-103">Dieses Element enthält die **Service** Verhaltens-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="4e97e-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="4e97e-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="4e97e-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="4e97e-105">Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4e97e-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="4e97e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e97e-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e97e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4e97e-107">Attributes and Elements</span></span>  

 <span data-ttu-id="4e97e-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e97e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e97e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="4e97e-109">Attributes</span></span>  

 <span data-ttu-id="4e97e-110">Keine</span><span class="sxs-lookup"><span data-stu-id="4e97e-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e97e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e97e-111">Child Elements</span></span>  
  
|<span data-ttu-id="4e97e-112">Element</span><span class="sxs-lookup"><span data-stu-id="4e97e-112">Element</span></span>|<span data-ttu-id="4e97e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e97e-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="4e97e-114">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="4e97e-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e97e-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e97e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4e97e-116">Element</span><span class="sxs-lookup"><span data-stu-id="4e97e-116">Element</span></span>|<span data-ttu-id="4e97e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e97e-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="4e97e-118">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="4e97e-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e97e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e97e-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="4e97e-120">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="4e97e-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
