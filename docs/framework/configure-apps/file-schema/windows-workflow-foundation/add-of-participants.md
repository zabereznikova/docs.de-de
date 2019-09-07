---
title: <add> von <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 479430abd06561cc294b3da3d0922b737364b50f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398934"
---
# <a name="add-of-participants"></a><span data-ttu-id="60b28-102">\<> der \<Teilnehmer hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="60b28-102">\<add> of \<participants></span></span>
<span data-ttu-id="60b28-103">Konfiguriert einen Nachverfolgungsteilnehmer, der den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauscht und sie entsprechend der Weise verarbeitet, wie er konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="60b28-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="60b28-104">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="60b28-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="60b28-105">Weitere Informationen zur Workflow Nachverfolgung und Nachverfolgung von Teilnehmern finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und nach [Verfolgung von Teilnehmern](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="60b28-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="60b28-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60b28-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60b28-107">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="60b28-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="60b28-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="60b28-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="60b28-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Teilnehmer >** ](participants.md)</span><span class="sxs-lookup"><span data-stu-id="60b28-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants.md)</span></span>\
<span data-ttu-id="60b28-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="60b28-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b28-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="60b28-111">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60b28-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="60b28-112">Attributes and Elements</span></span>  
 <span data-ttu-id="60b28-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60b28-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60b28-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="60b28-114">Attributes</span></span>  
  
|<span data-ttu-id="60b28-115">Element</span><span class="sxs-lookup"><span data-stu-id="60b28-115">Element</span></span>|<span data-ttu-id="60b28-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60b28-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60b28-117">Name</span><span class="sxs-lookup"><span data-stu-id="60b28-117">name</span></span>|<span data-ttu-id="60b28-118">Eine Zeichenfolge, die den Namen eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="60b28-118">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="60b28-119">profileName</span><span class="sxs-lookup"><span data-stu-id="60b28-119">profileName</span></span>|<span data-ttu-id="60b28-120">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt. Dieses Profil definiert die Nachverfolgungsdatensätze, die der Nachverfolgungsteilnehmer abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="60b28-120">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="60b28-121">Typ</span><span class="sxs-lookup"><span data-stu-id="60b28-121">type</span></span>|<span data-ttu-id="60b28-122">Eine Zeichenfolge, die den Typ eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="60b28-122">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60b28-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60b28-123">Child Elements</span></span>  
 <span data-ttu-id="60b28-124">Keine</span><span class="sxs-lookup"><span data-stu-id="60b28-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60b28-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60b28-125">Parent Elements</span></span>  
  
|<span data-ttu-id="60b28-126">Element</span><span class="sxs-lookup"><span data-stu-id="60b28-126">Element</span></span>|<span data-ttu-id="60b28-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60b28-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60b28-128">\<participants></span><span class="sxs-lookup"><span data-stu-id="60b28-128">\<participants></span></span>](participants.md)|<span data-ttu-id="60b28-129">Eine Liste von Nachverfolgungsteilnehmern</span><span class="sxs-lookup"><span data-stu-id="60b28-129">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60b28-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60b28-130">Remarks</span></span>  
 <span data-ttu-id="60b28-131">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="60b28-131">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="60b28-132">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="60b28-132">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="60b28-133">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="60b28-133">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="60b28-134">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="60b28-134">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="60b28-135">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="60b28-135">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="60b28-136">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="60b28-136">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="60b28-137">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="60b28-137">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="60b28-138">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="60b28-138">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60b28-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60b28-139">Example</span></span>  
 <span data-ttu-id="60b28-140">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="60b28-140">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="60b28-141">Die Anbieter-ID, die der etw-Überwachungs Teilnehmer zum Schreiben der nach Verfolgungs Datensätze in etw verwendet, ist im  **\<Abschnitt Diagnose >** definiert.</span><span class="sxs-lookup"><span data-stu-id="60b28-141">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="60b28-142">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="60b28-142">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="60b28-143">Dies wird durch das **ProfileName** -Attribut des  **\<Add >** -Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="60b28-143">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="60b28-144">Nachdem diese definiert wurden, wird der nach Verfolgungs Teilnehmer dem  **\<etwtracking->** Dienst Verhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60b28-144">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="60b28-145">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="60b28-145">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60b28-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60b28-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="60b28-147">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="60b28-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="60b28-148">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="60b28-148">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
