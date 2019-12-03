---
title: Einstellungsprozess
ms.date: 03/30/2017
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
ms.openlocfilehash: 02968acfc762550c9010dd0ed29acbca845e08bb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715978"
---
# <a name="hiring-process"></a>Einstellungsprozess
In diesem Beispiel wird veranschaulicht, wie ein Geschäftsprozess mit Messagingaktivitäten sowie zwei als Workflowdienste gehostete Workflows implementiert werden. Diese Workflows sind Teil der IT-Infrastruktur des fiktionalen Unternehmens Contoso, Inc.  
  
 Der `HiringRequest`-Workflowprozess (implementiert als <xref:System.Activities.Statements.Flowchart>) erfordert eine Autorisierung durch mehrere Manager in der Organisation. Um dieses Ziel zu erreichen, verwendet der Workflow andere vorhandene Dienste in der Organisation (in unserem Fall ein Posteingangs Dienst und ein Organisationsdaten Dienst, der als Plain Windows Communication Foundation (WCF)-Dienste implementiert ist).  
  
 Mit dem `ResumeRequest`-Workflow (implementiert als <xref:System.Activities.Statements.Sequence>) wird eine Stellenausschreibung auf der externen Website der Personalabteilung von Contoso veröffentlicht, und die eingehenden Lebensläufe werden verwaltet. Die Stellenausschreibung ist auf der externen Website des Unternehmens abrufbar, bis ein diesbezüglich festgelegter Zeitraum abgelaufen ist oder sie von einem Mitarbeiter von Contoso entfernt wird.  
  
 In diesem Beispiel werden die folgenden Funktionen von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] veranschaulicht:  
  
- <xref:System.Activities.Statements.Flowchart>-Workflow und <xref:System.Activities.Statements.Sequence>-Workflow zur Modellierung von Geschäftsprozessen  
  
- Workflowdienste.  
  
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
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
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
  
|-Projekt|Beschreibung|  
|-------------|-----------------|  
|ContosoHR|Enthält Datenverträge, Geschäftsobjekte und Repositoryklassen.|  
|HiringRequestService|Enthält die Definition des Workflows zum Stellenausschreibungsverfahren.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die den Workflow (XAML-Datei) selbst als Dienst hostet.|  
|ResumeRequestService|Ein Workflowdienst, mit dem die Lebensläufe der Bewerber erfasst werden, bis die Stellenanzeige abläuft oder der Bewerbungsprozess beendet werden muss.<br /><br /> Dieses Projekt wird als deklarativer Workflowdienst (XAMLX) implementiert.|  
|OrgService|Ein Dienst, mit dem organisatorische Informationen (Employees, Positions, PositionTypes und Departments) verfügbar gemacht werden. Sie können sich diesen Dienst als Organisationsmodul im Rahmen der Unternehmensressourcenplanung (ERP) vorstellen.<br /><br /> Dieses Projekt wird als Konsolenanwendung implementiert, die einen Windows Communication Foundation (WCF)-Dienst verfügbar macht.|  
|InboxService|Ein Posteingang mit aktionsfähigen Aufgaben für Mitarbeiter.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die einen WCF-Dienst verfügbar macht.|  
|InternalClient|Eine Webanwendung zur Interaktion mit dem Prozess. Benutzer können HiringProcess-Workflows anzeigen, starten sowie daran teilnehmen. Mit dieser Anwendung können außerdem ResumeRequest-Prozesse gestartet und überwacht werden.<br /><br /> Diese Site ist als interne Site für das Intranet von Contoso implementiert. Dieses Projekt ist als ASP.NET-Website implementiert.|  
|CareersWebSite|Eine externe Website, mit der offene Stellen von Contoso bekannt gemacht werden. Bewerber können zu dieser Seite navigieren und ihren Lebenslauf einreichen.|  
  
## <a name="feature-summary"></a>Zusammenfassung der Funktionen  
 In der folgenden Tabelle wird die Verwendung der einzelnen Funktionen in diesem Beispiel beschrieben.  
  
