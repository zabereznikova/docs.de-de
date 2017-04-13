---
title: "Dienst&#252;berwachungsverhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Dienst&#252;berwachungsverhalten
Dieses Beispiel zeigt, wie das <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> verwendet werden kann, um die Überwachung von Sicherheitsereignissen während Dienstvorgängen zu aktivieren.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).Der Dienst und der Client wurden mit dem [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) konfiguriert.Das `mode`\-Attribut aus dem [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) wurde auf `Message` und `clientCredentialType` wurde auf `Windows` festgelegt.In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von IIS \(Internet Information Services, Internetinformationsdienste\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstkonfigurationsdatei verwendet das `serviceSecurityAudit`\-Element, um Überwachung zu konfigurieren.  
  
```  
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
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.  
  
 Die resultierenden Überwachungsprotokolle können in der Ereignisanzeige angezeigt werden.Standardmäßig können die Überwachungsereignisse unter Windows XP im Anwendungsprotokoll und unter Windows Server 2003 und Windows Vista im Sicherheitsprotokoll angezeigt werden.Unter Windows Server 2008 und Windows 7 können die Überwachungsereignisse standardmäßig in den Anwendungs\- und Dienstprotokollen eingesehen werden.Der Speicherort für Überwachungsereignisse kann durch Festlegen des `auditLogLocation`\-Attributs auf "Application" oder "Security" angegeben werden.Weitere Informationen finden Sie unter [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).Wenn die Ereignisse in das Sicherheitsprotokoll geschrieben werden, sollte LocalSecurityPolicy\-\> Objektzugriff aktivieren auf "Erfolg" und "Fehler" eingestellt werden.  
  
 Im Ereignisprotokoll ist die Quelle der Überwachungsereignisse "ServiceModel Audit 3.0.0.0".Überwachungsdatensätze für die Nachrichtenauthentifizierung weisen die Kategorie "MessageAuthentication" auf, während Überwachungsdatensätze für die Dienstautorisierung die Kategorie "ServiceAuthorization" aufweisen.  
  
 Ereignisse der Nachrichtenauthentifizierungsüberwachung zeigen an, ob die Nachricht manipuliert wurde, abgelaufen ist und ob der Client für den Dienst authentifiziert werden kann.Sie enthalten Informationen darüber, ob die Authentifizierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients und über den Endpunkt, an den die Nachricht zusammen mit der der Nachricht zugewiesenen Aktion gesendet wurde.  
  
 Ereignisse der Dienstautorisierungsüberwachung enthalten die Autorisierungsentscheidung, die vom Dienstautorisierungs\-Manager getroffen wird.Sie enthalten Informationen darüber, ob die Autorisierung erfolgreich war oder fehlgeschlagen ist, sowie Informationen über die Identität des Clients, den Endpunkt, an den die Nachricht gesendet wurde, die der Nachricht zugewiesene Aktion, die Kennung des Autorisierungskontexts, der aus der eingehenden Nachricht generiert wurde, und den Typ des Autorisierungs\-Managers, der die Zugriffsentscheidung getroffen hat.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Siehe auch  
 [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)   
 [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)