---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: d9b40551233f3b22db7953f1980aaf99b0ee8ae9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185352"
---
# \<variable>

<span data-ttu-id="bcd50-101">Stellt eine Auflistung von Variablen dar, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bcd50-101">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="bcd50-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bcd50-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**  
  
## <a name="syntax"></a><span data-ttu-id="bcd50-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcd50-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcd50-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bcd50-104">Attributes and Elements</span></span>  

 <span data-ttu-id="bcd50-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bcd50-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcd50-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="bcd50-106">Attributes</span></span>  
  
|<span data-ttu-id="bcd50-107">attribute</span><span class="sxs-lookup"><span data-stu-id="bcd50-107">Attribute</span></span>|<span data-ttu-id="bcd50-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcd50-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcd50-109">name</span><span class="sxs-lookup"><span data-stu-id="bcd50-109">name</span></span>|<span data-ttu-id="bcd50-110">Eine Zeichenfolge, die den Namen der Variablen angibt.</span><span class="sxs-lookup"><span data-stu-id="bcd50-110">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcd50-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bcd50-111">Child Elements</span></span>  

 <span data-ttu-id="bcd50-112">Keine</span><span class="sxs-lookup"><span data-stu-id="bcd50-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcd50-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bcd50-113">Parent Elements</span></span>  
  
|<span data-ttu-id="bcd50-114">Element</span><span class="sxs-lookup"><span data-stu-id="bcd50-114">Element</span></span>|<span data-ttu-id="bcd50-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcd50-115">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="bcd50-116">Eine einer Aktivitätszustandsabfrage zugeordnete Variable.</span><span class="sxs-lookup"><span data-stu-id="bcd50-116">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcd50-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bcd50-117">Remarks</span></span>  

 <span data-ttu-id="bcd50-118">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="bcd50-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="bcd50-119">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="bcd50-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="bcd50-120">Sie können die [\<arguments>](arguments.md) Elemente, [\<states>](states.md) und verwenden [\<states>](states.md) , um beliebige Variablen oder Argumente aus beliebigen Aktivitäten in einem Workflow zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="bcd50-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="bcd50-121">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bcd50-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="bcd50-122">Variablen und Argumente können nur mit einem activitystatus erecord extrahiert werden und können daher innerhalb eines Überwachungs Profils mit abonniert werden [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="bcd50-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bcd50-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcd50-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bcd50-124">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="bcd50-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bcd50-125">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="bcd50-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
