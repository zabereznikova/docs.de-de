---
title: Dienstüberwachungsverhalten
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: bfe13146a7f7cdec648a82a34c34077ec5466809
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599931"
---
# <a name="service-auditing-behavior"></a>Dienstüberwachungsverhalten
Dieses Beispiel zeigt, wie das <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> verwendet werden kann, um die Überwachung von Sicherheitsereignissen während Dienstvorgängen zu aktivieren. Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten. Der Dienst und der Client wurden mithilfe von konfiguriert [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . Das `mode` -Attribut von wurde [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) auf festgelegt, `Message` und wurde `clientCredentialType` auf festgelegt `Windows` . In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstkonfigurationsdatei verwendet das `serviceSecurityAudit`-Element, um Überwachung zu konfigurieren.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.  
  
 Die resultierenden Überwachungsprotokolle können in der Ereignisanzeige angezeigt werden. Standardmäßig können die Überwachungsereignisse unter Windows XP im Anwendungsprotokoll und unter Windows Server 2003 und Windows Vista im Sicherheitsprotokoll angezeigt werden. Unter Windows Server 2008 und Windows 7 können die Überwachungsereignisse standardmäßig in den Anwendungs- und Dienstprotokollen eingesehen werden. Der Speicherort der Überwachungs Ereignisse kann durch Festlegen des- `auditLogLocation` Attributs auf "Application" oder "Security" angegeben werden. Weitere Informationen finden Sie unter Vorgehensweise: Überwachen von [Sicherheits Ereignissen](../feature-details/how-to-audit-wcf-security-events.md). Wenn die Ereignisse in das Sicherheitsprotokoll geschrieben werden, sollte LocalSecurityPolicy-> Objektzugriff aktivieren auf "Erfolg" und "Fehler" festgelegt werden.  
  
 Im Ereignisprotokoll ist die Quelle der Überwachungsereignisse "ServiceModel Audit 3.0.0.0". Überwachungsdaten Sätze für die Nachrichten Authentifizierung weisen die Kategorie "MessageAuthentication" auf, während Überwachungsdaten Sätze für die Dienst Autorisierung die Kategorie "ServiceAuthorization" aufweisen.  
  
 Ereignisse der Nachrichtenauthentifizierungsüberwachung zeigen an, ob die Nachricht manipuliert wurde, abgelaufen ist und ob der Client für den Dienst authentifiziert werden kann. Sie enthalten Informationen darüber, ob die Authentifizierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients und über den Endpunkt, an den die Nachricht zusammen mit der der Nachricht zugewiesenen Aktion gesendet wurde.  
  
 Ereignisse der Dienstautorisierungsüberwachung enthalten die Autorisierungsentscheidung, die vom Dienstautorisierungs-Manager getroffen wird. Sie enthalten Informationen darüber, ob die Autorisierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients, den Endpunkt, an den die Nachricht gesendet wurde, die der Nachricht zugewiesene Aktion, die Kennung des Autorisierungskontexts, der aus der eingehenden Nachricht generiert wurde, und den Typ des Autorisierungs-Managers, der die Zugriffsentscheidung getroffen hat.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Auditing](../feature-details/auditing-security-events.md)
- [Vorgehensweise: Überwachen von Sicherheitsereignissen](../feature-details/how-to-audit-wcf-security-events.md)
