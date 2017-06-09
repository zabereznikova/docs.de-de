---
title: "Einstellungsprozess | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Einstellungsprozess
In diesem Beispiel wird veranschaulicht, wie ein Geschäftsprozess mit Messagingaktivitäten sowie zwei als Workflowdienste gehostete Workflows implementiert werden.Diese Workflows sind Teil der IT\-Infrastruktur des fiktionalen Unternehmens Contoso, Inc.  
  
 Der `HiringRequest`\-Workflowprozess \(implementiert als <xref:System.Activities.Statements.Flowchart>\) erfordert eine Autorisierung durch mehrere Manager in der Organisation.Zu diesem Zweck werden vom Workflow bestehende Dienste in der Organisation genutzt \(im vorliegenden Fall ein Posteingangsdienst sowie ein Datenorganisationsdienst, die als einfache [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste implementiert sind\).  
  
 Mit dem `ResumeRequest`\-Workflow \(implementiert als <xref:System.Activities.Statements.Sequence>\) wird eine Stellenausschreibung auf der externen Website der Personalabteilung von Contoso veröffentlicht, und die eingehenden Lebensläufe werden verwaltet.Die Stellenausschreibung ist auf der externen Website des Unternehmens abrufbar, bis ein diesbezüglich festgelegter Zeitraum abgelaufen ist oder sie von einem Mitarbeiter von Contoso entfernt wird.  
  
 In diesem Beispiel werden die folgenden Funktionen von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] veranschaulicht:  
  
-   <xref:System.Activities.Statements.Flowchart>\-Workflow und <xref:System.Activities.Statements.Sequence>\-Workflow zur Modellierung von Geschäftsprozessen  
  
-   Workflowdienste  
  
-   Messagingaktivitäten  
  
-   Inhaltsbasierte Korrelation  
  
-   Benutzerdefinierte Aktivitäten \(deklarativ und codebasiert\)  
  
-   Vom System bereitgestellte SQL Server\-Persistenz  
  
-   <xref:System.Activities.Persistence.PersistenceParticipant> \(benutzerdefiniert\)  
  
-   Benutzerdefinierte Nachverfolgung  
  
-   Ereignisablaufverfolgung \(ETW\) für Windows  
  
-   Komposition von Aktivitäten  
  
-   <xref:System.Activities.Statements.Parallel>\-Aktivitäten  
  
-   <xref:System.Activities.Statements.CancellationScope>\-Aktivität  
  
-   Permanente Zeitgeber \(<xref:System.Activities.Statements.Delay>\-Aktivität\)  
  
-   Transaktionen  
  
-   Mehrere Workflows in einer Projektmappe  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## Beschreibung des Vorgangs  
 Contoso, Inc.ist bestrebt, die Belegschaft in den einzelnen Abteilungen möglichst optimal zu gestalten.Bevor ein Mitarbeiter eine Stellenausschreibung initiieren kann und Neueinstellungen möglich sind, muss daher ein entsprechendes Genehmigungsverfahren durchlaufen werden.Dieses Genehmigungsverfahren zur Neueinstellung ist im HiringRequestService\-Projekt definiert und umfasst folgende Schritte:  
  
1.  Ein Mitarbeiter \(der Antragsteller\) beantragt eine Neueinstellung.  
  
2.  Diese muss vom verantwortlichen Manager genehmigt werden:  
  
    1.  Der Antrag kann vom Manager abgelehnt werden.  
  
    2.  Der Antrag kann mit der Bitte um weitere Informationen an den Antragsteller zurückgegeben werden:  
  
        1.  Der Antragsteller überprüft die Bitte und sendet den Antrag zurück an den Manager.  
  
    3.  Der Antrag kann vom Manager genehmigt werden.  
  
3.  Nachdem der Antrag vom zuständigen Manager genehmigt wurde, muss er vom Abteilungsleiter abgesegnet werden:  
  
    1.  Der Antrag kann vom Abteilungsleiter zurückgewiesen werden.  
  
    2.  Der Antrag kann vom Abteilungsleiter genehmigt werden.  
  
