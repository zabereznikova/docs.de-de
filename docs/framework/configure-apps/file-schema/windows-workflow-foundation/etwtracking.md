---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 12589ab7c6cb65618a5f53a3e4be49d85a2ffbb7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358963"
---
# <a name="etwtracking"></a><span data-ttu-id="e2a7a-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="e2a7a-101">\<etwTracking></span></span>
<span data-ttu-id="e2a7a-102">Ein Dienstverhalten, das einen Dienst, ETW-nachverfolgung mit ermöglicht eine <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="e2a7a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e2a7a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2a7a-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e2a7a-104">\<behaviors></span></span>  
<span data-ttu-id="e2a7a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e2a7a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e2a7a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e2a7a-106">\<behavior></span></span>  
<span data-ttu-id="e2a7a-107">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="e2a7a-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a7a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2a7a-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2a7a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e2a7a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e2a7a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2a7a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e2a7a-111">Attributes</span></span>  
  
|<span data-ttu-id="e2a7a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e2a7a-112">Attribute</span></span>|<span data-ttu-id="e2a7a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2a7a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2a7a-114">profileName</span><span class="sxs-lookup"><span data-stu-id="e2a7a-114">profileName</span></span>|<span data-ttu-id="e2a7a-115">Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2a7a-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2a7a-116">Child Elements</span></span>  
 <span data-ttu-id="e2a7a-117">Keine</span><span class="sxs-lookup"><span data-stu-id="e2a7a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2a7a-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2a7a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e2a7a-119">Element</span><span class="sxs-lookup"><span data-stu-id="e2a7a-119">Element</span></span>|<span data-ttu-id="e2a7a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2a7a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2a7a-121">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e2a7a-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e2a7a-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2a7a-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2a7a-123">Remarks</span></span>  
 <span data-ttu-id="e2a7a-124">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="e2a7a-125">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="e2a7a-126">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2a7a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2a7a-127">Example</span></span>  
 <span data-ttu-id="e2a7a-128">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="e2a7a-129">Die Anbieter-Id, die ETW-Nachverfolgungsteilnehmer verwendet wird, für die Nachverfolgungsdatensätze an ETW, wird definiert, der  **\<Diagnose >** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="e2a7a-130">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="e2a7a-131">Dadurch wird definiert, indem die **ProfileName** Attribut der  **\<hinzufügen >** Element.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="e2a7a-132">Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer hinzugefügt, um die  **\<EtwTracking >** -Dienstverhalten.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="e2a7a-133">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="e2a7a-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e2a7a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2a7a-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="e2a7a-135">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="e2a7a-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e2a7a-136">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="e2a7a-136">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
