---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: d562bd4e3d46a1bdf41fc4065fee926850a49aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152170"
---
# <a name="etwtracking"></a><span data-ttu-id="fe01c-101">\<etwTracking-></span><span class="sxs-lookup"><span data-stu-id="fe01c-101">\<etwTracking></span></span>
<span data-ttu-id="fe01c-102">Ein Dienstverhalten, das einem Dienst ermöglicht, die ETW-Nachverfolgung mit einem <xref:System.Activities.Tracking.EtwTrackingParticipant> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe01c-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="fe01c-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe01c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe01c-104">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe01c-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="fe01c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe01c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="fe01c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe01c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="fe01c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe01c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="fe01c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span><span class="sxs-lookup"><span data-stu-id="fe01c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe01c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe01c-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe01c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe01c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fe01c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe01c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe01c-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="fe01c-112">Attributes</span></span>  
  
|<span data-ttu-id="fe01c-113">attribute</span><span class="sxs-lookup"><span data-stu-id="fe01c-113">Attribute</span></span>|<span data-ttu-id="fe01c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe01c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe01c-115">profileName</span><span class="sxs-lookup"><span data-stu-id="fe01c-115">profileName</span></span>|<span data-ttu-id="fe01c-116">Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="fe01c-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe01c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe01c-117">Child Elements</span></span>  
 <span data-ttu-id="fe01c-118">Keine.</span><span class="sxs-lookup"><span data-stu-id="fe01c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe01c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe01c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fe01c-120">Element</span><span class="sxs-lookup"><span data-stu-id="fe01c-120">Element</span></span>|<span data-ttu-id="fe01c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe01c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe01c-122">\<Verhalten> \<von serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fe01c-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fe01c-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="fe01c-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe01c-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fe01c-124">Remarks</span></span>  
 <span data-ttu-id="fe01c-125">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="fe01c-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="fe01c-126">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fe01c-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="fe01c-127">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="fe01c-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe01c-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe01c-128">Example</span></span>  
 <span data-ttu-id="fe01c-129">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fe01c-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="fe01c-130">Die Anbieter-ID, die der ETW-Tracking-Teilnehmer zum Schreiben der Tracking-Datensätze in ETW verwendet, ist im \*\* \<Abschnitt Diagnose>\*\* definiert.</span><span class="sxs-lookup"><span data-stu-id="fe01c-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="fe01c-131">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="fe01c-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="fe01c-132">Dies wird durch das **attributName** des \*\* \<add>-Elements\*\* definiert.</span><span class="sxs-lookup"><span data-stu-id="fe01c-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="fe01c-133">Sobald diese definiert sind, wird der Tracking-Teilnehmer dem \*\* \<etwTracking->-Dienstverhalten\*\* hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fe01c-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="fe01c-134">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="fe01c-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe01c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe01c-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="fe01c-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="fe01c-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fe01c-137">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="fe01c-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