4.  Nach der Genehmigung durch den Abteilungsleiter muss der Vorgang noch von 2 Personalvorständen oder vom Firmenchef autorisiert werden:  
  
    1.  Der Vorgang kann dann in den Zustand der Genehmigung oder Ablehnung übergehen.  
  
    2.  Wenn der Vorgang genehmigt wurde, wird eine neue Instanz des `ResumeRequest`\-Workflows gestartet \(`ResumeRequest` ist über einen Dienstverweis mit HiringRequest.csproj verknüpft.\)  
  
 Nachdem die Neueinstellung von den Managern gebilligt wurde, muss von der Personalabteilung eine geeignete Person gefunden werden.Dieser Vorgang wird vom zweiten Workflow \(`ResumeRequest`, definiert in ResumeRequestService.csproj\) durchgeführt.Mit diesem Workflow wird der Ablauf für die Veröffentlichung einer Stellenausschreibung auf der externen Website mit Stellenausschreibungen von Contoso definiert. Eingehende Lebensläufe werden erfasst, und der Status der Stellenausschreibung wird überwacht.Stellenausschreibungen sind abrufbar, bis ein diesbezüglich festgelegter Zeitraum abgelaufen ist oder sie von einem Mitarbeiter von Contoso entfernt werden.Der `ResumeRequest`\-Workflow besteht aus den folgenden Schritten:  
  
1.  Ein Mitarbeiter von Contoso gibt die Stelleninformationen ein und legt einen Zeitraum für die Ausschreibung fest.Nachdem die Informationen eingegeben wurden, wird die Stelle auf der Website mit Stellenanzeigen veröffentlicht.  
  
2.  Interessierte Personen können jetzt ihren Lebenslauf einreichen.Eingereichte Lebensläufe werden als Datensätze gespeichert und mit der Stellenausschreibung verknüpft.  
  
3.  Bewerber können Lebensläufe einreichen, bis die Stellenanzeige abgelaufen ist oder der Bewerbungsprozess von einem Mitarbeiter von Contoso ausdrücklich beendet und die Anzeige entfernt wird.  
  
## Projekte im Beispiel  
 In der folgenden Tabelle werden die Projekte in der Beispielprojektmappe aufgeführt:  
  
|Projekt|Beschreibung|  
|-------------|------------------|  
|ContosoHR|Enthält Datenverträge, Geschäftsobjekte und Repositoryklassen.|  
|HiringRequestService|Enthält die Definition des Workflows zum Stellenausschreibungsverfahren.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die den Workflow \(XAML\-Datei\) selbst als Dienst hostet.|  
|ResumeRequestService|Ein Workflowdienst, mit dem die Lebensläufe der Bewerber erfasst werden, bis die Stellenanzeige abläuft oder der Bewerbungsprozess beendet werden muss.<br /><br /> Dieses Projekt wird als deklarativer Workflowdienst \(XAMLX\) implementiert.|  
|OrgService|Ein Dienst, mit dem organisatorische Informationen \(Employees, Positions, PositionTypes und Departments\) verfügbar gemacht werden.Sie können sich diesen Dienst als Organisationsmodul im Rahmen der Unternehmensressourcenplanung \(ERP\) vorstellen.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst verfügbar macht.|  
|InboxService|Ein Posteingang mit aktionsfähigen Aufgaben für Mitarbeiter.<br /><br /> Dieses Projekt ist als Konsolenanwendung implementiert, die einen WCF\-Dienst verfügbar macht.|  
|InternalClient|Eine Webanwendung zur Interaktion mit dem Prozess.Benutzer können HiringProcess\-Workflows anzeigen, starten sowie daran teilnehmen.Mit dieser Anwendung können außerdem ResumeRequest\-Prozesse gestartet und überwacht werden.<br /><br /> Diese Site ist als interne Site für das Intranet von Contoso implementiert.Dieses Projekt ist als ASP.NET\-Website implementiert.|  
|CareersWebSite|Eine externe Website, mit der offene Stellen von Contoso bekannt gemacht werden.Bewerber können zu dieser Seite navigieren und ihren Lebenslauf einreichen.|  
  
