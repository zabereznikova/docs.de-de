---
title: "Anleitung zum Einrichten eines virtuellen Verzeichnisses | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Anleitung zum Einrichten eines virtuellen Verzeichnisses
Für die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Beispiele ist die Nutzung eines gemeinsamen virtuellen Verzeichnisses mit dem Namen servicemodelsamples vorgesehen, das dem Ordner %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples zugeordnet ist.  
  
> [!NOTE]
>  % SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste \(IIS\) installiert ist.  
  
 Zum Erstellen des virtuellen Verzeichnisses können Sie die Dateien Setupvroot.bat und Cleanupvroot.bat aus [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausführen.Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.  
  
## Prozeduren  
  
#### So erstellen Sie ein virtuelles Verzeichnis in IIS 7.0 oder 7.5  
  
1.  Klicken Sie im Menü **Start** auf **Ausführen**, und geben Sie **inetmgr** ein, um das MMC\-Snap\-In Internetinformationsdienste \(IIS\) zu öffnen.  
  
2.  Erweitern Sie im linken Bereich den Knoten mit dem Namen des Computers und dann den Knoten **Sites**.  
  
3.  Klicken Sie mit der rechten Maustaste auf **Standardwebsite**, und wählen Sie anschließend **Anwendung hinzufügen** aus, um das Fenster **Anwendung hinzufügen** zu öffnen.  
  
4.  Geben Sie in diesem Fenster `servicemodelsamples` als Alias für das virtuelle Verzeichnis ein, das Sie erstellen.  
  
5.  Erstellen Sie das folgende Verzeichnis: %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.  
  
6.  Legen Sie den physischen Pfad auf %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples fest.Die meisten der WCF\-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
7.  Klicken Sie auf **OK**.Die Webanwendung wird für die WCF\-Beispiele erstellt.  
  
    > [!NOTE]
    >  Sie müssen diesen Vorgang nur einmal ausführen, da für alle [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Beispiele dieselbe Webanwendung mit dem Namen servicemodelsamples verwendet wird.  
  
    > [!NOTE]
    >  In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.  
  
     Nachdem Sie das virtuelle Verzeichnis erstellt haben, müssen Sie die entsprechenden Eigenschaften einstellen, um das Ausführen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten zu ermöglichen.Details finden Sie weiter unten.  
  
#### So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie `start inetmgr` ein, um das MMC\-Snap\-In Internetinformationsdienste \(IIS\) zu öffnen.  
  
2.  Erweitern Sie im linken Bildschirmbereich den Knoten mit dem Namen des Computers und dann den Knoten **Websites**.  
  
3.  Klicken Sie mit der rechten Maustaste auf **Standardwebsite**, und wählen Sie **Neu \> Virtuelles Verzeichnis**, um den Assistenten zum Erstellen eines virtuellen Verzeichnisses zu öffnen.  
  
4.  Geben Sie im Assistenten `servicemodelsamples` als Alias für das virtuelle Verzeichnis ein, das Sie erstellen.  
  
5.  Legen Sie den Pfad auf %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples fest.Die meisten der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
6.  Klicken Sie auf **Weiter**.  
  
7.  Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    -   **Lesen**  
  
    -   **Skripts ausführen \(z. B. ASP\)**  
  
8.  Klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen**, um die Ausführung des Assistenten abzuschließen.  
  
    > [!NOTE]
    >  Sie müssen diesen Vorgang nur einmal ausführen, da für alle [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Beispiele dasselbe virtuelle Verzeichnis mit dem Namen servicemodelsamples verwendet wird.  
  
#### So stellen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 7.0 oder 7.5 ein  
  
1.  Klicken Sie auf den Knoten servicemodelsamples.Unten im Fenster sind zwei Ansichten aufgelistet.Wählen Sie die Ansicht **Features** aus, wenn diese nicht bereits ausgewählt ist.  
  
2.  Doppelklicken Sie auf den Eintrag für **Verzeichnis durchsuchen**.  
  
3.  Wählen Sie im Aktionsbereich die Option **Aktivieren** aus.So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
 Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können.Details finden Sie weiter unten.  
  
#### So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest  
  
1.  Klicken Sie mit der rechten Maustaste auf den Knoten servicemodelsamples, und klicken Sie anschließend auf **Eigenschaften**.  
  
2.  Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    -   **Lesen**  
  
    -   **Protokollieren von Besuchen**  
  
    -   **Indizieren dieser Ressource**  
  
3.  Aktivieren Sie das Kontrollkästchen **Verzeichnis durchsuchen**.So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
#### So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 7.0 oder 7.5 ein  
  
1.  Navigieren Sie zu %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.  
  
2.  Klicken Sie mit der rechten Maustaste auf den Ordner servicemodelsamples, und klicken Sie auf **Freigeben** oder auf **Freigeben für**.  
  
3.  Klicken Sie auf den Dropdownpfeil links neben der Schaltfläche **Hinzufügen**.  
  
4.  Wählen Sie die Option **Suchen**.Das Fenster **Benutzer oder Gruppen auswählen** wird geöffnet.  
  
5.  Klicken Sie auf **Erweitert**.  
  
6.  Klicken Sie auf **Speicherorte**.Das Fenster **Speicherorte** wird geöffnet.  
  
7.  Wählen Sie den Eintrag für den verwendeten Computer aus.Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen.Wenn Sie den Computer ausgewählt haben, klicken Sie auf **OK**.  
  
8.  Klicken Sie auf **Suche starten**.Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.  
  
9. Suchen Sie in der Spalte **Name \(RDN\)** den Eintrag **IIS\_IUSRS**.Wählen Sie diesen Eintrag aus, und klicken Sie auf **OK**, um das Fenster mit den Suchergebnissen zu schließen.  
  
10. Klicken Sie auf **OK**, um das Fenster **Benutzer oder Gruppen auswählen** zu schließen.  
  
11. Klicken Sie auf **Freigeben**, um die Änderungen zu übernehmen.  
  
12. Nachdem Sie alle Änderungen vorgenommen haben, klicken Sie auf **Fertig**, um das Fenster **Dateifreigabe** zu schließen.  
  
#### So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein  
  
1.  Navigieren Sie zu %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.  
  
2.  Klicken Sie mit der rechten Maustaste auf den Ordner **servicemodelsamples**, und klicken Sie dann auf **Freigabe und Sicherheit**.  
  
3.  Klicken Sie auf die Registerkarte **Sicherheit**.  
  
4.  Wenn Sie IIS 6.0 verwenden, überprüfen Sie, ob im Feld **Gruppen\- oder Benutzernamen** der Eintrag **Internetgastkonto** vorhanden ist.  
  
     Falls der Eintrag nicht vorhanden ist:  
  
    1.  Klicken Sie auf **Start** und anschließend auf **Systemsteuerung**.  
  
    2.  Wenn das Symbol **Benutzerkonten** nicht angezeigt wird, klicken Sie auf **Zur Kategorieansicht wechseln**.  
  
    3.  Klicken Sie auf das Symbol **Benutzerkonten**.  
  
    4.  Klicken Sie unter "oder ein Systemsteuerungssymbol" auf **Benutzerkonten**.  
  
    5.  Klicken Sie im Dialogfeld **Benutzerkonten** auf die Registerkarte **Erweitert**.  
  
    6.  Klicken Sie auf **Erweitert**.  
  
    7.  Klicken Sie im Dialogfeld **Lokale Benutzer und Gruppen** auf den Ordner **Benutzer**, um ihn zu erweitern.  
  
    8.  Doppelklicken Sie im rechten Bildschirmbereich auf **Internetgastkonto**.  
  
    9. Kopieren Sie im Dialogfeld **Eigenschaften** den Namen, der als Internetgastkonto verwendet wird.Standardmäßig beginnt der Name mit "USR\_", gefolgt von dem Namen des Computers.  
  
    10. Schließen Sie das Dialogfeld **Eigenschaften**.  
  
    11. Schließen Sie das Dialogfeld **Lokale Benutzer und Gruppen**.  
  
    12. Schließen Sie das Dialogfeld **Benutzerkonten**.  
  
    13. Schließen Sie das andere Dialogfeld **Benutzerkonten**.  
  
    14. Klicken Sie im Dialogfeld **Eigenschaften von servicemodelsamples** auf der Registerkarte **Sicherheit** auf die Schaltfläche **Hinzufügen**.  
  
    15. Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich ein, und fügen Sie dann den Namen des Internetbenutzerkontos ein, z. B. myMachineName\\%InternetGuestAccountName%  
  
    16. Klicken Sie auf **Namen überprüfen**, um den Namen zu überprüfen.Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.  
  
5.  Wenn Sie IIS 6.0 verwenden, müssen Sie außerdem überprüfen, ob im Feld **Gruppen\- oder Benutzernamen** der Eintrag NETZWERKDIENST vorhanden ist.  
  
     Wenn NETZWERKDIENST nicht vorhanden ist:  
  
    1.  Klicken Sie auf **Hinzufügen**.  
  
    2.  Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** den Namen des Computers gefolgt von einem umgekehrten Schrägstrich ein.  
  
    3.  Geben Sie nach dem Schrägstrich service ein \(ohne Leerzeichen\).  
  
    4.  Klicken Sie auf **Namen überprüfen**.  
  
    5.  Wenn mehrere Namen gefunden wurden, wählen Sie **NETZWERKDIENST** aus, und klicken Sie auf **OK**.  
  
    6.  Klicken Sie auf **OK**, um das Dialogfeld **Benutzer oder Gruppen auswählen** zu schließen.  
  
6.  Wenn Sie Windows XP SP2 mit IIS 5.1 verwenden, überprüfen Sie, ob im Feld **Gruppen\- oder Benutzernamen** die Einträge Internetgastkonto und ASPNET vorhanden sind.  
  
     Beachten Sie, dass der ASPNET\-Benutzer möglicherweise der integrierten Sicherheitsgruppe **Benutzer** zugewiesen ist.Wenn dies der Fall ist und die Gruppe **Benutzer** im Dialogfeld aufgelistet wird, müssen Sie diese nicht als separates Element der Liste der zugelassenen Benutzer hinzufügen.  
  
     So prüfen Sie, ob ASPNET Teil der Sicherheitsgruppe **Benutzer** ist:  
  
    1.  Klicken Sie im Menü **Start** auf **Systemsteuerung**.  
  
    2.  Klicken Sie auf das Symbol **Benutzerkonten**.  
  
    3.  Überprüfen Sie in der Spalte **Gruppe**, ob **ASPNET** der Wert "Benutzer" zugewiesen ist.  
  
## Siehe auch  
 [Hostinganweisungen des Internetinformationsdiensts](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)