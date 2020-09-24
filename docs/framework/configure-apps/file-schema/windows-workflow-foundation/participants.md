---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: 51c7824a4dcbd95eac098d25e9a971514e2a1e0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167040"
---
# \<participants>

<span data-ttu-id="eb96a-101">Konfiguriert eine Liste von Nachverfolgungsteilnehmern, die den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauschen und sie entsprechend der Weise verarbeiten, wie sie konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="eb96a-101">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="eb96a-102">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="eb96a-102">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="eb96a-103">Weitere Informationen zur Workflow Nachverfolgung und Nachverfolgung von Teilnehmern finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und nach [Verfolgung von Teilnehmern](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="eb96a-103">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**  
  
## <a name="syntax"></a><span data-ttu-id="eb96a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb96a-104">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb96a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb96a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eb96a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb96a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb96a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb96a-107">Attributes</span></span>  

 <span data-ttu-id="eb96a-108">Keine</span><span class="sxs-lookup"><span data-stu-id="eb96a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb96a-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb96a-109">Child Elements</span></span>  
  
|<span data-ttu-id="eb96a-110">Element</span><span class="sxs-lookup"><span data-stu-id="eb96a-110">Element</span></span>|<span data-ttu-id="eb96a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb96a-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-participants.md)|<span data-ttu-id="eb96a-112">Enthält Einstellungen für einen Nachverfolgungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="eb96a-112">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb96a-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb96a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="eb96a-114">Element</span><span class="sxs-lookup"><span data-stu-id="eb96a-114">Element</span></span>|<span data-ttu-id="eb96a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb96a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<tracking>](tracking.md)|<span data-ttu-id="eb96a-116">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="eb96a-116">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb96a-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eb96a-117">Remarks</span></span>  

 <span data-ttu-id="eb96a-118">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb96a-118">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="eb96a-119">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="eb96a-119">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="eb96a-120">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="eb96a-120">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="eb96a-121">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="eb96a-121">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="eb96a-122">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="eb96a-122">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="eb96a-123">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="eb96a-123">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="eb96a-124">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb96a-124">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="eb96a-125">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="eb96a-125">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb96a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb96a-126">Example</span></span>  

 <span data-ttu-id="eb96a-127">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="eb96a-127">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="eb96a-128">Die Anbieter-ID, die der etw-Überwachungs Teilnehmer zum Schreiben der nach Verfolgungs Datensätze in etw verwendet, ist im **\<diagnostics>** Abschnitt definiert.</span><span class="sxs-lookup"><span data-stu-id="eb96a-128">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="eb96a-129">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="eb96a-129">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="eb96a-130">Dies wird durch das **ProfileName** -Attribut des- **\<add>** Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="eb96a-130">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="eb96a-131">Nachdem diese definiert wurden, wird dem Dienst Verhalten der nach Verfolgungs Teilnehmer hinzugefügt **\<etwTracking>** .</span><span class="sxs-lookup"><span data-stu-id="eb96a-131">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="eb96a-132">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="eb96a-132">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb96a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb96a-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="eb96a-134">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="eb96a-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eb96a-135">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="eb96a-135">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
