---
title: Einstellungsprozess
ms.date: 03/30/2017
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
ms.openlocfilehash: c6f542cef8e1417ed9c8d3a185252a91062e2161
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62005055"
---
# <a name="hiring-process"></a>Einstellungsprozess
In diesem Beispiel wird veranschaulicht, wie ein Geschäftsprozess mit Messagingaktivitäten sowie zwei als Workflowdienste gehostete Workflows implementiert werden. Diese Workflows sind Teil der IT-Infrastruktur des fiktionalen Unternehmens Contoso, Inc.  
  
 Der `HiringRequest`-Workflowprozess (implementiert als <xref:System.Activities.Statements.Flowchart>) erfordert eine Autorisierung durch mehrere Manager in der Organisation. Um dieses Ziel zu erreichen, verwendet der Workflow bestehende Dienste in der Organisation (in unserem Fall, ein posteingangsdienst sowie ein Organisationsdaten-Dienst, der als einfache Windows Communication Foundation (WCF)-Dienste implementiert).  
  
 Mit dem `ResumeRequest`-Workflow (implementiert als <xref:System.Activities.Statements.Sequence>) wird eine Stellenausschreibung auf der externen Website der Personalabteilung von Contoso veröffentlicht, und die eingehenden Lebensläufe werden verwaltet. Die Stellenausschreibung ist auf der externen Website des Unternehmens abrufbar, bis ein diesbezüglich festgelegter Zeitraum abgelaufen ist oder sie von einem Mitarbeiter von Contoso entfernt wird.  
  
 In diesem Beispiel werden die folgenden Funktionen von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] veranschaulicht:  
  
- <xref:System.Activities.Statements.Flowchart>-Workflow und <xref:System.Activities.Statements.Sequence>-Workflow zur Modellierung von Geschäftsprozessen  
  
- Workflowdienste  
  
- Messagingaktivitäten  
  
- Inhaltsbasierte Korrelation  
  
- Benutzerdefinierte Aktivitäten (deklarativ und codebasiert)  
  
- Vom System bereitgestellte SQL Server-Persistenz  
  
- <xref:System.Activities.Persistence.PersistenceParticipant> (benutzerdefiniert)  
  
- Benutzerdefinierte Nachverfolgung  
  
- Ereignisablaufverfolgung (ETW) für Windows  
  
- Komposition von Aktivitäten  
  
- <xref:System.Activities.Statements.Parallel>-Aktivitäten  
  
- <xref:System.Activities.Statements.CancellationScope>-Aktivität  
  
- Permanente Zeitgeber (<xref:System.Activities.Statements.Delay>-Aktivität)  
  
- Transaktionen  
  
- Mehrere Workflows in einer Projektmappe  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## <a name="description-of-the-process"></a>Beschreibung des Vorgangs  
 Contoso, Inc. ist bestrebt, die Belegschaft in den einzelnen Abteilungen möglichst optimal zu gestalten. Bevor ein Mitarbeiter eine Stellenausschreibung initiieren kann und Neueinstellungen möglich sind, muss daher ein entsprechendes Genehmigungsverfahren durchlaufen werden. Dieses Genehmigungsverfahren zur Neueinstellung ist im HiringRequestService-Projekt definiert und umfasst folgende Schritte:  
  
1. Ein Mitarbeiter (der Antragsteller) beantragt eine Neueinstellung.  
  
2. Diese muss vom verantwortlichen Manager genehmigt werden:  
  
    1. Der Antrag kann vom Manager abgelehnt werden.  
  
    2. Der Antrag kann mit der Bitte um weitere Informationen an den Antragsteller zurückgegeben werden:  
  
        1. Der Antragsteller überprüft die Bitte und sendet den Antrag zurück an den Manager.  
  
    3. Der Antrag kann vom Manager genehmigt werden.  
  
3. Nachdem der Antrag vom zuständigen Manager genehmigt wurde, muss er vom Abteilungsleiter abgesegnet werden:  
  
    1. Der Antrag kann vom Abteilungsleiter zurückgewiesen werden.  
  
    2. Der Antrag kann vom Abteilungsleiter genehmigt werden.  
  
