---
title: '&lt;add&gt; von &lt;participants&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: bc32b9b55ef8767be44cc69b9277c81d62a1944d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575894"
---
# <a name="ltaddgt-of-ltparticipantsgt"></a>&lt;add&gt; von &lt;participants&gt;
Konfiguriert einen Nachverfolgungsteilnehmer, der den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauscht und sie entsprechend der Weise verarbeitet, wie er konfiguriert wurde. Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.  
  
 Weitere Informationen im Workflow-Überwachung und zu nachverfolgungsteilnehmern finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsteilnehmer](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).  
  
\<system.serviceModel>  
\<tracking>  
\<participants>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Name|Eine Zeichenfolge, die den Namen eines Nachverfolgungsteilnehmers angibt.|  
|profileName|Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt. Dieses Profil definiert die Nachverfolgungsdatensätze, die der Nachverfolgungsteilnehmer abonniert hat.|  
|Typ|Eine Zeichenfolge, die den Typ eines Nachverfolgungsteilnehmers angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|Eine Liste von Nachverfolgungsteilnehmern|  
  
## <a name="remarks"></a>Hinweise  
 Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern. Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.  
  
 Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden. Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.  
  
 Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt. Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird. Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden. Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.  
  
 Die Anbieter-Id, die ETW-Nachverfolgungsteilnehmer verwendet wird, für die Nachverfolgungsdatensätze an ETW, wird definiert, der  **\<Diagnose >** Abschnitt. Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat. Dadurch wird definiert, indem die **ProfileName** Attribut der  **\<hinzufügen >** Element. Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer hinzugefügt, um die  **\<EtwTracking >** -Dienstverhalten. Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.  
  
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
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Überwachungsteilnehmer](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
