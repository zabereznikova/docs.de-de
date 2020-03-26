---
title: Einstellungsprozess
ms.date: 03/30/2017
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
ms.openlocfilehash: ade72422d29d170e9c80f602f151ce765a1a00f7
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291687"
---
# <a name="hiring-process"></a>Einstellungsprozess
In diesem Beispiel wird veranschaulicht, wie ein Geschäftsprozess mit Messagingaktivitäten sowie zwei als Workflowdienste gehostete Workflows implementiert werden. Diese Workflows sind Teil der IT-Infrastruktur des fiktionalen Unternehmens Contoso, Inc.  
  
 Der `HiringRequest`-Workflowprozess (implementiert als <xref:System.Activities.Statements.Flowchart>) erfordert eine Autorisierung durch mehrere Manager in der Organisation. Um dieses Ziel zu erreichen, verwendet der Workflow andere vorhandene Dienste in der Organisation (in unserem Fall einen Posteingangsdienst und einen Organisationsdatendienst, der als reine Windows Communication Foundation (WCF)-Dienste implementiert ist).  
  
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
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## <a name="description-of-the-process"></a>Beschreibung des Vorgangs  
 Contoso, Inc. ist bestrebt, die Belegschaft in den einzelnen Abteilungen möglichst optimal zu gestalten. Bevor ein Mitarbeiter eine Stellenausschreibung initiieren kann und Neueinstellungen möglich sind, muss daher ein entsprechendes Genehmigungsverfahren durchlaufen werden. Dieses Genehmigungsverfahren zur Neueinstellung ist im HiringRequestService-Projekt definiert und umfasst folgende Schritte:  
  
1. Ein Mitarbeiter (der Antragsteller) beantragt eine Neueinstellung.  
  
2. Der Manager des Anforderers muss die Anforderung genehmigen:  
  
    1. Der Antrag kann vom Manager abgelehnt werden.  
  
    2. Der Antrag kann mit der Bitte um weitere Informationen an den Antragsteller zurückgegeben werden:  
  
        1. Der Antragsteller überprüft die Bitte und sendet den Antrag zurück an den Manager.  
  
    3. Der Antrag kann vom Manager genehmigt werden.  
  
3. Nachdem der Manager des Anforderers zugestimmt hat, muss der Abteilungsbesitzer die Anforderung genehmigen:  
  
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
  
|Project|Beschreibung|  
|-------------|-----------------|  
|ContosoHR|Enthält Datenverträge, Geschäftsobjekte und Repository-Klassen.|  
|HiringRequestService|Enthält die Definition des Workflows zum Stellenausschreibungsverfahren.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die den Workflow (XAML-Datei) selbst als Dienst hostet.|  
|ResumeRequestService|Ein Workflowdienst, mit dem die Lebensläufe der Bewerber erfasst werden, bis die Stellenanzeige abläuft oder der Bewerbungsprozess beendet werden muss.<br /><br /> Dieses Projekt wird als deklarativer Workflowdienst (XAMLX) implementiert.|  
|OrgService|Ein Dienst, mit dem organisatorische Informationen (Employees, Positions, PositionTypes und Departments) verfügbar gemacht werden. Sie können sich diesen Dienst als Organisationsmodul im Rahmen der Unternehmensressourcenplanung (ERP) vorstellen.<br /><br /> Dieses Projekt wird als Konsolenanwendung implementiert, die einen Windows Communication Foundation (WCF)-Dienst verfügbar macht.|  
|InboxService|Ein Posteingang mit aktionsfähigen Aufgaben für Mitarbeiter.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die einen WCF-Dienst verfügbar macht.|  
|InternalClient|Eine Webanwendung zur Interaktion mit dem Prozess. Benutzer können HiringProcess-Workflows anzeigen, starten sowie daran teilnehmen. Mit dieser Anwendung können außerdem ResumeRequest-Prozesse gestartet und überwacht werden.<br /><br /> Diese Site ist als interne Site für das Intranet von Contoso implementiert. Dieses Projekt ist als ASP.NET-Website implementiert.|  
|CareersWebSite|Eine externe Website, mit der offene Stellen von Contoso bekannt gemacht werden. Bewerber können zu dieser Seite navigieren und ihren Lebenslauf einreichen.|  
  
## <a name="feature-summary"></a>Zusammenfassung der Funktionen  
 In der folgenden Tabelle wird die Verwendung der einzelnen Funktionen in diesem Beispiel beschrieben.  
  
