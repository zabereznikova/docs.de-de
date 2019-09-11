---
title: <add>von WCF
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: 0b21bdabc76ec4853a0f2664cdd3cead149417a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850300"
---
# <a name="add-of-wcf"></a><span data-ttu-id="657ef-102">\<> von WCF hinzufügen</span><span class="sxs-lookup"><span data-stu-id="657ef-102">\<add> of WCF</span></span>
<span data-ttu-id="657ef-103">Konfiguriert einen Nachverfolgungsteilnehmer, der den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauscht und sie entsprechend der Weise verarbeitet, wie er konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="657ef-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="657ef-104">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="657ef-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="657ef-105">Weitere Informationen zur Workflow Nachverfolgung und Nachverfolgung von Teilnehmern finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und nach [Verfolgung von Teilnehmern](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="657ef-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="657ef-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="657ef-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="657ef-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="657ef-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="657ef-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="657ef-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="657ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Teilnehmer >** ](participants-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="657ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants-of-wcf.md)</span></span>\
<span data-ttu-id="657ef-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="657ef-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657ef-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="657ef-111">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="657ef-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="657ef-112">Attributes and Elements</span></span>  
 <span data-ttu-id="657ef-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="657ef-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="657ef-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="657ef-114">Attributes</span></span>  
  
|<span data-ttu-id="657ef-115">Element</span><span class="sxs-lookup"><span data-stu-id="657ef-115">Element</span></span>|<span data-ttu-id="657ef-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="657ef-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="657ef-117">NAME</span><span class="sxs-lookup"><span data-stu-id="657ef-117">name</span></span>|<span data-ttu-id="657ef-118">Eine Zeichenfolge, die den Namen eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="657ef-118">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="657ef-119">profileName</span><span class="sxs-lookup"><span data-stu-id="657ef-119">profileName</span></span>|<span data-ttu-id="657ef-120">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt. Dieses Profil definiert die Nachverfolgungsdatensätze, die der Nachverfolgungsteilnehmer abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="657ef-120">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="657ef-121">Typ</span><span class="sxs-lookup"><span data-stu-id="657ef-121">type</span></span>|<span data-ttu-id="657ef-122">Eine Zeichenfolge, die den Typ eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="657ef-122">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="657ef-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="657ef-123">Child Elements</span></span>  
 <span data-ttu-id="657ef-124">Keine</span><span class="sxs-lookup"><span data-stu-id="657ef-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="657ef-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="657ef-125">Parent Elements</span></span>  
  
|<span data-ttu-id="657ef-126">Element</span><span class="sxs-lookup"><span data-stu-id="657ef-126">Element</span></span>|<span data-ttu-id="657ef-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="657ef-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="657ef-128">\<participants></span><span class="sxs-lookup"><span data-stu-id="657ef-128">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="657ef-129">Eine Liste von Nachverfolgungsteilnehmern</span><span class="sxs-lookup"><span data-stu-id="657ef-129">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="657ef-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="657ef-130">Remarks</span></span>  
 <span data-ttu-id="657ef-131">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="657ef-131">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="657ef-132">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="657ef-132">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="657ef-133">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="657ef-133">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="657ef-134">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="657ef-134">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="657ef-135">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="657ef-135">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="657ef-136">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="657ef-136">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="657ef-137">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="657ef-137">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="657ef-138">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="657ef-138">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="657ef-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="657ef-139">Example</span></span>  
 <span data-ttu-id="657ef-140">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="657ef-140">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="657ef-141">Die Anbieter-ID, die der ETW-Nachverfolgungsteilnehmer verwendet, um die Nachverfolgungsdatensätze an ETW weiterzuleiten, ist im Abschnitt `<diagnostics>` definiert.</span><span class="sxs-lookup"><span data-stu-id="657ef-141">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="657ef-142">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="657ef-142">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="657ef-143">Dieses Profil wird durch das `profileName`-Attribut des `<add>`-Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="657ef-143">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="657ef-144">Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer dem `<etwTracking>`-Dienstverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="657ef-144">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="657ef-145">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="657ef-145">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="657ef-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="657ef-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="657ef-147">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="657ef-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="657ef-148">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="657ef-148">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