4. Nach der Genehmigung durch den Abteilungsleiter muss der Vorgang noch von 2 Personalvorständen oder vom Firmenchef autorisiert werden:  
  
    1. Der Vorgang kann dann in den Zustand der Genehmigung oder Ablehnung übergehen.  
  
    2. Wenn der Vorgang genehmigt wurde, wird eine neue Instanz des `ResumeRequest`-Workflows gestartet (`ResumeRequest` ist über einen Dienstverweis mit HiringRequest.csproj verknüpft.)  
  
 Nachdem die Neueinstellung von den Managern gebilligt wurde, muss von der Personalabteilung eine geeignete Person gefunden werden. Dieser Vorgang wird vom zweiten Workflow (`ResumeRequest`, definiert in ResumeRequestService.csproj) durchgeführt. Mit diesem Workflow wird der Ablauf für die Veröffentlichung einer Stellenausschreibung auf der externen Website mit Stellenausschreibungen von Contoso definiert. Eingehende Lebensläufe werden erfasst, und der Status der Stellenausschreibung wird überwacht. Stellenausschreibungen sind abrufbar, bis ein diesbezüglich festgelegter Zeitraum abgelaufen ist oder sie von einem Mitarbeiter von Contoso entfernt werden. Der `ResumeRequest`-Workflow besteht aus den folgenden Schritten:  
  
1. Ein Mitarbeiter von Contoso gibt die Stelleninformationen ein und legt einen Zeitraum für die Ausschreibung fest. Nachdem die Informationen eingegeben wurden, wird die Stelle auf der Website mit Stellenanzeigen veröffentlicht.  
  
2. Interessierte Personen können jetzt ihren Lebenslauf einreichen. Eingereichte Lebensläufe werden als Datensätze gespeichert und mit der Stellenausschreibung verknüpft.  
  
3. Bewerber können Lebensläufe einreichen, bis die Stellenanzeige abgelaufen ist oder der Bewerbungsprozess von einem Mitarbeiter von Contoso ausdrücklich beendet und die Anzeige entfernt wird.  
  
## <a name="projects-in-the-sample"></a>Projekte im Beispiel  
 In der folgenden Tabelle werden die Projekte in der Beispielprojektmappe aufgeführt:  
  
|Projekt|Beschreibung|  
|-------------|-----------------|  
|ContosoHR|Enthält Datenverträge, Geschäftsobjekte und Repositoryklassen.|  
|HiringRequestService|Enthält die Definition des Workflows zum Stellenausschreibungsverfahren.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die den Workflow (XAML-Datei) selbst als Dienst hostet.|  
|ResumeRequestService|Ein Workflowdienst, mit dem die Lebensläufe der Bewerber erfasst werden, bis die Stellenanzeige abläuft oder der Bewerbungsprozess beendet werden muss.<br /><br /> Dieses Projekt wird als deklarativer Workflowdienst (XAMLX) implementiert.|  
|OrgService|Ein Dienst, mit dem organisatorische Informationen (Employees, Positions, PositionTypes und Departments) verfügbar gemacht werden. Sie können sich diesen Dienst als Organisationsmodul im Rahmen der Unternehmensressourcenplanung (ERP) vorstellen.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die einen Windows Communication Foundation (WCF)-Dienst verfügbar macht.|  
|InboxService|Ein Posteingang mit aktionsfähigen Aufgaben für Mitarbeiter.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die einen WCF-Dienst verfügbar macht.|  
|InternalClient|Eine Webanwendung zur Interaktion mit dem Prozess. Benutzer können HiringProcess-Workflows anzeigen, starten sowie daran teilnehmen. Mit dieser Anwendung können außerdem ResumeRequest-Prozesse gestartet und überwacht werden.<br /><br /> Diese Site ist als interne Site für das Intranet von Contoso implementiert. Dieses Projekt ist als ASP.NET-Website implementiert.|  
|CareersWebSite|Eine externe Website, mit der offene Stellen von Contoso bekannt gemacht werden. Bewerber können zu dieser Seite navigieren und ihren Lebenslauf einreichen.|  
  
## <a name="feature-summary"></a>Zusammenfassung der Funktionen  
 In der folgenden Tabelle wird die Verwendung der einzelnen Funktionen in diesem Beispiel beschrieben.  
  
