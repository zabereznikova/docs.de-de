---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 094fbf95042c00287fb8dfcca28753cfe501a8d8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398755"
---
# <a name="etwtracking"></a><span data-ttu-id="f318d-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="f318d-101">\<etwTracking></span></span>
<span data-ttu-id="f318d-102">Ein Dienst Verhalten, das einem Dienst ermöglicht, die ETW-nach <xref:System.Activities.Tracking.EtwTrackingParticipant>Verfolgung mit einem zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f318d-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="f318d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f318d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f318d-104">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f318d-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="f318d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f318d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="f318d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f318d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="f318d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f318d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="f318d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<etwtracking->**</span><span class="sxs-lookup"><span data-stu-id="f318d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f318d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f318d-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f318d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f318d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f318d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f318d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f318d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f318d-112">Attributes</span></span>  
  
|<span data-ttu-id="f318d-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f318d-113">Attribute</span></span>|<span data-ttu-id="f318d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f318d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f318d-115">profileName</span><span class="sxs-lookup"><span data-stu-id="f318d-115">profileName</span></span>|<span data-ttu-id="f318d-116">Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="f318d-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f318d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f318d-117">Child Elements</span></span>  
 <span data-ttu-id="f318d-118">Keine</span><span class="sxs-lookup"><span data-stu-id="f318d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f318d-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f318d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f318d-120">Element</span><span class="sxs-lookup"><span data-stu-id="f318d-120">Element</span></span>|<span data-ttu-id="f318d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f318d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f318d-122">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="f318d-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="f318d-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="f318d-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f318d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f318d-124">Remarks</span></span>  
 <span data-ttu-id="f318d-125">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="f318d-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="f318d-126">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f318d-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="f318d-127">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f318d-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f318d-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f318d-128">Example</span></span>  
 <span data-ttu-id="f318d-129">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f318d-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="f318d-130">Die Anbieter-ID, die der etw-Überwachungs Teilnehmer zum Schreiben der nach Verfolgungs Datensätze in etw verwendet, ist im  **\<Abschnitt Diagnose >** definiert.</span><span class="sxs-lookup"><span data-stu-id="f318d-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="f318d-131">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="f318d-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="f318d-132">Dies wird durch das **ProfileName** -Attribut des  **\<Add >** -Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="f318d-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="f318d-133">Nachdem diese definiert wurden, wird der nach Verfolgungs Teilnehmer dem  **\<etwtracking->** Dienst Verhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f318d-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="f318d-134">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="f318d-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f318d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f318d-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="f318d-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f318d-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f318d-137">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="f318d-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
