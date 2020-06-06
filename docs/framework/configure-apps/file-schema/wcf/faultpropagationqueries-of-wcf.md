---
title: <faultPropagationQueries>von WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855268"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="d3aea-102">\<faultPropagationQueries>von WCF</span><span class="sxs-lookup"><span data-stu-id="d3aea-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="d3aea-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d3aea-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d3aea-104">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d3aea-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d3aea-105">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d3aea-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d3aea-106">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d3aea-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="d3aea-107">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d3aea-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d3aea-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3aea-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3aea-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3aea-109">Attributes and elements</span></span>

<span data-ttu-id="d3aea-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3aea-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d3aea-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3aea-111">Attributes</span></span>

<span data-ttu-id="d3aea-112">Keine</span><span class="sxs-lookup"><span data-stu-id="d3aea-112">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="d3aea-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3aea-113">Child elements</span></span>

|<span data-ttu-id="d3aea-114">Element</span><span class="sxs-lookup"><span data-stu-id="d3aea-114">Element</span></span>|<span data-ttu-id="d3aea-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d3aea-115">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="d3aea-116">Eine Abfrage, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="d3aea-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d3aea-117">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d3aea-117">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3aea-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3aea-118">Parent elements</span></span>  
  
|<span data-ttu-id="d3aea-119">Element</span><span class="sxs-lookup"><span data-stu-id="d3aea-119">Element</span></span>|<span data-ttu-id="d3aea-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d3aea-120">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="d3aea-121">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="d3aea-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3aea-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3aea-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d3aea-123">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d3aea-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d3aea-124">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d3aea-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
