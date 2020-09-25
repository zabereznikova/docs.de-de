---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 24e9136729df1352ebb1e665d1ebaf0ce9dc28a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175836"
---
# \<faultPropagationQueries>

<span data-ttu-id="f4f48-101">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="f4f48-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4f48-102">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f4f48-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f4f48-103">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="f4f48-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f4f48-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f4f48-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="f4f48-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f4f48-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="f4f48-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4f48-106">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4f48-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f4f48-107">Attributes and Elements</span></span>  

 <span data-ttu-id="f4f48-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4f48-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4f48-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4f48-109">Attributes</span></span>  

 <span data-ttu-id="f4f48-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f4f48-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4f48-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4f48-111">Child Elements</span></span>  
  
|<span data-ttu-id="f4f48-112">Element</span><span class="sxs-lookup"><span data-stu-id="f4f48-112">Element</span></span>|<span data-ttu-id="f4f48-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4f48-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="f4f48-114">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="f4f48-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f4f48-115">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f4f48-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f4f48-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4f48-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f4f48-117">Element</span><span class="sxs-lookup"><span data-stu-id="f4f48-117">Element</span></span>|<span data-ttu-id="f4f48-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4f48-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="f4f48-119">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="f4f48-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4f48-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4f48-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f4f48-121">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f4f48-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f4f48-122">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="f4f48-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
