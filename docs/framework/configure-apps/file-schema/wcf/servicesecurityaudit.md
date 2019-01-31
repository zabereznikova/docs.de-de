---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 05579f1c2a0d0c0637530c524c37b141a9d37b5b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287754"
---
# <a name="servicesecurityaudit"></a>\<serviceSecurityAudit>
Legt Einstellungen fest, die die Überwachung von Sicherheitsereignissen während der Dienstvorgänge ermöglichen.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceSecurityAudit>  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|auditLogLocation|Gibt den Speicherort des Überwachungsprotokolls an. Folgende Werte sind gültig:<br /><br /> – Default: Sicherheitsereignisse werden in das Anwendungsprotokoll auf Windows XP, und klicken Sie in das Ereignisprotokoll auf Windows Server 2003 und Windows Vista geschrieben.<br />-Anwendung: Überprüfungsereignisse werden in das Anwendungsereignisprotokoll geschrieben.<br />-Sicherheit: Überprüfungsereignisse werden in das Sicherheitsereignisprotokoll geschrieben.<br /><br /> Der Standardwert lautet Default. Weitere Informationen finden Sie unter <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.<br /><br /> Anwendungen sollten über Schreibfehler im Überwachungsprotokoll benachrichtigt werden. Wenn die Anwendung nicht für das Verarbeiten von Überwachungsfehlern ausgelegt ist, sollten Sie dieses Attribut verwenden, um Fehler beim Schreiben in das Überwachungsprotokoll zu unterdrücken.<br /><br /> Wenn dieses Attribut den Wert `true` hat, werden Ausnahmen (außer OutOfMemoryException, StackOverFlowException, ThreadAbortException und ArgumentException), die aus Versuchen, Überwachungsereignisse zu schreiben, hervorgehen, vom System verarbeitet und nicht an die Anwendung weitergegeben. Wenn dieses Attribut den Wert `false` hat, werden alle Ausnahmen, die aus Versuchen, Überwachungsereignisse zu schreiben, hervorgehen, an die Anwendung weitergegeben.<br /><br /> Die Standardeinstellung ist `true`.|  
|serviceAuthorizationAuditLevel|Gibt die Typen von Autorisierungsereignissen an, die im Überwachungsprotokoll aufgezeichnet werden. Folgende Werte sind gültig:<br /><br /> – None: Keine Überwachung der dienstautorisierungsereignisse wird durchgeführt werden.<br />– Erfolg: Es werden nur erfolgreiche dienstautorisierungsereignisse überwacht.<br />-Fehler: Es werden nur Fehler-dienstautorisierungsereignisse überwacht.<br />-SuccessOrFailure: Es werden sowohl erfolgreiche und fehlgeschlagene dienstautorisierungsereignisse überwacht.<br /><br /> Der Standardwert ist None. Weitere Informationen finden Sie unter <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Gibt den Typ der protokollierten Nachrichtenauthentifizierungs-Überwachungsereignisse an. Folgende Werte sind gültig:<br /><br /> – None: Es werden keine Überwachungsereignisse generiert.<br />– Erfolg: Nur erfolgreiche Sicherheitsereignisse (vollständige Prüfung, einschließlich der Signatur der nachrichtenüberprüfung nachrichtensignaturprüfung, verschlüsselungs- und tokenüberprüfung) Ereignisse werden protokolliert.<br />-Fehler: Es werden nur fehlgeschlagene Ereignisse protokolliert.<br />-SuccessOrFailure: Sowohl Erfolgs-als auch Ereignisse werden protokolliert.<br /><br /> Der Standardwert ist None. Weitere Informationen finden Sie unter <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement wird verwendet, um Windows Communication Foundation (WCF)-Authentifizierungsereignisse zu überwachen. Ist die Überwachung aktiviert, können entweder erfolgreiche oder fehlgeschlagene Authentifizierungsversuche (oder beides) überwacht werden. Die Ereignisse werden in eines der drei Ereignisprotokolle geschrieben: das Anwendungs-, Sicherheits- oder Standardprotokoll für die Betriebssystemversion. Die Ereignisprotokolle können alle mit der Windows-Ereignisanzeige angezeigt werden.  
  
 Ein ausführliches Beispiel für die Verwendung dieses Konfigurationselements finden Sie unter [Dienstüberwachungsverhalten](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).  
  
 Standardmäßig können unter Windows XP die Überwachungsereignisse im Anwendungsprotokoll und unter Windows Server 2003 und Windows Vista im Sicherheitsprotokoll angezeigt werden. Der Speicherort von Überwachungsereignissen kann durch Festlegen des `auditLogLocation`-Attributs auf "Application" oder "Security" angegeben werden. Weitere Informationen finden Sie unter [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Wenn die Ereignisse in das Sicherheitsprotokoll geschrieben werden, sollte "LocalSecurityPolicy-> Objektzugriff aktivieren" auf "Erfolg" und "Fehler" eingestellt werden.  
  
 Im Ereignisprotokoll ist die Quelle der Überwachungsereignisse "ServiceModel Audit 3.0.0.0". Nachrichtenauthentifizierungsüberwachungs-Datensätze weisen die Kategorie "MessageAuthentication" auf, während Dienstautorisierungsüberwachungs-Datensätze die Kategorie 'ServiceAuthorization' aufweisen.  
  
 Ereignisse der Nachrichtenauthentifizierungsüberwachung zeigen an, ob die Nachricht manipuliert wurde, abgelaufen ist und ob der Client für den Dienst authentifiziert werden kann. Sie enthalten Informationen darüber, ob die Authentifizierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients und über den Endpunkt, an den die Nachricht zusammen mit der der Nachricht zugewiesenen Aktion gesendet wurde.  
  
 Ereignisse der Dienstautorisierungsüberwachung enthalten die Autorisierungsentscheidung, die vom Dienstautorisierungs-Manager getroffen wird. Sie bieten Informationen zu, ob die Autorisierung erfolgreich waren oder fehlgeschlagen ist, zusammen mit der Identität des Clients, der Endpunkt die Nachricht gesendet wurde, mit der Nachricht, die Kennung des Autorisierungskontexts, der generiert wurde, von der zugewiesenen Aktion die eingehende Nachricht und den Typ des Autorisierungs-Managers, der die zugriffsentscheidung getroffen hat.  
  
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
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Überwachung](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
- [Dienstüberwachungsverhalten](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)
