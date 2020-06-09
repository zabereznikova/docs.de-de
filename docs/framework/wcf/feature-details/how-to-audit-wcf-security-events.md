---
title: 'Vorgehensweise: Überwachen von Windows Communication Foundation-Sicherheitsereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 186dd4a7fc2beae848e5cbd167a204352ee6ed4e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601295"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a>Vorgehensweise: Überwachen von Windows Communication Foundation-Sicherheitsereignissen
Mit Windows Communication Foundation (WCF) können Sie Sicherheitsereignisse im Windows-Ereignisprotokoll protokollieren, die mit dem Windows Ereignisanzeige angezeigt werden können. In diesem Thema wird erläutert, wie eine Anwendung so eingerichtet werden kann, dass Sicherheitsereignisse protokolliert werden. Weitere Informationen zur WCF- [Überwachung finden Sie](auditing-security-events.md)unter Überwachung.  
  
### <a name="to-audit-security-events-in-code"></a>So überwachen Sie Sicherheitsereignisse im Code  
  
1. Geben Sie den Speicherort des Überwachungsprotokolls an. Legen Sie hierzu die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>-Eigenschaft der <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>-Klasse auf einen der <xref:System.ServiceModel.AuditLogLocation>-Enumerationswerte fest, wie im folgenden Code gezeigt:  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     Die- <xref:System.ServiceModel.AuditLogLocation> Enumeration besitzt drei Werte: `Application` , `Security` oder `Default` . Mithilfe des Werts wird eines der in der Ereignisanzeige angezeigten Protokolle angegeben: entweder das Sicherheits- oder das Anwendungsprotokoll. Bei Verwendung des `Default`-Werts ist das tatsächliche Protokoll vom Betriebssystem abhängig, unter dem die Anwendung ausgeführt wird. Ist bei aktivierter Überwachung kein Protokollspeicherort angegeben, wird für Plattformen, von denen das Schreiben in das Sicherheitsprotokoll unterstützt wird, standardmäßig das `Security`-Protokoll verwendet. Andernfalls wird das `Application`-Protokoll verwendet. Standardmäßig unterstützen nur Windows Server 2003 und Windows Vista das Schreiben in das Sicherheitsprotokoll.  
  
2. Richten Sie die zu überwachenden Ereignistypen ein. Ereignisse auf Dienstebene sowie Autorisierungsereignisse auf Nachrichtenebene können gleichzeitig überwacht werden. Legen Sie hierzu die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>-Eigenschaft oder die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>-Eigenschaft auf einen der <xref:System.ServiceModel.AuditLevel>-Enumerationswerte fest, wie im folgenden Code gezeigt:  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. Geben Sie an, ob Fehler bei Protokollüberwachungsereignissen unterdrückt oder für die Anwendung verfügbar gemacht werden sollen. Legen Sie die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>-Eigenschaft entweder auf `true` oder auf `false` fest, wie im folgenden Code gezeigt:  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     Die standardmäßige `SuppressAuditFailure`-Eigenschaft ist `true`. Die Anwendung wird also durch einen Fehler bei der Überwachung nicht beeinträchtigt. Andernfalls wird eine Ausnahme ausgelöst. Für jede erfolgreiche Überwachung wird eine ausführliche Ablaufverfolgung geschrieben. Für jeden Überwachungsfehler wird eine Ablaufverfolgung auf Fehlerebene geschrieben.  
  
4. Löschen Sie das vorhandene <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> aus der Verhaltensauflistung, die sich in der Beschreibung eines <xref:System.ServiceModel.ServiceHost> befindet. Der Zugriff auf die Verhaltensauflistung erfolgt über die <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Eigenschaft, auf die wiederum über die <xref:System.ServiceModel.ServiceHostBase.Description%2A>-Eigenschaft zugegriffen wird. Fügen Sie der gleichen Auflistung anschließend das neue <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> hinzu, wie im folgenden Code gezeigt:  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a>So richten Sie die Überwachung in der Konfiguration ein  
  
1. Fügen Sie [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) dem- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) Abschnitt der Datei "Web. config" ein-Element hinzu, um die Überwachung in der Konfiguration einzurichten. Fügen Sie dann ein [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) -Element hinzu, und legen Sie die verschiedenen Attribute fest, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"
                serviceAuthorizationAuditLevel="None"
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. Geben Sie das Verhalten für den Dienst an, wie im folgenden Beispiel gezeigt:  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a>Beispiel  
 Mithilfe des folgenden Codes wird eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse erstellt, und der Verhaltensauflistung wird ein neues <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> hinzugefügt.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Durch Festlegen der <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>-Eigenschaft auf `true` werden Fehler beim Generieren von Sicherheitsüberwachungen unterdrückt. (Bei Verwendung von `false` wird eine Ausnahme ausgelöst). Wenn Sie jedoch die folgende Windows-Eigenschaft für die **lokale Sicherheitseinstellung** aktivieren, führt ein Fehler beim Generieren von Überwachungs Ereignissen dazu, dass Windows sofort heruntergefahren wird:  
  
 **Überwachung: System sofort herunterfahren, wenn Sicherheitsüberprüfungen nicht protokolliert werden können**  
  
 Um die-Eigenschaft festzulegen, öffnen Sie das Dialogfeld **Lokale Sicherheitseinstellungen** . Klicken Sie unter **Sicherheitseinstellungen**auf **lokale Richtlinien**. Klicken Sie dann auf **Sicherheitsoptionen**.  
  
 Wenn die <xref:System.ServiceModel.AuditLogLocation> -Eigenschaft auf festgelegt ist <xref:System.ServiceModel.AuditLogLocation.Security> und die Überwachung des **Objekt Zugriffs** in der **lokalen Sicherheitsrichtlinie**nicht festgelegt ist, werden Überwachungs Ereignisse nicht in das Sicherheitsprotokoll geschrieben. Es wird zwar kein Fehler zurückgegeben, doch die Überwachungseinträge werden nicht in das Sicherheitsprotokoll geschrieben.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [Auditing](auditing-security-events.md)
