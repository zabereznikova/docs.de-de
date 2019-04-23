---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: ffc16f78b266b69e80023f177f10ad6f367b5623
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104883"
---
# <a name="participants"></a><span data-ttu-id="36d94-101">\<participants></span><span class="sxs-lookup"><span data-stu-id="36d94-101">\<participants></span></span>
<span data-ttu-id="36d94-102">Konfiguriert eine Liste von Nachverfolgungsteilnehmern, die den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauschen und sie entsprechend der Weise verarbeiten, wie sie konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="36d94-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="36d94-103">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="36d94-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="36d94-104">Weitere Informationen im Workflow-Überwachung und zu nachverfolgungsteilnehmern finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsteilnehmer](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="36d94-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="36d94-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36d94-105">\<system.serviceModel></span></span>  
<span data-ttu-id="36d94-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="36d94-106">\<tracking></span></span>  
<span data-ttu-id="36d94-107">\<participants></span><span class="sxs-lookup"><span data-stu-id="36d94-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d94-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="36d94-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36d94-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="36d94-109">Attributes and Elements</span></span>  
 <span data-ttu-id="36d94-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36d94-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36d94-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="36d94-111">Attributes</span></span>  
 <span data-ttu-id="36d94-112">Keine</span><span class="sxs-lookup"><span data-stu-id="36d94-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36d94-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36d94-113">Child Elements</span></span>  
  
|<span data-ttu-id="36d94-114">Element</span><span class="sxs-lookup"><span data-stu-id="36d94-114">Element</span></span>|<span data-ttu-id="36d94-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36d94-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d94-116">\<add></span><span class="sxs-lookup"><span data-stu-id="36d94-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="36d94-117">Enthält Einstellungen für einen Nachverfolgungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="36d94-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36d94-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36d94-118">Parent Elements</span></span>  
  
|<span data-ttu-id="36d94-119">Element</span><span class="sxs-lookup"><span data-stu-id="36d94-119">Element</span></span>|<span data-ttu-id="36d94-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36d94-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d94-121">\<tracking></span><span class="sxs-lookup"><span data-stu-id="36d94-121">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="36d94-122">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="36d94-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d94-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36d94-123">Remarks</span></span>  
 <span data-ttu-id="36d94-124">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="36d94-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="36d94-125">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="36d94-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="36d94-126">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="36d94-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="36d94-127">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="36d94-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="36d94-128">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="36d94-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="36d94-129">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="36d94-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="36d94-130">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="36d94-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="36d94-131">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="36d94-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36d94-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36d94-132">Example</span></span>  
 <span data-ttu-id="36d94-133">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="36d94-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="36d94-134">Die Anbieter-Id, die ETW-Nachverfolgungsteilnehmer verwendet wird, für die Nachverfolgungsdatensätze an ETW, wird definiert, der  **\<Diagnose >** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="36d94-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="36d94-135">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="36d94-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="36d94-136">Dadurch wird definiert, indem die **ProfileName** Attribut der  **\<hinzufügen >** Element.</span><span class="sxs-lookup"><span data-stu-id="36d94-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="36d94-137">Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer hinzugefügt, um die  **\<EtwTracking >** -Dienstverhalten.</span><span class="sxs-lookup"><span data-stu-id="36d94-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="36d94-138">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="36d94-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="36d94-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36d94-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="36d94-140">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="36d94-140">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="36d94-141">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="36d94-141">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