|Funktion|Beschreibung|Project|  
|-------------|-----------------|-------------|  
|Flussdiagramm|Der Geschäftsprozess wird als Flussdiagramm dargestellt. Die Darstellung als Flussdiagramm entspricht der möglichen Darstellung des Prozesses durch ein Unternehmen auf einem Whiteboard.|HiringRequestService|  
|Workflowdienste|Das Flussdiagramm mit der Prozessdefinition wird in einem Dienst gehostet (in diesem Beispiel wird der Dienst in einer Konsolenanwendung gehostet).|HiringRequestService|  
|Messagingaktivitäten|Messagingaktivitäten werden im Flussdiagramm auf zweierlei Weise verwendet:<br /><br /> - Um Informationen vom Benutzer zu erhalten (um die Entscheidungen und die zugehörigen Informationen in jedem Genehmigungsschritt zu erhalten).<br />- Zur Interaktion mit anderen vorhandenen Diensten (InboxService und OrgDataService, die über Dienstverweise verwendet werden).|HiringRequestService|  
|Inhaltsbasierte Korrelation|Genehmigungsnachrichten werden mit der ID-Eigenschaft der Stellenausschreibung korreliert:<br /><br /> - Wenn ein Prozess gestartet wird, wird das Korrelationshandle mit der ID der Anforderung initialisiert.<br />- Eingehende Genehmigungsmeldungen korrelieren mit ihrer ID (der erste Parameter jeder Genehmigungsnachricht ist die ID der Anforderung).|HiringRequestService/ResumeRequestService|  
|Benutzerdefinierte Aktivitäten (deklarativ und codebasiert)|Dieses Beispiel enthält verschiedene benutzerdefinierte Aktivitäten:<br /><br /> -   `SaveActionTracking`: Diese Aktivität gibt <xref:System.Activities.Tracking.TrackingRecord> eine <xref:System.Activities.NativeActivityContext.Track%2A>benutzerdefinierte (verwendung ) aus. Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.NativeActivity> mit imperativem Code erstellt.<br />-   `GetEmployeesByPositionTypes`: Diese Aktivität erhält eine Liste der Positionstyp-IDs und gibt eine Liste der Personen zurück, die diese Position in Contoso haben. Diese Aktivität wurde deklarativ (mit dem Aktivitätsdesigner) erstellt.<br />-   `SaveHiringRequestInfo`: Diese Aktivität speichert `HiringRequest` die `HiringRequestRepository.Save`Informationen von a (verwenden ). Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.CodeActivity> mit imperativem Code erstellt.|HiringRequestService|  
|Vom System bereitgestellte SQL Server-Persistenz|Die <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz, die als Host für die Prozessdefinition des Flussdiagramms fungiert, ist für die Verwendung der vom System bereitgestellten SQL Server-Persistenz konfiguriert.|HiringRequestService/ResumeRequestService|  
|Benutzerdefinierte Nachverfolgung|Das Beispiel enthält einen benutzerdefinierten Überwachungsteilnehmer, mit dem der Verlauf eines `HiringRequestProcess` (welche Aktion wurde wann von wem ausgeführt) gespeichert wird. Der Quellcode ist im Ordner für die Überwachung von HiringRequestService gespeichert.|HiringRequestService|  
|ETW-Überwachung|Die vom System bereitgestellte ETW-Überwachung wird in der Datei App.config im Dienst HiringRequestService konfiguriert.|HiringRequestService|  
|Komposition von Aktivitäten|Die Prozessdefinition verwendet die freie Komposition von <xref:System.Activities.Activity>. Das Flussdiagramm enthält verschiedene aufeinanderfolgende sowie parallele Aktivitäten, die wiederum andere Aktivitäten enthalten usw.|HiringRequestService|  
|Parallele Aktivitäten|-   <xref:System.Activities.Statements.ParallelForEach%601>wird verwendet, um sich parallel im Posteingang des CEO und der HR Manager zu registrieren (Warten auf den Genehmigungsschritt von zwei HR-Managern).<br />-   <xref:System.Activities.Statements.Parallel>wird verwendet, um einige Bereinigungsaufgaben in den Schritten Abgeschlossen und Abgelehnt auszuführen|HiringRequestService|  
|Abbruch des Modells|Im Flussdiagramm wird mit <xref:System.Activities.Statements.CancellationScope> ein Abbruchverhalten erstellt (im vorliegenden Fall werden einige Bereinigungsaufgaben ausgeführt.).|HiringRequestService|  
|Kundenpersistenzteilnehmer|Mit `HiringRequestPersistenceParticipant` werden Daten aus einer Workflowvariablen in einer Tabelle erfasst, die in der Personaldatenbank von Contoso gespeichert ist.|HiringRequestService|  
|Workflowdienste|`ResumeRequestService` wird unter Verwendung von Workflowdiensten implementiert. Workflowdefinition und Dienstinformationen sind in ResumeRequestService.xamlx enthalten. Der Dienst ist für die Verwendung von Persistenz und Überwachung konfiguriert.|ResumeRequestService|  
|Permanente Zeitgeber|`ResumeRequestService` definiert mit permanenten Zeitgebern den Zeitraum für eine Stellenausschreibung (sobald dieser abgelaufen ist, wird die Stellenausschreibung geschlossen).|ResumeRequestService|  
|Transaktionen|Mit <xref:System.Activities.Statements.TransactionScope> wird die Konsistenz der Daten während der Ausführung verschiedener Aktivitäten (bei der Erfassung eines neuen Lebenslaufs) sichergestellt.|ResumeRequestService|  
|Transaktionen|Der benutzerdefinierte Persistenzteilnehmer (`HiringRequestPersistenceParticipant`) und der benutzerdefinierte Überwachungsteilnehmer (`HistoryFileTrackingParticipant`) verwenden die gleiche Transaktion.|HiringRequestService|  
|Verwendung [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in ASP.NET Anwendungen.|Auf Workflows wird von zwei ASP.NET Anwendungen zugegriffen.|InternalClient/CareersWebSite|  
  
## <a name="data-storage"></a>Datenspeicherung  
 Die Daten werden in einer SQL Server-Datenbank mit dem Namen `ContosoHR` gespeichert. (Das Skript zum Erstellen der Datenbank befindet sich im Ordner `DbSetup`.) Workflowinstanzen werden in einer SQL Server-Datenbank mit dem Namen `InstanceStore` gespeichert. (Die Skripts zum Erstellen des Instanzspeichers sind Teil von [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].)  
  
 Beide Datenbanken werden erstellt, indem Das Skript Setup.cmd aus einer Entwicklereingabeaufforderung für Visual Studio ausgeführt wird.  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  
  
#### <a name="to-create-the-databases"></a>So erstellen Sie die Datenbanken  
  
1. Öffnen Sie eine Entwicklereingabeaufforderung für Visual Studio.  
  
2. Navigieren Sie zum Beispielordner.  
  
3. Führen Sie Setup.cmd aus.  
  
4. Vergewissern Sie sich, dass die `ContosoHR`-Datenbank und die `InstanceStore`-Datenbank in SQL Express erstellt wurden.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>So richten Sie die Projektmappe für die Ausführung ein  
  
1. Starten Sie Visual Studio als Administrator. Öffnen Sie HiringRequest.sln.  
  
2. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften**aus.  
  
3. Wählen Sie die Option **Mehrere Startprojekte** aus, und legen Sie **die Optionen CareersWebSite**, **InternalClient**, **HiringRequestService**und **ResumeRequestService** auf **Start**fest. Belassen Sie **ContosoHR**, **InboxService**und **OrgService** als Keine.  
  
4. Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken. Vergewissern Sie sich, dass der Build erfolgreich erstellt wurde.  
  
#### <a name="to-run-the-solution"></a>So führen Sie die Projektmappe aus  
  
1. Drücken Sie nach dem Erstellen der Projektmappe STRG+F5, um diese ohne Debuggen auszuführen. Vergewissern Sie sich, dass alle Dienste gestartet wurden.  
  
2. Klicken Sie in der Projektmappe mit der rechten Maustaste auf **InternalClient,** und wählen Sie dann **Ansicht im Browser**aus. Die Standardseite für `InternalClient` wird angezeigt. Vergewissern Sie sich, dass die Dienste ausgeführt werden, und klicken Sie auf den Link.  
  
3. Das **HiringRequest-Modul** wird angezeigt. Sie können dieses Szenario hier detailliert verfolgen.  
  
4. Nachdem der `HiringRequest` abgeschlossen wurde, können Sie den `ResumeRequest` starten. Sie können dieses Szenario hier detailliert verfolgen.  
  
5. Nachdem der `ResumeRequest` gesendet wurde, ist er auf der öffentlichen Website (mit den Stellenanzeigen von Contoso) verfügbar. Navigieren Sie zum Stellenanzeigenportal von Contoso, um die Stellenausschreibung anzuzeigen (und sich zu bewerben).  
  
6. Klicken Sie in der Projektmappe mit der rechten Maustaste auf **CareersWebSite,** und wählen Sie **Ansicht im Browser**aus.  
  
7. Navigieren Sie `InternalClient` zurück zum , indem Sie in der Projektmappe mit der rechten Maustaste auf **InternalClient** klicken und **Ansicht im Browser**auswählen.  
  
8. Wechseln Sie zum Abschnitt **JobPostings,** indem Sie im oberen Posteingang auf den Link **Stellenbuchungen** klicken. Sie können dieses Szenario hier detailliert verfolgen.  
  
## <a name="scenarios"></a>Szenarien  
  
### <a name="hiring-request"></a>Stellenausschreibung  
  
1. Michael Alexander (Softwareentwickler) möchte eine neue Stelle für einen Softwareentwickler ausschreiben, der über mindestens 3 Jahre C#-Erfahrung verfügen muss und mit Tests in der technischen Entwicklungsabteilung betraut werden soll.  
  
2. Nach der Erstellung wird die Anforderung in Michaels Posteingang angezeigt (klicken Sie auf **Aktualisieren,** wenn die Anfrage nicht angezeigt wird), und wartet auf die Zustimmung von Peter Brehm, der Michaels Manager ist.  
  
3. Peter will auf Michaels Wunsch reagieren. Er ist der Ansicht, dass für die Stelle 5 Jahre C#-Erfahrung erforderlich sind und teilt dies Michael Alexander in einer Anmerkung mit.  
  
4. Michael sieht eine Nachricht in seinem Posteingang von seinem Manager und will handeln. Michael sieht die Geschichte des Positionsbegehrens und stimmt Peter zu. Er ändert die Stellenausschreibung dahingehend, dass nun 5 Jahre C#-Erfahrung vorausgesetzt werden und akzeptiert die Änderung.  
  
5. Peter handelt auf Michaels geänderten Wunsch und nimmt ihn an. Als Nächstes muss die Stellenausschreibung vom Entwicklungsvorstand Tsvi Reiter genehmigt werden.  
  
6. Tsvi Reiter möchte die Stellenausschreibung beschleunigen, gibt daher in einem Kommentar an, dass der Vorgang dringend ist, und genehmigt anschließend die Ausschreibung.  
  
7. Abschließend muss die Stellenausschreibung von zwei Personalvorständen oder dem Firmenchef gebilligt werden. Der Firmenchef Brian Richard Goldstein sieht den Dringlichkeitsvermerk des Entwicklungsvorstands Reiter. Er beschließt daher die Konsultation der Personalvorstände zu umgehen und genehmigt die Ausschreibung selbst.  
  
8. Der Antrag wird aus Michaels Posteingang entfernt und der Prozess der Einstellung eines SDET hat nun begonnen.  
  
### <a name="start-resume-request"></a>Erfassung von Lebensläufen  
  
1. Jetzt wartet die Stellenposition darauf, auf einer externen Website bereitgestellt zu werden, auf der sich Personen bewerben können (Sie können sehen, dass sie auf den Link **Stellenbuchungen klickt).** Die Stellenausschreibung wird derzeit von einem Mitarbeiter der Personalabteilung abschließend bearbeitet und anschließend veröffentlicht.  
  
2. HR möchte diese Stellenposition bearbeiten (durch Klicken auf den **Link Bearbeiten),** indem sie eine Zeiteinstellung von 60 Minuten setzt (im wirklichen Leben können dies Tage oder Wochen sein). Der Gültigkeitszeitraum ermöglicht das Entfernen der Stellenausschreibung von der externen Website nach Ablauf eines bestimmten Zeitraums.  
  
3. Nach dem Speichern der bearbeiteten Auftragsposition wird sie auf der Registerkarte Empfangen von **Resumes** angezeigt (aktualisieren Sie die Webseite, um die neue Auftragsposition anzuzeigen).  
  
### <a name="collecting-resumes"></a>Erfassen von Lebensläufen  
  
1. Die Stellenausschreibung soll auf der externen Website angezeigt werden. Interessenten können sich nun auf die Stelle bewerben und ihren Lebenslauf einreichen.  
  
2. Wenn Sie zum Stellenbuchungslistendienst zurückkehren, können Sie die bisher gesammelten Lebensläufe "anzeigen".  
  
3. Die Erfassung von Lebensläufen kann von der Personalabteilung auch beendet werden (etwa nachdem die Stelle wunschgemäß besetzt wurde).  
  
## <a name="troubleshooting"></a>Problembehandlung  
  
1. Stellen Sie sicher, dass Sie Visual Studio mit Administratorrechten ausführen.  
  
2. Überprüfen Sie Folgendes, falls die Projektmappe nicht erstellt werden kann:  
  
    - Der Verweis `ContosoHR` auf fehlt `InternalClient` nicht `CareersWebSite` in der oder Projekte.  
  
3. Überprüfen Sie Folgendes, falls die Projektmappe nicht ausgeführt werden kann:  
  
    1. Alle Dienste werden ausgeführt.  
  
    2. Die Dienstverweise werden aktualisiert.  
  
        1. Öffnen Sie den Ordner App_WebReferences.  
  
        2. Klicken Sie mit der rechten Maustaste auf **Contoso,** und wählen Sie **Web-/Dienstreferenzen aktualisieren**aus.  
  
        3. Erstellen Sie die Lösung neu, indem Sie STRG+SHIFT+B in Visual Studio drücken.  
  
## <a name="uninstalling"></a>Deinstallieren  
  
1. Löschen Sie den SQL Server-Instanzspeicher, indem Sie die Datei Cleanup.bat im Ordner DbSetup ausführen.  
  
2. Entfernen Sie den Quellcode von Ihrer Festplatte.
