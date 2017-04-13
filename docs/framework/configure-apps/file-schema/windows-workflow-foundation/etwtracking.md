---
title: "&lt;etwTracking&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;etwTracking&gt;
Ein Dienstverhalten, das es einem Dienst ermöglicht, die ETW\-Nachverfolgung mit einem <xref:System.Activities.Tracking.ETWTrackingParticipant> zu verwenden.  
  
## Syntax  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <etwTracking profileName=”String” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|profileName|Eine Zeichenfolge, die den Namen des diesem Verhalten zugeordneten Nachverfolgungsprofils angibt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<behavior\> von \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## Hinweise  
 Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Dienstes hinzugefügt wird, konfiguriert es einen Nachverfolgungsteilnehmer für einen Workflowdienst.  
  
 Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.  Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.  
  
## Beispiel  
 In der folgenden Beispielkonfiguration wird der standardmäßige ETW\-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.  
  
 Die Anbieter\-ID, die der ETW\-Nachverfolgungsteilnehmer verwendet, um die Nachverfolgungsdatensätze an ETW weiterzuleiten, ist im Abschnitt **\<diagnostics\>** definiert.  Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.  Dieses Profil wird durch das **profileName**\-Attribut des **\<add\>**\-Elements definiert.  Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer dem **\<etwTracking\>**\-Dienstverhalten hinzugefügt.  Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.  
  
```  
  
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
  
## Siehe auch  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>   
 [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Überwachungsteilnehmer](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)