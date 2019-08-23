---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 653693fef92072cb1e6e23234359b765f0f18fc9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940231"
---
# <a name="etwtracking"></a><span data-ttu-id="118da-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="118da-101">\<etwTracking></span></span>
<span data-ttu-id="118da-102">Ein Dienst Verhalten, das einem Dienst ermöglicht, die ETW-nach <xref:System.Activities.Tracking.EtwTrackingParticipant>Verfolgung mit einem zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="118da-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="118da-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="118da-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="118da-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="118da-104">\<behaviors></span></span>  
<span data-ttu-id="118da-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="118da-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="118da-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="118da-106">\<behavior></span></span>  
<span data-ttu-id="118da-107">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="118da-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118da-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="118da-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="118da-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="118da-109">Attributes and Elements</span></span>  
 <span data-ttu-id="118da-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="118da-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="118da-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="118da-111">Attributes</span></span>  
  
|<span data-ttu-id="118da-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="118da-112">Attribute</span></span>|<span data-ttu-id="118da-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="118da-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="118da-114">profileName</span><span class="sxs-lookup"><span data-stu-id="118da-114">profileName</span></span>|<span data-ttu-id="118da-115">Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="118da-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="118da-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="118da-116">Child Elements</span></span>  
 <span data-ttu-id="118da-117">Keine</span><span class="sxs-lookup"><span data-stu-id="118da-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="118da-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="118da-118">Parent Elements</span></span>  
  
|<span data-ttu-id="118da-119">Element</span><span class="sxs-lookup"><span data-stu-id="118da-119">Element</span></span>|<span data-ttu-id="118da-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="118da-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="118da-121">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="118da-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="118da-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="118da-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="118da-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="118da-123">Remarks</span></span>  
 <span data-ttu-id="118da-124">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="118da-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="118da-125">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="118da-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="118da-126">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="118da-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="118da-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="118da-127">Example</span></span>  
 <span data-ttu-id="118da-128">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="118da-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="118da-129">Die Anbieter-ID, die der etw-Überwachungs Teilnehmer zum Schreiben der nach Verfolgungs Datensätze in etw verwendet, ist im  **\<Abschnitt Diagnose >** definiert.</span><span class="sxs-lookup"><span data-stu-id="118da-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="118da-130">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="118da-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="118da-131">Dies wird durch das **ProfileName** -Attribut des  **\<Add >** -Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="118da-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="118da-132">Nachdem diese definiert wurden, wird der nach Verfolgungs Teilnehmer dem  **\<etwtracking->** Dienst Verhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="118da-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="118da-133">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="118da-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="118da-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="118da-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="118da-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="118da-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="118da-136">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="118da-136">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
