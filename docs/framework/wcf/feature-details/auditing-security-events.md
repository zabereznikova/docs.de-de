---
title: "&#220;berwachen von Sicherheitsereignissen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Überwachen von Sicherheitsereignissen [WCF]"
ms.assetid: 5633f61c-a3c9-40dd-8070-1c373b66a716
caps.latest.revision: 27
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 27
---
# &#220;berwachen von Sicherheitsereignissen
Mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erstellte Anwendungen können mit der Überwachungsfunktion Sicherheitsereignisse \(Erfolg, Fehler oder beides\) protokollieren.Die Ereignisse werden in das Ereignisprotokoll von Windows geschrieben und können in der Ereignisanzeige untersucht werden.  
  
 Mithilfe der Überwachung können Administratoren bereits stattgefundene oder gerade laufende Angriffe erkennen.Darüber hinaus können Entwickler mittels Überwachung sicherheitsrelevante Probleme debuggen.Falls beispielsweise berechtigten Benutzern versehentlich aufgrund eines Fehlers in der Konfiguration der Autorisierung oder Überprüfungsrichtlinie der Zugriff verweigert wird, kann die Ursache für diesen Fehler schnell durch Überprüfung des Ereignisprotokolls erkannt und isoliert werden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Sicherheit finden Sie unter [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Programmierung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] finden Sie unter [Basis\-WCF\-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## Überwachungsstufe und Überwachungsverhalten  
 Es gibt zwei Stufen für die Sicherheitsüberwachung:  
  
-   Autorisierung auf Dienstebene: Es wird ein Aufrufer autorisiert.  
  
-   Auf Nachrichtenebene: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] überprüft die Gültigkeit der Nachricht und authentifiziert den Aufrufer.  
  
 Sie können beide Überwachungsstufen auf Erfolg oder Fehler hin überprüfen. Dies wird als *Überwachungsverhalten* bezeichnet.  
  
## Auswahl des Überwachungsprotokolls  
 Nachdem Überwachungsstufe und Überwachungsverhalten festgelegt wurden, können Sie \(oder ein Administrator\) angeben, in welches Überwachungsprotokoll geschrieben werden soll.Zur Auswahl stehen drei Optionen: Standard \(Default\), Anwendung \(Application\) und Sicherheit \(Security\).Falls Sie "Standard" auswählen, ist das tatsächlich verwendete Protokoll vom verwendeten Betriebssystem abhängig und davon, ob auf diesem System in das Sicherheitsprotokoll geschrieben werden darf.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] zum "Betriebssystem" weiter unten in diesem Thema.  
  
 Zum Schreiben in das Sicherheitsprotokoll ist die Berechtigungsstufe `SeAuditPrivilege` erforderlich.Standardmäßig verfügen nur die Konten "Lokales System" und "Netzwerkdienst" über diese Berechtigung.Zum Verwalten der Sicherheitsprotokollfunktionen `read` und `delete` ist die Berechtigungsstufe `SeSecurityPrivilege` erforderlich.Standardmäßig verfügen nur Administratoren über diese Berechtigung.  
  
 Authentifizierte Benutzer dagegen dürfen das Anwendungsprotokoll anzeigen und in dieses Protokoll schreiben.[!INCLUDE[wxp](../../../../includes/wxp-md.md)] schreibt Überwachungsereignisse standardmäßig in das Anwendungsprotokoll.Dieses Protokoll kann auch persönliche Daten enthalten, die allen authentifizierten Benutzern zugänglich sind.  
  
## Unterdrücken von Überwachungsfehlern  
 Eine weitere Option bei der Überwachung ist die Unterdrückung von Überwachungsfehlern.Standardmäßig wirken sich Überwachungsfehler nicht auf die Anwendung aus.Bei Bedarf können Sie diese Option jedoch auf `false` setzen. In diesem Fall wird eine Ausnahme ausgelöst.  
  
## Programmieren der Überwachung  
 Sie können das Überwachungsverhalten entweder programmatisch oder über die Konfiguration festlegen.  
  
### Überwachen von Klassen  
 In der folgenden Tabelle werden die Klassen und Eigenschaften vorgestellt, mit denen das Überwachungsverhalten programmiert wird.  
  
