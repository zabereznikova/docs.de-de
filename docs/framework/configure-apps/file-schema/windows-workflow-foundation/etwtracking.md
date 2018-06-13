---
title: '&lt;etwTracking&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 6defccdd6a81a1c00a4b65fa9214c86e6cccbea2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756744"
---
# <a name="ltetwtrackinggt"></a><span data-ttu-id="0e674-102">&lt;etwTracking&gt;</span><span class="sxs-lookup"><span data-stu-id="0e674-102">&lt;etwTracking&gt;</span></span>
<span data-ttu-id="0e674-103">Ein Dienstverhalten, das einen Dienst für die Nutzung von ETW-nachverfolgung mit ermöglicht eine <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="0e674-103">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="0e674-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e674-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e674-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0e674-105">\<behaviors></span></span>  
<span data-ttu-id="0e674-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0e674-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0e674-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0e674-107">\<behavior></span></span>  
<span data-ttu-id="0e674-108">\<EtwTracking ></span><span class="sxs-lookup"><span data-stu-id="0e674-108">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e674-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e674-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e674-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e674-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0e674-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e674-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e674-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e674-112">Attributes</span></span>  
  
|<span data-ttu-id="0e674-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0e674-113">Attribute</span></span>|<span data-ttu-id="0e674-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e674-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e674-115">profileName</span><span class="sxs-lookup"><span data-stu-id="0e674-115">profileName</span></span>|<span data-ttu-id="0e674-116">Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="0e674-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e674-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e674-117">Child Elements</span></span>  
 <span data-ttu-id="0e674-118">Keine</span><span class="sxs-lookup"><span data-stu-id="0e674-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e674-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e674-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0e674-120">Element</span><span class="sxs-lookup"><span data-stu-id="0e674-120">Element</span></span>|<span data-ttu-id="0e674-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e674-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e674-122">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0e674-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0e674-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="0e674-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e674-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e674-124">Remarks</span></span>  
 <span data-ttu-id="0e674-125">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="0e674-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="0e674-126">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0e674-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="0e674-127">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="0e674-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e674-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e674-128">Example</span></span>  
 <span data-ttu-id="0e674-129">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0e674-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="0e674-130">Die Anbieter-Id, die ETW-Nachverfolgungsteilnehmer verwendet, für die Nachverfolgungsdatensätze an ETW wird definiert, der  **\<Diagnose >** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0e674-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="0e674-131">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="0e674-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="0e674-132">Dies wird definiert, indem die **ProfileName** Attribut des der  **\<hinzufügen >** Element.</span><span class="sxs-lookup"><span data-stu-id="0e674-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="0e674-133">Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer hinzugefügt, um die  **\<EtwTracking >** -Dienstverhalten.</span><span class="sxs-lookup"><span data-stu-id="0e674-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="0e674-134">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="0e674-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e674-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e674-135">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="0e674-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0e674-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0e674-137">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="0e674-137">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
