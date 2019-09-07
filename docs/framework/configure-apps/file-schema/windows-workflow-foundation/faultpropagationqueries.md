---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398731"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="020bc-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="020bc-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="020bc-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="020bc-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="020bc-103">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="020bc-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="020bc-104">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="020bc-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="020bc-105">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="020bc-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="020bc-106">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="020bc-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="020bc-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="020bc-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="020bc-108">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="020bc-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="020bc-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="020bc-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="020bc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="020bc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="020bc-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="020bc-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="020bc-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<"fehlerpropagationqueries"->**</span><span class="sxs-lookup"><span data-stu-id="020bc-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="020bc-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="020bc-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="020bc-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="020bc-114">Attributes and Elements</span></span>  
 <span data-ttu-id="020bc-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="020bc-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="020bc-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="020bc-116">Attributes</span></span>  
 <span data-ttu-id="020bc-117">Keine</span><span class="sxs-lookup"><span data-stu-id="020bc-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="020bc-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="020bc-118">Child Elements</span></span>  
  
|<span data-ttu-id="020bc-119">Element</span><span class="sxs-lookup"><span data-stu-id="020bc-119">Element</span></span>|<span data-ttu-id="020bc-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="020bc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="020bc-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="020bc-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="020bc-122">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="020bc-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="020bc-123">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="020bc-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="020bc-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="020bc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="020bc-125">Element</span><span class="sxs-lookup"><span data-stu-id="020bc-125">Element</span></span>|<span data-ttu-id="020bc-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="020bc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="020bc-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="020bc-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="020bc-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="020bc-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="020bc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="020bc-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="020bc-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="020bc-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="020bc-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="020bc-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
