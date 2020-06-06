---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398908"
---
# \<argument>
<span data-ttu-id="abe7c-101">Ein Konfigurationselement, das ein einer Aktivitätszustandsabfrage zugeordnetes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="abe7c-101">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="abe7c-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="abe7c-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**  
  
## <a name="syntax"></a><span data-ttu-id="abe7c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="abe7c-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abe7c-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="abe7c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="abe7c-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="abe7c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abe7c-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="abe7c-106">Attributes</span></span>  
  
|<span data-ttu-id="abe7c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="abe7c-107">Attribute</span></span>|<span data-ttu-id="abe7c-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="abe7c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abe7c-109">name</span><span class="sxs-lookup"><span data-stu-id="abe7c-109">name</span></span>|<span data-ttu-id="abe7c-110">Eine Zeichenfolge, die den Namen des Arguments angibt.</span><span class="sxs-lookup"><span data-stu-id="abe7c-110">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abe7c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="abe7c-111">Child Elements</span></span>  
 <span data-ttu-id="abe7c-112">Keine</span><span class="sxs-lookup"><span data-stu-id="abe7c-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abe7c-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="abe7c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="abe7c-114">Element</span><span class="sxs-lookup"><span data-stu-id="abe7c-114">Element</span></span>|<span data-ttu-id="abe7c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abe7c-115">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="abe7c-116">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="abe7c-116">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abe7c-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="abe7c-117">Remarks</span></span>  
 <span data-ttu-id="abe7c-118">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="abe7c-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="abe7c-119">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="abe7c-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="abe7c-120">Sie können die [\<arguments>](arguments.md) Elemente, [\<states>](states.md) und verwenden [\<states>](states.md) , um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="abe7c-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="abe7c-121">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="abe7c-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="abe7c-122">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mit abonniert werden [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="abe7c-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="abe7c-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abe7c-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="abe7c-124">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="abe7c-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="abe7c-125">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="abe7c-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
