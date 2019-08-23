---
title: <add> von <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: a6dc07b6f419fcb98e3f182269a99cb281139ba9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946195"
---
# <a name="add-of-participants"></a><span data-ttu-id="90bc4-102">\<> der \<Teilnehmer hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="90bc4-102">\<add> of \<participants></span></span>
<span data-ttu-id="90bc4-103">Konfiguriert einen Nachverfolgungsteilnehmer, der den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauscht und sie entsprechend der Weise verarbeitet, wie er konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="90bc4-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="90bc4-104">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="90bc4-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="90bc4-105">Weitere Informationen zur Workflow Nachverfolgung und Nachverfolgung von Teilnehmern finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und nach [Verfolgung von Teilnehmern](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="90bc4-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="90bc4-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90bc4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="90bc4-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="90bc4-107">\<tracking></span></span>  
<span data-ttu-id="90bc4-108">\<Teilnehmer ></span><span class="sxs-lookup"><span data-stu-id="90bc4-108">\<participants></span></span>  
<span data-ttu-id="90bc4-109">\<add></span><span class="sxs-lookup"><span data-stu-id="90bc4-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90bc4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="90bc4-110">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90bc4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90bc4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="90bc4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90bc4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90bc4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="90bc4-113">Attributes</span></span>  
  
|<span data-ttu-id="90bc4-114">Element</span><span class="sxs-lookup"><span data-stu-id="90bc4-114">Element</span></span>|<span data-ttu-id="90bc4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90bc4-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90bc4-116">Name</span><span class="sxs-lookup"><span data-stu-id="90bc4-116">name</span></span>|<span data-ttu-id="90bc4-117">Eine Zeichenfolge, die den Namen eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="90bc4-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="90bc4-118">profileName</span><span class="sxs-lookup"><span data-stu-id="90bc4-118">profileName</span></span>|<span data-ttu-id="90bc4-119">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt. Dieses Profil definiert die Nachverfolgungsdatensätze, die der Nachverfolgungsteilnehmer abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="90bc4-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="90bc4-120">Typ</span><span class="sxs-lookup"><span data-stu-id="90bc4-120">type</span></span>|<span data-ttu-id="90bc4-121">Eine Zeichenfolge, die den Typ eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="90bc4-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90bc4-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90bc4-122">Child Elements</span></span>  
 <span data-ttu-id="90bc4-123">Keine</span><span class="sxs-lookup"><span data-stu-id="90bc4-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90bc4-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90bc4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="90bc4-125">Element</span><span class="sxs-lookup"><span data-stu-id="90bc4-125">Element</span></span>|<span data-ttu-id="90bc4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90bc4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90bc4-127">\<participants></span><span class="sxs-lookup"><span data-stu-id="90bc4-127">\<participants></span></span>](participants.md)|<span data-ttu-id="90bc4-128">Eine Liste von Nachverfolgungsteilnehmern</span><span class="sxs-lookup"><span data-stu-id="90bc4-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90bc4-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90bc4-129">Remarks</span></span>  
 <span data-ttu-id="90bc4-130">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="90bc4-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="90bc4-131">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="90bc4-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="90bc4-132">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="90bc4-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="90bc4-133">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="90bc4-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="90bc4-134">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="90bc4-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="90bc4-135">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="90bc4-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="90bc4-136">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="90bc4-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="90bc4-137">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="90bc4-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90bc4-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90bc4-138">Example</span></span>  
 <span data-ttu-id="90bc4-139">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="90bc4-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="90bc4-140">Die Anbieter-ID, die der etw-Überwachungs Teilnehmer zum Schreiben der nach Verfolgungs Datensätze in etw verwendet, ist im  **\<Abschnitt Diagnose >** definiert.</span><span class="sxs-lookup"><span data-stu-id="90bc4-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="90bc4-141">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="90bc4-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="90bc4-142">Dies wird durch das **ProfileName** -Attribut des  **\<Add >** -Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="90bc4-142">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="90bc4-143">Nachdem diese definiert wurden, wird der nach Verfolgungs Teilnehmer dem  **\<etwtracking->** Dienst Verhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="90bc4-143">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="90bc4-144">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="90bc4-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90bc4-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90bc4-145">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="90bc4-146">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="90bc4-146">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="90bc4-147">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="90bc4-147">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