|Feature|Beschreibung|-Projekt|  
|-------------|-----------------|-------------|  
|Flussdiagramm|Der Geschäftsprozess wird als Flussdiagramm dargestellt. Die Darstellung als Flussdiagramm entspricht der möglichen Darstellung des Prozesses durch ein Unternehmen auf einem Whiteboard.|HiringRequestService|  
|Workflowdienste|Das Flussdiagramm mit der Prozessdefinition wird in einem Dienst gehostet (in diesem Beispiel wird der Dienst in einer Konsolenanwendung gehostet).|HiringRequestService|  
|Messagingaktivitäten|Messagingaktivitäten werden im Flussdiagramm auf zweierlei Weise verwendet:<br /><br /> -Zum Abrufen von Informationen vom Benutzer (zum Empfangen der Entscheidungen und zugehöriger Informationen in den einzelnen Genehmigungs Schritten).<br />-Für die Interaktion mit anderen vorhandenen Diensten (inboxservice und orgdataservice, verwendet durch Dienst Verweise).|HiringRequestService|  
|Inhaltsbasierte Korrelation|Genehmigungsnachrichten werden mit der ID-Eigenschaft der Stellenausschreibung korreliert:<br /><br /> -Wenn ein Prozess gestartet wird, wird das Korrelations Handle mit der ID der Anforderung initialisiert.<br />-Eingehende Genehmigungs Nachrichten korrelieren Ihre ID (der erste Parameter jeder Genehmigungs Nachricht ist die ID der Anforderung).|HiringRequestService/ResumeRequestService|  
|Benutzerdefinierte Aktivitäten (deklarativ und codebasiert)|Dieses Beispiel enthält verschiedene benutzerdefinierte Aktivitäten:<br /><br /> -   `SaveActionTracking`: diese Aktivität gibt ein benutzerdefiniertes <xref:System.Activities.Tracking.TrackingRecord> aus (mit <xref:System.Activities.NativeActivityContext.Track%2A>). Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.NativeActivity> mit imperativem Code erstellt.<br />-   `GetEmployeesByPositionTypes`: diese Aktivität empfängt eine Liste der Positionstyp-IDs und gibt eine Liste von Personen zurück, die diese Position in "Tento" aufweisen. Diese Aktivität wurde deklarativ (mit dem Aktivitätsdesigner) erstellt.<br />-   `SaveHiringRequestInfo`: diese Aktivität speichert die Informationen eines `HiringRequest` (mit `HiringRequestRepository.Save`). Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.CodeActivity> mit imperativem Code erstellt.|HiringRequestService|  
|Vom System bereitgestellte SQL Server-Persistenz|Die <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz, die als Host für die Prozessdefinition des Flussdiagramms fungiert, ist für die Verwendung der vom System bereitgestellten SQL Server-Persistenz konfiguriert.|HiringRequestService/ResumeRequestService|  
|Benutzerdefinierte Nachverfolgung|Das Beispiel enthält einen benutzerdefinierten Überwachungsteilnehmer, mit dem der Verlauf eines `HiringRequestProcess` (welche Aktion wurde wann von wem ausgeführt) gespeichert wird. Der Quellcode ist im Ordner für die Überwachung von HiringRequestService gespeichert.|HiringRequestService|  
|ETW-Überwachung|Die vom System bereitgestellte ETW-Überwachung wird in der Datei App.config im Dienst HiringRequestService konfiguriert.|HiringRequestService|  
|Komposition von Aktivitäten|Die Prozessdefinition verwendet die freie Komposition von <xref:System.Activities.Activity>. Das Flussdiagramm enthält verschiedene aufeinanderfolgende sowie parallele Aktivitäten, die wiederum andere Aktivitäten enthalten usw.|HiringRequestService|  
|Parallelaktivitäten|-   <xref:System.Activities.Statements.ParallelForEach%601> wird für die parallele Registrierung in der Eingangsbox des CEO und der Personalabteilung verwendet (wartet auf den Genehmigungs Schritt für zwei Personalmanager).<br />-   <xref:System.Activities.Statements.Parallel> wird verwendet, um in den abgeschlossenen und abgelehnten Schritten einige Bereinigungs Aufgaben auszuführen.|HiringRequestService|  
|Abbruch des Modells|Im Flussdiagramm wird mit <xref:System.Activities.Statements.CancellationScope> ein Abbruchverhalten erstellt (im vorliegenden Fall werden einige Bereinigungsaufgaben ausgeführt.).|HiringRequestService|  
|Kundenpersistenzteilnehmer|Mit `HiringRequestPersistenceParticipant` werden Daten aus einer Workflowvariablen in einer Tabelle erfasst, die in der Personaldatenbank von Contoso gespeichert ist.|HiringRequestService|  
|Workflowdienste|`ResumeRequestService` wird unter Verwendung von Workflowdiensten implementiert. Die Definition des Workflows sowie Informationen zum Dienst sind in ResumeRequestService.xamlx enthalten. Der Dienst ist für die Verwendung von Persistenz und Überwachung konfiguriert.|ResumeRequestService|  
|Dauerhafte Timer|`ResumeRequestService` definiert mit permanenten Zeitgebern den Zeitraum für eine Stellenausschreibung (sobald dieser abgelaufen ist, wird die Stellenausschreibung geschlossen).|ResumeRequestService|  
|Transaktionen|Mit <xref:System.Activities.Statements.TransactionScope> wird die Konsistenz der Daten während der Ausführung verschiedener Aktivitäten (bei der Erfassung eines neuen Lebenslaufs) sichergestellt.|ResumeRequestService|  
|Transaktionen|Der benutzerdefinierte Persistenzteilnehmer (`HiringRequestPersistenceParticipant`) und der benutzerdefinierte Überwachungsteilnehmer (`HistoryFileTrackingParticipant`) verwenden die gleiche Transaktion.|HiringRequestService|  
|Verwenden von [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in ASP.NET-Anwendungen.|Der Zugriff auf Workflows erfolgt über zwei ASP.NET-Anwendungen.|InternalClient/CareersWebSite|  
  
## <a name="data-storage"></a>Datenspeicher  
 Die Daten werden in einer SQL Server-Datenbank mit dem Namen `ContosoHR` gespeichert. (Das Skript zum Erstellen der Datenbank befindet sich im Ordner `DbSetup`.) Workflowinstanzen werden in einer SQL Server-Datenbank mit dem Namen `InstanceStore` gespeichert. (Die Skripts zum Erstellen des Instanzspeichers sind Teil von [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].)  
  
 Beide Datenbanken werden erstellt, indem Sie das Skript "Setup. cmd" aus einer Developer-Eingabeaufforderung für Visual Studio ausführen.  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  
  
#### <a name="to-create-the-databases"></a>So erstellen Sie die Datenbanken  
  
1. Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio.  
  
2. Navigieren Sie zum Beispielordner.  
  
3. Führen Sie Setup.cmd aus.  
  
4. Vergewissern Sie sich, dass die `ContosoHR`-Datenbank und die `InstanceStore`-Datenbank in SQL Express erstellt wurden.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>So richten Sie die Projektmappe für die Ausführung ein  
  
1. Führen Sie Visual Studio als Administrator aus. Öffnen Sie HiringRequest.sln.  
  
2. Klicken Sie mit der rechten Maustaste auf **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**aus.  
  
3. Wählen Sie die Option **mehrere Start Projekte** aus, und legen Sie **careerswebsite**, **InternalClient**, **hiringrequestservice**und **resumerequestservice** auf **Start**fest. Belassen Sie **condesohr**, **inboxservice**und **orgservice** als None.  
  
4. Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken. Vergewissern Sie sich, dass der Build erfolgreich erstellt wurde.  
  
#### <a name="to-run-the-solution"></a>So führen Sie die Projektmappe aus  
  
1. Drücken Sie nach dem Erstellen der Projektmappe STRG+F5, um diese ohne Debuggen auszuführen. Vergewissern Sie sich, dass alle Dienste gestartet wurden.  
  
2. Klicken Sie in der Projekt Mappe mit der rechten Maustaste auf **InternalClient** , und wählen Sie dann **in Browser anzeigen** Die Standardseite für `InternalClient` wird angezeigt. Vergewissern Sie sich, dass die Dienste ausgeführt werden, und klicken Sie auf den Link.  
  
3. Das **hiringrequest** -Modul wird angezeigt. Sie können dieses Szenario hier detailliert verfolgen.  
  
4. Nachdem der `HiringRequest` abgeschlossen wurde, können Sie den `ResumeRequest` starten. Sie können dieses Szenario hier detailliert verfolgen.  
  
5. Nachdem der `ResumeRequest` gesendet wurde, ist er auf der öffentlichen Website (mit den Stellenanzeigen von Contoso) verfügbar. Navigieren Sie zum Stellenanzeigenportal von Contoso, um die Stellenausschreibung anzuzeigen (und sich zu bewerben).  
  
6. Klicken Sie in der Projekt Mappe mit der rechten Maustaste auf **careerswebsite** , und wählen Sie **in Browser anzeigen**  
  
7. Navigieren Sie zurück zum `InternalClient`, indem Sie in der Projekt Mappe mit der rechten Maustaste auf **InternalClient** klicken und **in Browser anzeigen**auswählen.  
  
8. Wechseln Sie zum Abschnitt **jobpostings** , indem Sie im oberen Menü des Postfachs auf den Link **jobpostings** klicken. Sie können dieses Szenario hier detailliert verfolgen.  
  
## <a name="scenarios"></a>Szenarien  
  
### <a name="hiring-request"></a>Stellenausschreibung  
  
1. Michael Alexander (Softwareentwickler) möchte eine neue Stelle für einen Softwareentwickler ausschreiben, der über mindestens 3 Jahre C#-Erfahrung verfügen muss und mit Tests in der technischen Entwicklungsabteilung betraut werden soll.  
  
2. Nachdem die Anforderung erstellt wurde, wird Sie in der Eingangsbox von Michael angezeigt (Klicken Sie auf **Aktualisieren** , wenn die Anforderung nicht angezeigt wird), die die Genehmigung von Peter Brehm erwartet hat  
  
3. Peter Brehm regt eine Änderung an der Ausschreibung an. Er ist der Ansicht, dass für die Stelle 5 Jahre C#-Erfahrung erforderlich sind und teilt dies Michael Alexander in einer Anmerkung mit.  
  
4. Michael sieht in seinem Posteingang eine Nachricht von seinem Vorgesetzten und möchte agieren. Michael sieht den Verlauf der Positions Anforderung und ist mit Peter einverstanden. Er ändert die Stellenausschreibung dahingehend, dass nun 5 Jahre C#-Erfahrung vorausgesetzt werden und akzeptiert die Änderung.  
  
5. Peter Brehm genehmigt nun die geänderte Ausschreibung von Michael Alexander. Als Nächstes muss die Stellenausschreibung vom Entwicklungsvorstand Tsvi Reiter genehmigt werden.  
  
6. Tsvi Reiter möchte die Stellenausschreibung beschleunigen, gibt daher in einem Kommentar an, dass der Vorgang dringend ist, und genehmigt anschließend die Ausschreibung.  
  
7. Abschließend muss die Stellenausschreibung von zwei Personalvorständen oder dem Firmenchef gebilligt werden. Der Firmenchef Brian Richard Goldstein sieht den Dringlichkeitsvermerk des Entwicklungsvorstands Reiter. Er beschließt daher die Konsultation der Personalvorstände zu umgehen und genehmigt die Ausschreibung selbst.  
  
8. Die Ausschreibung wird nun aus dem Posteingang von Michael Alexander entfernt und die Suche nach einem Softwareentwickler kann beginnen.  
  
### <a name="start-resume-request"></a>Erfassung von Lebensläufen  
  
1. Nun wartet die Auftrags Position darauf, auf einer externen Website bereitgestellt zu werden, auf der sich die Benutzer bewerben können (Sie können sehen, dass Sie auf den Link **jobpostings** klicken). Die Stellenausschreibung wird derzeit von einem Mitarbeiter der Personalabteilung abschließend bearbeitet und anschließend veröffentlicht.  
  
2. HR möchte diese Auftrags Position bearbeiten (durch Klicken auf den Link **Bearbeiten** ), indem ein Timeout von 60 Minuten festgelegt wird (in der Praxis können dies Tage oder Wochen sein). Der Gültigkeitszeitraum ermöglicht das Entfernen der Stellenausschreibung von der externen Website nach Ablauf eines bestimmten Zeitraums.  
  
3. Nachdem die bearbeitete Auftrags Position gespeichert wurde, wird Sie auf der Registerkarte **empfangende** Fortsetzung angezeigt (aktualisieren Sie die Webseite, um die neue Position des Auftrags anzuzeigen).  
  
### <a name="collecting-resumes"></a>Erfassen von Lebensläufen  
  
1. Die Stellenausschreibung soll auf der externen Website angezeigt werden. Interessenten können sich nun auf die Stelle bewerben und ihren Lebenslauf einreichen.  
  
2. Wenn Sie zum Listen Dienst "Auftrags Beiträge" zurückkehren, können Sie die bisher gesammelten "anzeigen" fortsetzen.  
  
3. Die Erfassung von Lebensläufen kann von der Personalabteilung auch beendet werden (etwa nachdem die Stelle wunschgemäß besetzt wurde).  
  
## <a name="troubleshooting"></a>Problembehandlung  
  
1. Stellen Sie sicher, dass Sie Visual Studio mit Administratorrechten ausführen.  
  
2. Überprüfen Sie Folgendes, falls die Projektmappe nicht erstellt werden kann:  
  
    - Der Verweis auf `ContosoHR` fehlt in den `InternalClient`-oder `CareersWebSite` Projekten.  
  
3. Überprüfen Sie Folgendes, falls die Projektmappe nicht ausgeführt werden kann:  
  
    1. Alle Dienste werden ausgeführt.  
  
    2. Die Dienstverweise werden aktualisiert.  
  
        1. Öffnen Sie den Ordner App_WebReferences.  
  
        2. Klicken Sie mit der rechten Maustaste auf "", und **Wählen Sie** **Web-/Dienstverweise aktualisieren**.  
  
        3. Erstellen Sie die Projekt Mappe neu, indem Sie STRG + UMSCHALT + B in Visual Studio drücken.  
  
## <a name="uninstalling"></a>wird deinstalliert  
  
1. Löschen Sie den SQL Server-Instanzspeicher, indem Sie die Datei Cleanup.bat im Ordner DbSetup ausführen.  
  
2. Entfernen Sie den Quellcode von Ihrer Festplatte.
