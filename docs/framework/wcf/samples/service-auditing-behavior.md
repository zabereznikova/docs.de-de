---
title: Dienstüberwachungsverhalten
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: 1719db9749336d584627280aba3412557b164356
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310394"
---
# <a name="service-auditing-behavior"></a>Dienstüberwachungsverhalten
Dieses Beispiel zeigt, wie das <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> verwendet werden kann, um die Überwachung von Sicherheitsereignissen während Dienstvorgängen zu aktivieren. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md). Der Dienst und der Client konfiguriert wurden mithilfe der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Die `mode` Attribut der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) festgelegt wurde `Message` und `clientCredentialType` festgelegt wurde `Windows`. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
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
  
 Die resultierenden Überwachungsprotokolle können in der Ereignisanzeige angezeigt werden. Standardmäßig können die Überwachungsereignisse unter Windows XP im Anwendungsprotokoll und unter Windows Server 2003 und Windows Vista im Sicherheitsprotokoll angezeigt werden. Unter Windows Server 2008 und Windows 7 können die Überwachungsereignisse standardmäßig in den Anwendungs- und Dienstprotokollen eingesehen werden. Der Speicherort für Überwachungsereignisse kann angegeben werden, durch Festlegen der `auditLogLocation` -Attributs auf "Application" oder "Sicherheit". Weitere Informationen finden Sie unter [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Wenn die Ereignisse geschrieben werden in das Sicherheitsprotokoll aus, die LocalSecurityPolicy -> Objektzugriff aktivieren für "Erfolg" und "Failure" festgelegt werden soll.  
  
 Im Ereignisprotokoll ist die Quelle der Überwachungsereignisse "ServiceModel Audit 3.0.0.0". Datensätze zur nachrichtenauthentifizierungsüberwachung weisen die Kategorie "Messageauthentication", während dienstautorisierungsüberwachungs-Datensätze die Kategorie "ServiceAuthorization" aufweisen.  
  
 Ereignisse der Nachrichtenauthentifizierungsüberwachung zeigen an, ob die Nachricht manipuliert wurde, abgelaufen ist und ob der Client für den Dienst authentifiziert werden kann. Sie enthalten Informationen darüber, ob die Authentifizierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients und über den Endpunkt, an den die Nachricht zusammen mit der der Nachricht zugewiesenen Aktion gesendet wurde.  
  
 Ereignisse der Dienstautorisierungsüberwachung enthalten die Autorisierungsentscheidung, die vom Dienstautorisierungs-Manager getroffen wird. Sie enthalten Informationen darüber, ob die Autorisierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients, den Endpunkt, an den die Nachricht gesendet wurde, die der Nachricht zugewiesene Aktion, die Kennung des Autorisierungskontexts, der aus der eingehenden Nachricht generiert wurde, und den Typ des Autorisierungs-Managers, der die Zugriffsentscheidung getroffen hat.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch

- [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
