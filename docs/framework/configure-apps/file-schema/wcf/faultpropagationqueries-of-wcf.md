---
title: <faultPropagationQueries>von WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855268"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="62944-102">\<"fehlerpropagationqueries"-> von WCF</span><span class="sxs-lookup"><span data-stu-id="62944-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="62944-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="62944-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="62944-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="62944-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="62944-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="62944-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="62944-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="62944-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="62944-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="62944-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="62944-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62944-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62944-109">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="62944-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="62944-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="62944-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="62944-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="62944-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="62944-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="62944-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="62944-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="62944-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="62944-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<"fehlerpropagationqueries"->**</span><span class="sxs-lookup"><span data-stu-id="62944-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62944-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="62944-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62944-116">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62944-116">Attributes and elements</span></span>

<span data-ttu-id="62944-117">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62944-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="62944-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="62944-118">Attributes</span></span>

<span data-ttu-id="62944-119">Keine</span><span class="sxs-lookup"><span data-stu-id="62944-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="62944-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62944-120">Child elements</span></span>

|<span data-ttu-id="62944-121">Element</span><span class="sxs-lookup"><span data-stu-id="62944-121">Element</span></span>|<span data-ttu-id="62944-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62944-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62944-123">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="62944-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="62944-124">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="62944-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="62944-125">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="62944-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62944-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62944-126">Parent elements</span></span>  
  
|<span data-ttu-id="62944-127">Element</span><span class="sxs-lookup"><span data-stu-id="62944-127">Element</span></span>|<span data-ttu-id="62944-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62944-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62944-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="62944-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="62944-130">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="62944-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62944-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62944-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="62944-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="62944-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="62944-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="62944-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
