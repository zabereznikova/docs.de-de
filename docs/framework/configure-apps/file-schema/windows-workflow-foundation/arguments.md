---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: f06a2188ea3561437c1453d3a1cb23d42d767f53
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398913"
---
# \<arguments>
<span data-ttu-id="50c82-101">Stellt eine Auflistung von Argumenten dar, die einer Aktivitätszustandsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="50c82-101">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="50c82-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="50c82-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**  
  
## <a name="syntax"></a><span data-ttu-id="50c82-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="50c82-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50c82-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="50c82-104">Attributes and Elements</span></span>  
 <span data-ttu-id="50c82-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50c82-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50c82-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="50c82-106">Attributes</span></span>  
 <span data-ttu-id="50c82-107">Keine</span><span class="sxs-lookup"><span data-stu-id="50c82-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50c82-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50c82-108">Child Elements</span></span>  
  
|<span data-ttu-id="50c82-109">Element</span><span class="sxs-lookup"><span data-stu-id="50c82-109">Element</span></span>|<span data-ttu-id="50c82-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50c82-110">Description</span></span>|  
|-------------|-----------------|  
|[\<argument>](argument.md)|<span data-ttu-id="50c82-111">Ein einer Aktivitätszustandsabfrage zugeordnetes Argument.</span><span class="sxs-lookup"><span data-stu-id="50c82-111">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50c82-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50c82-112">Parent Elements</span></span>  
  
|<span data-ttu-id="50c82-113">Element</span><span class="sxs-lookup"><span data-stu-id="50c82-113">Element</span></span>|<span data-ttu-id="50c82-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50c82-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="50c82-115">Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="50c82-115">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="50c82-116">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="50c82-116">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50c82-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="50c82-117">Remarks</span></span>  
 <span data-ttu-id="50c82-118">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="50c82-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="50c82-119">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="50c82-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="50c82-120">Sie können die [\<arguments>](arguments.md) Elemente, [\<states>](states.md) und verwenden [\<states>](states.md) , um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="50c82-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="50c82-121">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50c82-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="50c82-122">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mit abonniert werden [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="50c82-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50c82-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50c82-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="50c82-124">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="50c82-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="50c82-125">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="50c82-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