|Klasse|Beschreibung|  
|------------|------------------|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>|Ermöglicht das Festlegen von Optionen für die Überwachung als Dienstverhalten.|  
|<xref:System.ServiceModel.AuditLogLocation>|Eine Enumeration, mit der festgelegt wird, in welches Protokoll geschrieben werden soll.Die möglichen Werte sind Standard \(Default\), Anwendung \(Application\) und Sicherheit \(Security\).Bei Auswahl von "Standard" \(Default\) wird das Protokoll durch das Betriebssystem bestimmt.Weitere Informationen finden Sie unter "Auswählen des Anwendungsereignisprotokolls oder des Sicherheitsereignisprotokolls" weiter unten in diesem Thema.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>|Legt fest, welche Arten von Ereignissen für die Nachrichtenauthentifizierung auf Nachrichtenebene überwacht werden.Zur Auswahl stehen `None`, `Failure`, `Success` und `SuccessOrFailure`.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>|Legt fest, welche Arten von Ereignissen für die Dienstautorisierung auf Dienstebene überwacht werden.Zur Auswahl stehen `None`, `Failure`, `Success` und `SuccessOrFailure`.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>|Legt fest, was mit der Clientanforderung geschieht, wenn bei der Überwachung ein Fehler auftritt.Zum Beispiel, wenn der Dienst versucht, in das Sicherheitsprotokoll zu schreiben, ohne über die `SeAuditPrivilege`\-Berechtigung zu verfügen.Der Standardwert `true` gibt an, dass Fehler ignoriert werden und die Clientanforderung normal verarbeitet wird.|  
  
 Ein Beispiel, wie Sie eine Anwendung für die Protokollierung von Überwachungsereignissen einrichten können, finden Sie unter [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  
  
### Konfiguration  
 Sie können Überwachungsverhalten auch über die Konfiguration angeben, indem Sie ein [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) unter dem [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) hinzufügen.Sie müssen das Element wie im folgenden Code gezeigt unter einem [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) hinzufügen.  
  
```  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <behavior>  
        <!— auditLogLocation="Application" or "Security" -—>  
        <serviceSecurityAudit  
                  auditLogLocation="Application"  
                  suppressAuditFailure="true"  
                  serviceAuthorizationAuditLevel="Failure"  
                  messageAuthenticationAuditLevel="SuccessOrFailure" />   
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Falls bei aktivierter Überwachung `auditLogLocation` nicht angegeben wird, lautet der standardmäßige Protokollname "Security" bei Plattformen, auf denen in das Sicherheitsprotokoll geschrieben werden darf. Andernfalls wird "Application" verwendet.Das Schreiben in das Sicherheitsprotokoll wird nur auf den Betriebssystemen [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] zum "Betriebssystem" weiter unten in diesem Thema.  
  
## Sicherheitsüberlegungen  
 Wenn böswillige Benutzer erkennen, dass die Überwachung aktiviert ist, können diese Angreifer ungültige Nachrichten senden, die dazu führen, dass Überwachungseinträge geschrieben werden.Wenn das Überwachungsprotokoll auf diese Weise ausgefüllt wird, schlägt das Überwachungssystem fehl.Legen Sie die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>\-Eigenschaft auf `true` fest, und verwenden Sie die Eigenschaften der Ereignisanzeige zum Steuern des Überwachungsverhaltens, um diese Gefahr zu umgehen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] im Microsoft Support\-Artikel zum Anzeigen und Verwalten von Ereignisprotokollen in der Ereignisanzeige in Windows XP [Einsehen und Verwalten von Ereignisprotokollen in der Ereignisanzeige in Windows XP](http://go.microsoft.com/fwlink/?LinkId=89150).  
  
 Unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] sind die in das Anwendungsprotokoll geschriebenen Überwachungsereignisse für alle authentifizierten Benutzer sichtbar.  
  
## Auswählen des Anwendungsereignisprotokolls oder des Sicherheitsereignisprotokolls  
 Die folgenden Tabellen enthalten Informationen, die Ihnen dabei helfen sollen zu entscheiden, ob in das Anwendungsereignisprotokoll oder in das Sicherheitsereignisprotokoll geschrieben werden soll.  
  
#### Betriebssystem  
  
|System|Anwendungsprotokoll|Sicherheitsprotokoll|  
|------------|-------------------------|--------------------------|  
|[!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] oder höher|Unterstützt|Nicht unterstützt|  
|[!INCLUDE[ws2003sp1](../../../../includes/ws2003sp1-md.md)] und [!INCLUDE[wv](../../../../includes/wv-md.md)]|Unterstützt|Threadkontext muss `SeAuditPrivilege` verarbeiten|  
  
#### Andere Faktoren  
 Neben dem Betriebssystem wird die Aktivierung der Protokollierung noch durch andere, in der folgenden Tabelle beschriebene Einstellungen gesteuert.  
  
|Faktor|Anwendungsprotokoll|Sicherheitsprotokoll|  
|------------|-------------------------|--------------------------|  
|Überwachungsrichtlinienverwaltung|n\/v|Das Sicherheitsprotokoll wird nicht nur über die Konfiguration, sondern auch über die Richtlinie der lokalen Sicherheitsautorität \(LSA\) gesteuert.Darüber hinaus muss die Kategorie "Objektzugriffsversuche überwachen" aktiviert sein.|  
|Standardmäßige Benutzerfreundlichkeit|Alle authentifizierten Benutzer können in das Anwendungsprotokoll schreiben, es sind also für Anwendungsprozesse keine weiteren Berechtigungsschritte erforderlich.|Der Anwendungsprozess \(Kontext\) muss über die `SeAuditPrivilege`\-Berechtigung verfügen.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>   
 <xref:System.ServiceModel.AuditLogLocation>   
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Basis\-WCF\-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md)   
 [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)   
 [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)   
 [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)