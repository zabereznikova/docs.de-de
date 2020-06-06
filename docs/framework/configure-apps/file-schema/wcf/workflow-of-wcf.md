---
title: <workflow>von WCF
ms.date: 03/30/2017
ms.assetid: c0443eba-d3b4-4fae-886e-9878daf77691
ms.openlocfilehash: c6c9e14a4ad3d9713ae2d35d6ade20690e0c3575
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69932793"
---
# <a name="workflow-of-wcf"></a><span data-ttu-id="c1982-102">\<workflow>von WCF</span><span class="sxs-lookup"><span data-stu-id="c1982-102">\<workflow> of WCF</span></span>
<span data-ttu-id="c1982-103">Konfiguriert einen Nachverfolgungsteilnehmer, der den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauscht und sie entsprechend der Weise verarbeitet, wie er konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c1982-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="c1982-104">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="c1982-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="c1982-105">Weitere Informationen zur Workflow Nachverfolgung und Nachverfolgung von Teilnehmern finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und nach [Verfolgung von Teilnehmern](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="c1982-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 \<system.serviceModel>  
\<tracking>  
\<participants>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="c1982-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1982-106">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1982-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1982-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c1982-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1982-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1982-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1982-109">Attributes</span></span>  
  
|<span data-ttu-id="c1982-110">Element</span><span class="sxs-lookup"><span data-stu-id="c1982-110">Element</span></span>|<span data-ttu-id="c1982-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c1982-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1982-112">name</span><span class="sxs-lookup"><span data-stu-id="c1982-112">name</span></span>|<span data-ttu-id="c1982-113">Eine Zeichenfolge, die den Namen eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="c1982-113">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="c1982-114">profileName</span><span class="sxs-lookup"><span data-stu-id="c1982-114">profileName</span></span>|<span data-ttu-id="c1982-115">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt. Dieses Profil definiert die Nachverfolgungsdatensätze, die der Nachverfolgungsteilnehmer abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="c1982-115">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="c1982-116">type</span><span class="sxs-lookup"><span data-stu-id="c1982-116">type</span></span>|<span data-ttu-id="c1982-117">Eine Zeichenfolge, die den Typ eines Nachverfolgungsteilnehmers angibt.</span><span class="sxs-lookup"><span data-stu-id="c1982-117">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1982-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1982-118">Child Elements</span></span>  
 <span data-ttu-id="c1982-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c1982-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1982-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1982-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c1982-121">Element</span><span class="sxs-lookup"><span data-stu-id="c1982-121">Element</span></span>|<span data-ttu-id="c1982-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c1982-122">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="c1982-123">Eine Liste von Nachverfolgungsteilnehmern</span><span class="sxs-lookup"><span data-stu-id="c1982-123">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1982-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c1982-124">Remarks</span></span>  
 <span data-ttu-id="c1982-125">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c1982-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="c1982-126">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c1982-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="c1982-127">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c1982-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="c1982-128">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="c1982-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="c1982-129">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="c1982-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="c1982-130">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c1982-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="c1982-131">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1982-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="c1982-132">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="c1982-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1982-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1982-133">Example</span></span>  
 <span data-ttu-id="c1982-134">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c1982-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="c1982-135">Die Anbieter-ID, die der ETW-Nachverfolgungsteilnehmer verwendet, um die Nachverfolgungsdatensätze an ETW weiterzuleiten, ist im Abschnitt `<diagnostics>` definiert.</span><span class="sxs-lookup"><span data-stu-id="c1982-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="c1982-136">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="c1982-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="c1982-137">Dieses Profil wird durch das `profileName`-Attribut des `<add>`-Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="c1982-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="c1982-138">Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer dem `<etwTracking>`-Dienstverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c1982-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="c1982-139">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="c1982-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1982-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1982-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="c1982-141">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c1982-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c1982-142">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c1982-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