|Feature|Beschreibung|Projekt|  
|-------------|-----------------|-------------|  
|Flussdiagramm|Der Geschäftsprozess wird als Flussdiagramm dargestellt. Die Darstellung als Flussdiagramm entspricht der möglichen Darstellung des Prozesses durch ein Unternehmen auf einem Whiteboard.|HiringRequestService|  
|Workflowdienste|Das Flussdiagramm mit der Prozessdefinition wird in einem Dienst gehostet (in diesem Beispiel wird der Dienst in einer Konsolenanwendung gehostet).|HiringRequestService|  
|Messagingaktivitäten|Messagingaktivitäten werden im Flussdiagramm auf zweierlei Weise verwendet:<br /><br /> -Um Informationen über Benutzer (Ermitteln der Entscheidungen sowie diesbezüglicher Informationen in den einzelnen Genehmigungsschritten empfangen) zu erhalten.<br />-So mit anderen Diensten (InboxService und OrgDataService, Verwendung über Dienstverweise) zu interagieren.|HiringRequestService|  
|Inhaltsbasierte Korrelation|Genehmigungsnachrichten werden mit der ID-Eigenschaft der Stellenausschreibung korreliert:<br /><br /> – Wenn ein Prozess gestartet wird, wird das Korrelationshandle mit der ID der Anforderung initialisiert.<br />– ID (der erste Parameter jeder Genehmigungsnachricht ist die ID der Anforderung) korreliert eingehende genehmigungsnachrichten.|HiringRequestService/ResumeRequestService|  
|Benutzerdefinierte Aktivitäten (deklarativ und codebasiert)|Dieses Beispiel enthält verschiedene benutzerdefinierte Aktivitäten:<br /><br /> -   `SaveActionTracking`: Diese Aktivität gibt einen benutzerdefinierten <xref:System.Activities.Tracking.TrackingRecord> (mit <xref:System.Activities.NativeActivityContext.Track%2A>). Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.NativeActivity> mit imperativem Code erstellt.<br />-   `GetEmployeesByPositionTypes`: Diese Aktivität empfängt eine Liste der Stellen-IDs und gibt eine Liste der Personen, die von dieser Stelle bei Contoso haben. Diese Aktivität wurde deklarativ (mit dem Aktivitätsdesigner) erstellt.<br />-   `SaveHiringRequestInfo`: Diese Aktivität speichert die Informationen von einem `HiringRequest` (mit `HiringRequestRepository.Save`). Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.CodeActivity> mit imperativem Code erstellt.|HiringRequestService|  
|Vom System bereitgestellte SQL Server-Persistenz|Die <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz, die als Host für die Prozessdefinition des Flussdiagramms fungiert, ist für die Verwendung der vom System bereitgestellten SQL Server-Persistenz konfiguriert.|HiringRequestService/ResumeRequestService|  
|Benutzerdefinierte Nachverfolgung|Das Beispiel enthält einen benutzerdefinierten Überwachungsteilnehmer, mit dem der Verlauf eines `HiringRequestProcess` (welche Aktion wurde wann von wem ausgeführt) gespeichert wird. Der Quellcode ist im Ordner für die Überwachung von HiringRequestService gespeichert.|HiringRequestService|  
|ETW-Überwachung|Die vom System bereitgestellte ETW-Überwachung wird in der Datei App.config im Dienst HiringRequestService konfiguriert.|HiringRequestService|  
|Komposition von Aktivitäten|Die Prozessdefinition verwendet die freie Komposition von <xref:System.Activities.Activity>. Das Flussdiagramm enthält verschiedene aufeinanderfolgende sowie parallele Aktivitäten, die wiederum andere Aktivitäten enthalten usw.|HiringRequestService|  
|Parallele Aktivitäten|-   <xref:System.Activities.Statements.ParallelForEach%601> wird verwendet, um im Posteingang des Firmenchefs sowie der Personalvorständen parallel (wartet auf beiden Personalvorstände Genehmigungsschritt) zu registrieren.<br />-   <xref:System.Activities.Statements.Parallel> wird verwendet, um verschiedene Aufgaben für die Bereinigung in den Abschluss- und Ablehnungsschritten Schritten ausführen|HiringRequestService|  
|Abbruch des Modells|Im Flussdiagramm wird mit <xref:System.Activities.Statements.CancellationScope> ein Abbruchverhalten erstellt (im vorliegenden Fall werden einige Bereinigungsaufgaben ausgeführt.).|HiringRequestService|  
|Kundenpersistenzteilnehmer|Mit `HiringRequestPersistenceParticipant` werden Daten aus einer Workflowvariablen in einer Tabelle erfasst, die in der Personaldatenbank von Contoso gespeichert ist.|HiringRequestService|  
|Workflowdienste|`ResumeRequestService` wird unter Verwendung von Workflowdiensten implementiert. Die Definition des Workflows sowie Informationen zum Dienst sind in ResumeRequestService.xamlx enthalten. Der Dienst ist für die Verwendung von Persistenz und Überwachung konfiguriert.|ResumeRequestService|  
|Permanente Zeitgeber|`ResumeRequestService` definiert mit permanenten Zeitgebern den Zeitraum für eine Stellenausschreibung (sobald dieser abgelaufen ist, wird die Stellenausschreibung geschlossen).|ResumeRequestService|  
|Transaktionen|Mit <xref:System.Activities.Statements.TransactionScope> wird die Konsistenz der Daten während der Ausführung verschiedener Aktivitäten (bei der Erfassung eines neuen Lebenslaufs) sichergestellt.|ResumeRequestService|  
|Transaktionen|Der benutzerdefinierte Persistenzteilnehmer (`HiringRequestPersistenceParticipant`) und der benutzerdefinierte Überwachungsteilnehmer (`HistoryFileTrackingParticipant`) verwenden die gleiche Transaktion.|HiringRequestService|  
|Verwenden von [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendungen|Auf die Workflows wird durch zwei [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendungen zugegriffen.|InternalClient/CareersWebSite|  
  
## <a name="data-storage"></a>Datenspeicher  
 Die Daten werden in einer SQL Server-Datenbank mit dem Namen `ContosoHR` gespeichert. (Das Skript zum Erstellen der Datenbank befindet sich im Ordner `DbSetup`.) Workflowinstanzen werden in einer SQL Server-Datenbank mit dem Namen `InstanceStore` gespeichert. (Die Skripts zum Erstellen des Instanzspeichers sind Teil von [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].)  
  
 Beide Datenbanken werden durch Ausführen des Skripts Setup.cmd an einer Developer-Eingabeaufforderung für Visual Studio erstellt.  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  
  
#### <a name="to-create-the-databases"></a>So erstellen Sie die Datenbanken  
  
1. Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio.  
  
2. Navigieren Sie zum Beispielordner.  
  
3. Führen Sie Setup.cmd aus.  
  
4. Vergewissern Sie sich, dass die `ContosoHR`-Datenbank und die `InstanceStore`-Datenbank in SQL Express erstellt wurden.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>So richten Sie die Projektmappe für die Ausführung ein  
  
1. Führen Sie Visual Studio als Administrator aus. Öffnen Sie HiringRequest.sln.  
  
2. Mit der rechten Maustaste in der Lösung in **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.  
  
3. Wählen Sie die Option **mehrere Startprojekte** und legen Sie die **CareersWebSite**, **InternalClient**, **HiringRequestService**, und **ResumeRequestService** zu **starten**. Lassen Sie **ContosoHR**, **InboxService**, und **OrgService** mit "None".  
  
4. Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken. Vergewissern Sie sich, dass der Build erfolgreich erstellt wurde.  
  
#### <a name="to-run-the-solution"></a>So führen Sie die Projektmappe aus  
  
1. Drücken Sie nach dem Erstellen der Projektmappe STRG+F5, um diese ohne Debuggen auszuführen. Vergewissern Sie sich, dass alle Dienste gestartet wurden.  
  
2. Klicken Sie mit der rechten Maustaste auf **InternalClient** in der Projektmappe und wählen Sie dann **in Browser anzeigen**. Die Standardseite für `InternalClient` wird angezeigt. Vergewissern Sie sich, dass die Dienste ausgeführt werden, und klicken Sie auf den Link.  
  
3. Die **HiringRequest** Modul wird angezeigt. Sie können dieses Szenario hier detailliert verfolgen.  
  
4. Nachdem der `HiringRequest` abgeschlossen wurde, können Sie den `ResumeRequest` starten. Sie können dieses Szenario hier detailliert verfolgen.  
  
5. Nachdem der `ResumeRequest` gesendet wurde, ist er auf der öffentlichen Website (mit den Stellenanzeigen von Contoso) verfügbar. Navigieren Sie zum Stellenanzeigenportal von Contoso, um die Stellenausschreibung anzuzeigen (und sich zu bewerben).  
  
6. Mit der rechten Maustaste **CareersWebSite** in der Projektmappe, und wählen **in Browser anzeigen**.  
  
7. Navigieren Sie zurück zu den `InternalClient` mit der rechten Maustaste **InternalClient** in der Projektmappe auswählen und **in Browser anzeigen**.  
  
8. Wechseln Sie zu der **JobPostings** Abschnitt, indem Sie auf die **Stellenausschreibungen** Link im oberen Menü Posteingang. Sie können dieses Szenario hier detailliert verfolgen.  
  
## <a name="scenarios"></a>Szenarien  
  
### <a name="hiring-request"></a>Stellenausschreibung  
  
1. Michael Alexander (Softwareentwickler) möchte eine neue Stelle für einen Softwareentwickler ausschreiben, der über mindestens 3 Jahre C#-Erfahrung verfügen muss und mit Tests in der technischen Entwicklungsabteilung betraut werden soll.  
  
2. Nach dem Erstellen die Anforderung wird in Alexanders Posteingang angezeigt (klicken Sie auf **aktualisieren** , wenn die Anforderung nicht angezeigt wird) erwartet Brehm genehmigt, Michael-Manager ist.  
  
3. Peter Brehm regt eine Änderung an der Ausschreibung an. Er ist der Ansicht, dass für die Stelle 5 Jahre C#-Erfahrung erforderlich sind und teilt dies Michael Alexander in einer Anmerkung mit.  
  
4. Dieser sieht die Nachricht seines Vorgesetzten im Posteingang und möchte darauf reagieren. Vergangene Stellenausschreibungen zeigen, dass sein Vorgesetzter recht hat. Er ändert die Stellenausschreibung dahingehend, dass nun 5 Jahre C#-Erfahrung vorausgesetzt werden und akzeptiert die Änderung.  
  
5. Peter Brehm genehmigt nun die geänderte Ausschreibung von Michael Alexander. Als Nächstes muss die Stellenausschreibung vom Entwicklungsvorstand Tsvi Reiter genehmigt werden.  
  
6. Tsvi Reiter möchte die Stellenausschreibung beschleunigen, gibt daher in einem Kommentar an, dass der Vorgang dringend ist, und genehmigt anschließend die Ausschreibung.  
  
7. Abschließend muss die Stellenausschreibung von zwei Personalvorständen oder dem Firmenchef gebilligt werden. Der Firmenchef Brian Richard Goldstein sieht den Dringlichkeitsvermerk des Entwicklungsvorstands Reiter. Er beschließt daher die Konsultation der Personalvorstände zu umgehen und genehmigt die Ausschreibung selbst.  
  
8. Die Ausschreibung wird nun aus dem Posteingang von Michael Alexander entfernt und die Suche nach einem Softwareentwickler kann beginnen.  
  
### <a name="start-resume-request"></a>Erfassung von Lebensläufen  
  
1. Die stellenausschreibung wartet jetzt auf eine externe Website bereitgestellt wird, Interessenten können sich bewerben (Sie sehen, die Sie auf die **Stellenausschreibungen** Link). Die Stellenausschreibung wird derzeit von einem Mitarbeiter der Personalabteilung abschließend bearbeitet und anschließend veröffentlicht.  
  
2. Personalabteilung möchte die stellenausschreibung bearbeiten (durch Klicken auf die **bearbeiten** Link) durch ein Timeout von 60 Minuten festlegen (in der Praxis möglicherweise Tage oder Wochen). Der Gültigkeitszeitraum ermöglicht das Entfernen der Stellenausschreibung von der externen Website nach Ablauf eines bestimmten Zeitraums.  
  
3. Nachdem die bearbeitete stellenausschreibung gespeichert wurde, erscheint in der **Receiving Resumes** Registerkarte (Aktualisieren Sie die Webseite, um die neue stellenausschreibung anzuzeigen).  
  
### <a name="collecting-resumes"></a>Erfassen von Lebensläufen  
  
1. Die Stellenausschreibung soll auf der externen Website angezeigt werden. Interessenten können sich nun auf die Stelle bewerben und ihren Lebenslauf einreichen.  
  
2. Wenn Sie auf der stellenausschreibungen zurückkehren, können Sie "anzeigen wird fortgesetzt", die bisher erfasst wurden.  
  
3. Die Erfassung von Lebensläufen kann von der Personalabteilung auch beendet werden (etwa nachdem die Stelle wunschgemäß besetzt wurde).  
  
## <a name="troubleshooting"></a>Problembehandlung  
  
1. Stellen Sie sicher, dass Sie Visual Studio mit Administratorrechten ausgeführt werden.  
  
2. Überprüfen Sie Folgendes, falls die Projektmappe nicht erstellt werden kann:  
  
    - Der Verweis auf `ContosoHR` nicht fehlt die `InternalClient` oder `CareersWebSite` Projekte.  
  
3. Überprüfen Sie Folgendes, falls die Projektmappe nicht ausgeführt werden kann:  
  
    1. Alle Dienste werden ausgeführt.  
  
    2. Die Dienstverweise werden aktualisiert.  
  
        1. Öffnen Sie den Ordner App_WebReferences.  
  
        2. Mit der rechten Maustaste **Contoso** , und wählen Sie **Web-/Dienstverweise aktualisieren**.  
  
        3. Erstellen Sie die Projektmappe durch Drücken von STRG + UMSCHALT + B in Visual Studio neu.  
  
## <a name="uninstalling"></a>Deinstallieren  
  
1. Löschen Sie den SQL Server-Instanzspeicher, indem Sie die Datei Cleanup.bat im Ordner DbSetup ausführen.  
  
2. Entfernen Sie den Quellcode von Ihrer Festplatte.
