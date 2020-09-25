---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: e1048cf3a9f56e4177f3ffe2dcd561a1babadacd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198768"
---
# \<etwTracking>

<span data-ttu-id="6bcf3-101">Ein Dienstverhalten, das einem Dienst ermöglicht, die ETW-Nachverfolgung mit einem <xref:System.Activities.Tracking.EtwTrackingParticipant> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-101">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**  
  
## <a name="syntax"></a><span data-ttu-id="6bcf3-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bcf3-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bcf3-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6bcf3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6bcf3-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bcf3-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="6bcf3-105">Attributes</span></span>  
  
|<span data-ttu-id="6bcf3-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6bcf3-106">Attribute</span></span>|<span data-ttu-id="6bcf3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcf3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bcf3-108">profileName</span><span class="sxs-lookup"><span data-stu-id="6bcf3-108">profileName</span></span>|<span data-ttu-id="6bcf3-109">Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-109">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bcf3-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bcf3-110">Child Elements</span></span>  

 <span data-ttu-id="6bcf3-111">Keine</span><span class="sxs-lookup"><span data-stu-id="6bcf3-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bcf3-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bcf3-112">Parent Elements</span></span>  
  
|<span data-ttu-id="6bcf3-113">Element</span><span class="sxs-lookup"><span data-stu-id="6bcf3-113">Element</span></span>|<span data-ttu-id="6bcf3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bcf3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bcf3-115">\<behavior> von \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6bcf3-115">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="6bcf3-116">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-116">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bcf3-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6bcf3-117">Remarks</span></span>  

 <span data-ttu-id="6bcf3-118">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-118">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="6bcf3-119">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-119">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="6bcf3-120">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-120">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bcf3-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6bcf3-121">Example</span></span>  

 <span data-ttu-id="6bcf3-122">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-122">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="6bcf3-123">Die Anbieter-ID, die der etw-Überwachungs Teilnehmer zum Schreiben der nach Verfolgungs Datensätze in etw verwendet, ist im **\<diagnostics>** Abschnitt definiert.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-123">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="6bcf3-124">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-124">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="6bcf3-125">Dies wird durch das **ProfileName** -Attribut des- **\<add>** Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-125">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="6bcf3-126">Nachdem diese definiert wurden, wird dem Dienst Verhalten der nach Verfolgungs Teilnehmer hinzugefügt **\<etwTracking>** .</span><span class="sxs-lookup"><span data-stu-id="6bcf3-126">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="6bcf3-127">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="6bcf3-127">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6bcf3-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bcf3-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="6bcf3-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6bcf3-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6bcf3-130">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="6bcf3-130">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
