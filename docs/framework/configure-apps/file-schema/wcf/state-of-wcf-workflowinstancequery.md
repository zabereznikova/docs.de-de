---
title: <state>von WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854951"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="75826-102">\<state>von WCF,\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="75826-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="75826-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="75826-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="75826-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="75826-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="75826-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="75826-105">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75826-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75826-106">Attributes and elements</span></span>

<span data-ttu-id="75826-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75826-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="75826-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="75826-108">Attributes</span></span>

|<span data-ttu-id="75826-109">attribute</span><span class="sxs-lookup"><span data-stu-id="75826-109">Attribute</span></span>|<span data-ttu-id="75826-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75826-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="75826-111">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="75826-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75826-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75826-112">Child elements</span></span>

<span data-ttu-id="75826-113">Keine</span><span class="sxs-lookup"><span data-stu-id="75826-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="75826-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75826-114">Parent elements</span></span>

|<span data-ttu-id="75826-115">Element</span><span class="sxs-lookup"><span data-stu-id="75826-115">Element</span></span>|<span data-ttu-id="75826-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75826-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="75826-117">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="75826-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75826-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="75826-118">Remarks</span></span>  

<span data-ttu-id="75826-119">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="75826-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="75826-120">Mögliche Zustands Werte werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="75826-120">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="75826-121">Staat</span><span class="sxs-lookup"><span data-stu-id="75826-121">State</span></span>|<span data-ttu-id="75826-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75826-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="75826-123">Aborted</span><span class="sxs-lookup"><span data-stu-id="75826-123">Aborted</span></span>|<span data-ttu-id="75826-124">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="75826-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="75826-125">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="75826-125">Completed</span></span>|<span data-ttu-id="75826-126">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="75826-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="75826-127">Gelöscht</span><span class="sxs-lookup"><span data-stu-id="75826-127">Deleted</span></span>|<span data-ttu-id="75826-128">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="75826-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="75826-129">Idle</span><span class="sxs-lookup"><span data-stu-id="75826-129">Idle</span></span>|<span data-ttu-id="75826-130">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="75826-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="75826-131">Persisted</span><span class="sxs-lookup"><span data-stu-id="75826-131">Persisted</span></span>|<span data-ttu-id="75826-132">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="75826-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="75826-133">Resumed</span><span class="sxs-lookup"><span data-stu-id="75826-133">Resumed</span></span>|<span data-ttu-id="75826-134">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="75826-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="75826-135">Started</span><span class="sxs-lookup"><span data-stu-id="75826-135">Started</span></span>|<span data-ttu-id="75826-136">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="75826-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="75826-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="75826-137">UnhandledException</span></span>|<span data-ttu-id="75826-138">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="75826-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="75826-139">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="75826-139">Unloaded</span></span>|<span data-ttu-id="75826-140">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="75826-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="75826-141">Canceled</span><span class="sxs-lookup"><span data-stu-id="75826-141">Canceled</span></span>|<span data-ttu-id="75826-142">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="75826-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="75826-143">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="75826-143">Suspended</span></span>|<span data-ttu-id="75826-144">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="75826-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="75826-145">Terminated</span><span class="sxs-lookup"><span data-stu-id="75826-145">Terminated</span></span>|<span data-ttu-id="75826-146">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="75826-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="75826-147">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="75826-147">Unsuspended</span></span>|<span data-ttu-id="75826-148">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="75826-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75826-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75826-149">Example</span></span>

<span data-ttu-id="75826-150">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="75826-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="75826-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75826-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="75826-152">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="75826-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="75826-153">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="75826-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
