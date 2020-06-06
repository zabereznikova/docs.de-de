---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 10888f26053014ffb1fec49d1dfe87c7fd09ab54
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399579"
---
# \<serviceSecurityAudit>
Legt Einstellungen fest, die die Überwachung von Sicherheitsereignissen während der Dienstvorgänge ermöglichen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|auditLogLocation|Gibt den Speicherort des Überwachungsprotokolls an. Gültige Werte sind:<br /><br /> -Standard: Sicherheitsereignisse werden in das Anwendungsprotokoll unter Windows XP und in das Ereignisprotokoll unter Windows Server 2003 und Windows Vista geschrieben.<br />-Anwendung: Überwachungs Ereignisse werden in das Anwendungs Ereignisprotokoll geschrieben.<br />-Security: Überwachungs Ereignisse werden in das Sicherheits Ereignisprotokoll geschrieben.<br /><br /> Der Standardwert ist Default. Weitere Informationen finden Sie unter <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.<br /><br /> Anwendungen sollten über Schreibfehler im Überwachungsprotokoll benachrichtigt werden. Wenn die Anwendung nicht für das Verarbeiten von Überwachungsfehlern ausgelegt ist, sollten Sie dieses Attribut verwenden, um Fehler beim Schreiben in das Überwachungsprotokoll zu unterdrücken.<br /><br /> Wenn dieses Attribut den Wert `true` hat, werden Ausnahmen (außer OutOfMemoryException, StackOverFlowException, ThreadAbortException und ArgumentException), die aus Versuchen, Überwachungsereignisse zu schreiben, hervorgehen, vom System verarbeitet und nicht an die Anwendung weitergegeben. Wenn dieses Attribut den Wert `false` hat, werden alle Ausnahmen, die aus Versuchen, Überwachungsereignisse zu schreiben, hervorgehen, an die Anwendung weitergegeben.<br /><br /> Der Standardwert lautet `true`.|  
|serviceAuthorizationAuditLevel|Gibt die Typen von Autorisierungsereignissen an, die im Überwachungsprotokoll aufgezeichnet werden. Gültige Werte sind:<br /><br /> -None: Es wird keine Überwachung von Dienst Autorisierungs Ereignissen ausgeführt.<br />-Success: Es werden nur erfolgreiche Dienst Autorisierungs Ereignisse überwacht.<br />-Fehler: nur Fehler Dienst-Autorisierungs Ereignisse werden überwacht.<br />-Erfolgreiorfailure: sowohl Erfolgs-als auch Fehler Dienst-Autorisierungs Ereignisse werden überwacht.<br /><br /> Der Standardwert lautet „Keine“. Weitere Informationen finden Sie unter <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Gibt den Typ der protokollierten Nachrichtenauthentifizierungs-Überwachungsereignisse an. Gültige Werte sind:<br /><br /> -None: Es werden keine Überwachungs Ereignisse generiert.<br />-Erfolg: Es werden nur erfolgreiche Sicherheitsereignisse (vollständige Validierung einschließlich Validierung der Nachrichten Signatur, Chiffre Validierung und tokenüberprüfung) protokolliert.<br />-Fehler: nur Fehlerereignisse werden protokolliert.<br />-Erfolgreiorfailure: sowohl Erfolgs-als auch Fehlerereignisse werden protokolliert.<br /><br /> Der Standardwert lautet „Keine“. Weitere Informationen finden Sie unter <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieses Konfigurationselement wird verwendet, um Windows Communication Foundation (WCF)-Authentifizierungs Ereignisse zu überwachen. Ist die Überwachung aktiviert, können entweder erfolgreiche oder fehlgeschlagene Authentifizierungsversuche (oder beides) überwacht werden. Die Ereignisse werden in eines der drei Ereignisprotokolle geschrieben: das Anwendungs-, Sicherheits- oder Standardprotokoll für die Betriebssystemversion. Die Ereignisprotokolle können alle mit der Windows-Ereignisanzeige angezeigt werden.  
  
 Ein ausführliches Beispiel für die Verwendung dieses Konfigurations Elements finden Sie unter [Service Auditing Behavior](../../../wcf/samples/service-auditing-behavior.md).  
  
 Standardmäßig können unter Windows XP die Überwachungsereignisse im Anwendungsprotokoll und unter Windows Server 2003 und Windows Vista im Sicherheitsprotokoll angezeigt werden. Der Speicherort von Überwachungsereignissen kann durch Festlegen des `auditLogLocation`-Attributs auf "Application" oder "Security" angegeben werden. Weitere Informationen finden Sie unter Vorgehensweise: Überwachen von [Sicherheits Ereignissen](../../../wcf/feature-details/how-to-audit-wcf-security-events.md). Wenn die Ereignisse in das Sicherheitsprotokoll geschrieben werden, sollte das LocalSecurityPolicy-> Objektzugriff aktivieren auf "Erfolg" und "Fehler" festgelegt werden.  
  
 Im Ereignisprotokoll ist die Quelle der Überwachungsereignisse "ServiceModel Audit 3.0.0.0". Nachrichtenauthentifizierungsüberwachungs-Datensätze weisen die Kategorie "MessageAuthentication" auf, während Dienstautorisierungsüberwachungs-Datensätze die Kategorie 'ServiceAuthorization' aufweisen.  
  
 Ereignisse der Nachrichtenauthentifizierungsüberwachung zeigen an, ob die Nachricht manipuliert wurde, abgelaufen ist und ob der Client für den Dienst authentifiziert werden kann. Sie enthalten Informationen darüber, ob die Authentifizierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients und über den Endpunkt, an den die Nachricht zusammen mit der der Nachricht zugewiesenen Aktion gesendet wurde.  
  
 Ereignisse der Dienstautorisierungsüberwachung enthalten die Autorisierungsentscheidung, die vom Dienstautorisierungs-Manager getroffen wird. Sie enthalten Informationen darüber, ob die Autorisierung erfolgreich war oder fehlgeschlagen ist, sowie die Identität des Clients, den Endpunkt, an den die Nachricht gesendet wurde, die der Nachricht zugeordnete Aktion, den Bezeichner des Autorisierungs Kontexts, der von der eingehenden Nachricht generiert wurde, und den Typ des Autorisierungs-Managers, der die Zugriffs Entscheidung getroffen  
  
## <a name="example"></a>Beispiel  
  
```xml  
<system.serviceModel>
  <behaviors>
    <serviceBehaviors>
      <behavior name="NewBehavior">
        <serviceSecurityAudit auditLogLocation="Application"
                              suppressAuditFailure="true"
                              serviceAuthorizationAuditLevel="Success"
                              messageAuthenticationAuditLevel="Success" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Auditing](../../../wcf/feature-details/auditing-security-events.md)
- [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [Dienstüberwachungsverhalten](../../../wcf/samples/service-auditing-behavior.md)