## Zusammenfassung der Funktionen  
 In der folgenden Tabelle wird die Verwendung der einzelnen Funktionen in diesem Beispiel beschrieben.  
  
|Funktion|Beschreibung|Projekt|  
|--------------|------------------|-------------|  
|Flussdiagramm|Der Geschäftsprozess wird als Flussdiagramm dargestellt.Die Darstellung als Flussdiagramm entspricht der möglichen Darstellung des Prozesses durch ein Unternehmen auf einem Whiteboard.|HiringRequestService|  
|Workflowdienste|Das Flussdiagramm mit der Prozessdefinition wird in einem Dienst gehostet \(in diesem Beispiel wird der Dienst in einer Konsolenanwendung gehostet\).|HiringRequestService|  
|Messagingaktivitäten|Messagingaktivitäten werden im Flussdiagramm auf zweierlei Weise verwendet:<br /><br /> -   Abrufen von Informationen vom Benutzer \(Ermitteln der Entscheidungen sowie diesbezüglicher Informationen in den einzelnen Genehmigungsschritten\)<br />-   Interaktion mit anderen Diensten \(InboxService und OrgDataService, Verwendung über Dienstverweise\)|HiringRequestService|  
|Inhaltsbasierte Korrelation|Genehmigungsnachrichten werden mit der ID\-Eigenschaft der Stellenausschreibung korreliert:<br /><br /> -   Beim Starten eines Prozesses wird das Korrelationshandle mit der ID der Ausschreibung initialisiert.<br />-   Eingehende Genehmigungsnachrichten werden mit der ID korreliert \(der erste Parameter jeder Genehmigungsnachricht stellt die ID der Anforderung dar\).|HiringRequestService\/ResumeRequestService|  
|Benutzerdefinierte Aktivitäten \(deklarativ und codebasiert\)|Dieses Beispiel enthält verschiedene benutzerdefinierte Aktivitäten:<br /><br /> -   `SaveActionTracking`: Diese Aktivität gibt einen benutzerdefinierten <xref:System.Activities.Tracking.TrackingRecord> \(mit <xref:System.Activities.NativeActivityContext.Track%2A>\) aus.Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.NativeActivity> mit imperativem Code erstellt.<br />-   `GetEmployeesByPositionTypes`: Diese Aktivität empfängt eine Liste der Stellen\-IDs und gibt eine Liste der Personen mit dieser Stelle bei Contoso zurück.Diese Aktivität wurde deklarativ \(mit dem Aktivitätsdesigner\) erstellt.<br />-   `SaveHiringRequestInfo`: Durch diese Aktivität werden die Informationen eines `HiringRequest` \(mit `HiringRequestRepository.Save`\) gespeichert.Diese Aktivität wurde durch Erweiterung der <xref:System.Activities.CodeActivity> mit imperativem Code erstellt.|HiringRequestService|  
|Vom System bereitgestellte SQL Server\-Persistenz|Die <xref:System.ServiceModel.Activities.WorkflowServiceHost>\-Instanz, die als Host für die Prozessdefinition des Flussdiagramms fungiert, ist für die Verwendung der vom System bereitgestellten SQL Server\-Persistenz konfiguriert.|HiringRequestService\/ResumeRequestService|  
|Benutzerdefinierte Nachverfolgung|Das Beispiel enthält einen benutzerdefinierten Überwachungsteilnehmer, mit dem der Verlauf eines `HiringRequestProcess` \(welche Aktion wurde wann von wem ausgeführt\) gespeichert wird.Der Quellcode ist im Ordner für die Überwachung von HiringRequestService gespeichert.|HiringRequestService|  
|ETW\-Überwachung|Die vom System bereitgestellte ETW\-Überwachung wird in der Datei App.config im Dienst HiringRequestService konfiguriert.|HiringRequestService|  
|Komposition von Aktivitäten|Die Prozessdefinition verwendet die freie Komposition von <xref:System.Activities.Activity>.Das Flussdiagramm enthält verschiedene aufeinanderfolgende sowie parallele Aktivitäten, die wiederum andere Aktivitäten enthalten usw.|HiringRequestService|  
|Parallele Aktivitäten|-   Mit <xref:System.Activities.Statements.ParallelForEach%601> wird eine parallele Registrierung im Posteingang des Firmenchefs sowie der Personalvorstände vorgenommen \(Genehmigungsschritt durch die beiden Personalvorstände ausstehend\).<br />-   <xref:System.Activities.Statements.Parallel> wird für verschiedene Bereinigungsaufgaben in den Abschluss\- und Ablehnungsschritten verwendet.|HiringRequestService|  
|Abbruch des Modells|Im Flussdiagramm wird mit <xref:System.Activities.Statements.CancellationScope> ein Abbruchverhalten erstellt \(im vorliegenden Fall werden einige Bereinigungsaufgaben ausgeführt.\).|HiringRequestService|  
|Kundenpersistenzteilnehmer|Mit `HiringRequestPersistenceParticipant` werden Daten aus einer Workflowvariablen in einer Tabelle erfasst, die in der Personaldatenbank von Contoso gespeichert ist.|HiringRequestService|  
|Workflowdienste|`ResumeRequestService` wird unter Verwendung von Workflowdiensten implementiert.Die Definition des Workflows sowie Informationen zum Dienst sind in ResumeRequestService.xamlx enthalten.Der Dienst ist für die Verwendung von Persistenz und Überwachung konfiguriert.|ResumeRequestService|  
|Permanente Zeitgeber|`ResumeRequestService` definiert mit permanenten Zeitgebern den Zeitraum für eine Stellenausschreibung \(sobald dieser abgelaufen ist, wird die Stellenausschreibung geschlossen\).|ResumeRequestService|  
|Transaktionen|Mit <xref:System.Activities.Statements.TransactionScope> wird die Konsistenz der Daten während der Ausführung verschiedener Aktivitäten \(bei der Erfassung eines neuen Lebenslaufs\) sichergestellt.|ResumeRequestService|  
|Transaktionen|Der benutzerdefinierte Persistenzteilnehmer \(`HiringRequestPersistenceParticipant`\) und der benutzerdefinierte Überwachungsteilnehmer \(`HistoryFileTrackingParticipant`\) verwenden die gleiche Transaktion.|HiringRequestService|  
|Verwenden von [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendungen|Auf die Workflows wird durch zwei [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendungen zugegriffen.|InternalClient\/CareersWebSite|  
  
## Datenspeicher  
 Die Daten werden in einer SQL Server\-Datenbank mit dem Namen `ContosoHR` gespeichert. \(Das Skript zum Erstellen der Datenbank befindet sich im Ordner `DbSetup`.\)Workflowinstanzen werden in einer SQL Server\-Datenbank mit dem Namen `InstanceStore` gespeichert. \(Die Skripts zum Erstellen des Instanzspeichers sind Teil von [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].\)  
  
 Beide Datenbanken werden durch Ausführen des Skripts Setup.cmd an einer [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]\-Eingabeaufforderung erstellt.  
  
## Ausführen des Beispiels  
  
#### So erstellen Sie die Datenbanken  
  
1.  Öffnen Sie eine [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]\-Eingabeaufforderung.  
  
2.  Navigieren Sie zum Beispielordner.  
  
3.  Führen Sie Setup.cmd aus.  
  
4.  Vergewissern Sie sich, dass die `ContosoHR`\-Datenbank und die `InstanceStore`\-Datenbank in SQL Express erstellt wurden.  
  
#### So richten Sie die Projektmappe für die Ausführung ein  
  
1.  Führen Sie [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] als Administrator aus.Öffnen Sie HiringRequest.sln.  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften** aus.  
  
3.  Wählen Sie die Option **Mehrere Startprojekte** aus, und legen Sie **CareersWebSite**, **InternalClient**, **HiringRequestService** sowie **ResumeRequestService** auf **Start** fest.Behalten Sie für **ContosoHR**, **InboxService** und **OrgService** den Wert Keine bei.  
  
4.  Erstellen Sie die Projektmappe, indem Sie STRG\+UMSCHALT\+B drücken.Vergewissern Sie sich, dass der Build erfolgreich erstellt wurde.  
  
#### So führen Sie die Projektmappe aus  
  
1.  Drücken Sie nach dem Erstellen der Projektmappe STRG\+F5, um diese ohne Debuggen auszuführen.Vergewissern Sie sich, dass alle Dienste gestartet wurden.  
  
2.  Klicken Sie in der Projektmappe mit der rechten Maustaste auf **InternalClient**, und wählen Sie **In Browser anzeigen** aus.Die Standardseite für `InternalClient` wird angezeigt.Vergewissern Sie sich, dass die Dienste ausgeführt werden, und klicken Sie auf den Link.  
  
3.  Das Modul **HiringRequest** wird angezeigt.Sie können dieses Szenario hier detailliert verfolgen.  
  
4.  Nachdem der `HiringRequest` abgeschlossen wurde, können Sie den `ResumeRequest` starten.Sie können dieses Szenario hier detailliert verfolgen.  
  
5.  Nachdem der `ResumeRequest` gesendet wurde, ist er auf der öffentlichen Website \(mit den Stellenanzeigen von Contoso\) verfügbar.Navigieren Sie zum Stellenanzeigenportal von Contoso, um die Stellenausschreibung anzuzeigen \(und sich zu bewerben\).  
  
6.  Klicken Sie in der Projektmappe mit der rechten Maustaste auf **CareersWebSite**, und wählen Sie **In Browser anzeigen** aus.  
  
7.  Navigieren Sie wieder zum `InternalClient`, indem Sie in der Projektmappe mit der rechten Maustaste auf **InternalClient** klicken und **In Browser anzeigen** auswählen.  
  
8.  Wechseln Sie zum Abschnitt **JobPostings**, indem Sie oben im Menü des Posteingangs auf den Link **Job Postings** klicken.Sie können dieses Szenario hier detailliert verfolgen.  
  
## Szenarien  
  
### Stellenausschreibung  
  
1.  Michael Alexander \(Softwareentwickler\) möchte eine neue Stelle für einen Softwareentwickler ausschreiben, der über mindestens 3 Jahre C\#\-Erfahrung verfügen muss und mit Tests in der technischen Entwicklungsabteilung betraut werden soll.  
  
2.  Nachdem die Ausschreibung erstellt wurde, wird sie in Michael Alexanders Posteingang angezeigt \(ggf. müssen Sie auf **Aktualisieren** klicken, um die Ausschreibung anzuzeigen\) und muss nun vom zuständigen Manager Peter Brehm genehmigt werden.  
  
3.  Peter Brehm regt eine Änderung an der Ausschreibung an.Er ist der Ansicht, dass für die Stelle 5 Jahre C\#\-Erfahrung erforderlich sind und teilt dies Michael Alexander in einer Anmerkung mit.  
  
4.  Dieser sieht die Nachricht seines Vorgesetzten im Posteingang und möchte darauf reagieren.Vergangene Stellenausschreibungen zeigen, dass sein Vorgesetzter recht hat.Er ändert die Stellenausschreibung dahingehend, dass nun 5 Jahre C\#\-Erfahrung vorausgesetzt werden und akzeptiert die Änderung.  
  
5.  Peter Brehm genehmigt nun die geänderte Ausschreibung von Michael Alexander.Als Nächstes muss die Stellenausschreibung vom Entwicklungsvorstand Tsvi Reiter genehmigt werden.  
  
6.  Tsvi Reiter möchte die Stellenausschreibung beschleunigen, gibt daher in einem Kommentar an, dass der Vorgang dringend ist, und genehmigt anschließend die Ausschreibung.  
  
7.  Abschließend muss die Stellenausschreibung von zwei Personalvorständen oder dem Firmenchef gebilligt werden.Der Firmenchef Brian Richard Goldstein sieht den Dringlichkeitsvermerk des Entwicklungsvorstands Reiter.Er beschließt daher die Konsultation der Personalvorstände zu umgehen und genehmigt die Ausschreibung selbst.  
  
8.  Die Ausschreibung wird nun aus dem Posteingang von Michael Alexander entfernt und die Suche nach einem Softwareentwickler kann beginnen.  
  
### Erfassung von Lebensläufen  
  
1.  Die Stellenausschreibung kann nun auf einer externen Website veröffentlicht werden, und Interessenten können sich bewerben \(Klicken Sie auf den Link **Job Postings**, um die Stelle anzuzeigen.\).Die Stellenausschreibung wird derzeit von einem Mitarbeiter der Personalabteilung abschließend bearbeitet und anschließend veröffentlicht.  
  
2.  Die Personalabteilung möchte die Stellenausschreibung bearbeiten \(durch Klicken auf den Link **Bearbeiten**\) und einen Gültigkeitszeitraum von 60 Minuten festlegen \(in der Realität können dies auch Tage oder Wochen sein\).Der Gültigkeitszeitraum ermöglicht das Entfernen der Stellenausschreibung von der externen Website nach Ablauf eines bestimmten Zeitraums.  
  
3.  Nachdem die bearbeitete Stellenausschreibung gespeichert wurde, wird sie auf der Registerkarte **Receiving Resumes** angezeigt \(Aktualisieren Sie die Website, um die neue Stellenausschreibung anzuzeigen\).  
  
### Erfassen von Lebensläufen  
  
1.  Die Stellenausschreibung soll auf der externen Website angezeigt werden.Interessenten können sich nun auf die Stelle bewerben und ihren Lebenslauf einreichen.  
  
2.  Wenn Sie zur Auflistung der Stellenausschreibungen zurückkehren, können Sie die Lebensläufe anzeigen, die bis zu diesem Zeitpunkt erfasst wurden.  
  
3.  Die Erfassung von Lebensläufen kann von der Personalabteilung auch beendet werden \(etwa nachdem die Stelle wunschgemäß besetzt wurde\).  
  
## Problembehandlung  
  
1.  Vergewissern Sie sich, dass [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] mit Administratorrechten ausgeführt wird.  
  
2.  Überprüfen Sie Folgendes, falls die Projektmappe nicht erstellt werden kann:  
  
    -   Der Verweis auf `ContosoHR` ist sowohl im `InternalClient`\-Projekt als auch im `CareersWebSite`\-Projekt enthalten.  
  
3.  Überprüfen Sie Folgendes, falls die Projektmappe nicht ausgeführt werden kann:  
  
    1.  Alle Dienste werden ausgeführt.  
  
    2.  Die Dienstverweise werden aktualisiert.  
  
        1.  Öffnen Sie den Ordner App\_WebReferences.  
  
        2.  Klicken Sie mit der rechten Maustaste auf **Contoso**, und wählen Sie **Web\-\/Dienstverweise aktualisieren** aus.  
  
        3.  Erstellen Sie die Projektmappe neu, indem Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] STRG\+UMSCHALT\+B drücken.  
  
## Deinstallieren  
  
1.  Löschen Sie den SQL Server\-Instanzspeicher, indem Sie die Datei Cleanup.bat im Ordner DbSetup ausführen.  
  
2.  Entfernen Sie den Quellcode von Ihrer Festplatte.  
  
## Siehe auch