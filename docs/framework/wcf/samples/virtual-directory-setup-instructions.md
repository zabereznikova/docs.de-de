---
title: Anleitung zum Einrichten eines virtuellen Verzeichnisses
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: dba6547888935ccf36ec0924fd3c95e8fbda5688
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243650"
---
# <a name="virtual-directory-setup-instructions"></a>Anleitung zum Einrichten eines virtuellen Verzeichnisses

Die Windows Communication Foundation (WCF)-Beispiele sind dafür vorgesehen, ein gemeinsames virtuelles Verzeichnis namens "Service Model Samples" freizugeben, das dem Ordner "%SystemDrive%\inetpub\wwwroot\servicemodelsamples" zugeordnet ist.  
  
> [!NOTE]
> % SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste (IIS) installiert ist.  
  
 Sie können die Setupvroot.bat-und Cleanupvroot.bat Dateien aus dem [einmaligen Setup Windows Communication Foundation Verfahren](one-time-setup-procedure-for-the-wcf-samples.md) ausführen, um das virtuelle Verzeichnis zu erstellen. Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.  
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>So erstellen Sie ein virtuelles Verzeichnis in IIS 7,0 oder 7,5  
  
1. Klicken Sie im **Startmenü** auf **Ausführen**, und geben Sie **inetmgr** ein, um das MMC-Snap-in Internetinformationsdienste (IIS) zu öffnen.  
  
2. Erweitern Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann den Knoten **Standorte** .  
  
3. Klicken Sie mit der rechten Maustaste auf **Standard Website**, und wählen Sie **Anwendung hinzufügen** aus, um das **Fenster Anwendung hinzufügen** zu öffnen.  
  
4. Geben Sie im Fenster `servicemodelsamples` als Alias für das virtuelle Verzeichnis ein, das Sie erstellen.  
  
5. Erstellen Sie das folgende Verzeichnis: %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
6. Legen Sie den physischen Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.  Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
7. Klicken Sie auf **OK**. Die Webanwendung wird für die WCF-Beispiele erstellt.  
  
    > [!NOTE]
    > Diese Aufgabe muss nur einmal ausgeführt werden, da für alle WCF-Beispiele dieselbe Webanwendung Service Model Samples verwendet wird.  
  
    > [!NOTE]
    > In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.  
  
     Zusätzlich zum Erstellen des virtuellen Verzeichnisses müssen Sie auch seine Eigenschaften festlegen, um das Ausführen von WCF-Diensten zu ermöglichen. Weitere Informationen siehe unten.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0  
  
1. Öffnen Sie ein Eingabe Aufforderungs Fenster `start inetmgr` , und geben Sie ein, um das MMC-Snap-in Internetinformationsdienste (IIS) zu öffnen.  
  
2. Erweitern Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann den Knoten **Websites** .  
  
3. Klicken Sie mit der rechten Maustaste auf **Standard Website** , und wählen Sie **neu, virtuelles Verzeichnis** , um den Assistenten zum Erstellen virtueller Verzeichnisse zu öffnen.  
  
4. Geben Sie im Assistenten `servicemodelsamples` als Alias für das virtuelle Verzeichnis ein, das Sie erstellen.  
  
5. Legen Sie den Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest. Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
6. Klicken Sie auf **Weiter**.  
  
7. Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    - **Lesen**  
  
    - **Skripts ausführen (z. B. ASP)**  
  
8. Klicken Sie auf **weiter**, und klicken Sie dann auf **Fertig** stellen, um den Assistenten abzuschließen.  
  
    > [!NOTE]
    > Diese Aufgabe muss nur einmal ausgeführt werden, da für alle WCF-Beispiele dasselbe virtuelle Verzeichnis Service Model Samples verwendet wird.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>So legen Sie zusätzliche Eigenschaften für virtuelle Verzeichnisse in IIS 7,0 oder 7,5 fest  
  
1. Klicken Sie auf den Knoten servicemodelsamples. Unten im Fenster sind zwei Ansichten aufgelistet. Wählen Sie **Featureansicht** aus, wenn Sie nicht bereits ausgewählt ist.  
  
2. Doppelklicken Sie auf den Eintrag für **Verzeichnis durchsuchen**.  
  
3. Wählen Sie im Bereich Aktionen die Option **aktivieren** aus. So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
 Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können. Weitere Informationen siehe unten.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest  
  
1. Klicken Sie mit der rechten Maustaste auf den Knoten Service Model Samples, und klicken Sie auf **Eigenschaften**.  
  
2. Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    - **Lesen**  
  
    - **Protokoll Besuche**  
  
    - **Diese Ressource indizieren**  
  
3. Aktivieren Sie das Kontrollkästchen **Verzeichnis durchsuchen** . So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>So legen Sie die Sicherheitseigenschaften des Ordners in IIS 7,0 oder 7,5 fest  
  
1. Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Klicken Sie mit der rechten Maustaste auf den Ordner Service Model Samples, und klicken Sie auf **Freigeben** oder **Freigeben mit**.  
  
3. Klicken Sie auf den Pfeil nach unten auf der linken Seite der Schaltfläche **Hinzufügen** .  
  
4. Wählen Sie den Eintrag **Suchen** aus. Das Fenster **Benutzer oder Gruppen auswählen** wird geöffnet.  
  
5. Klicken Sie auf **Erweitert**.  
  
6. Klicken Sie auf **Standorte**. Das Fenster Speicher **Orte** ist nun geöffnet.  
  
7. Wählen Sie den Eintrag für den verwendeten Computer aus. Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen. Nachdem Sie den Computer ausgewählt haben, klicken Sie auf **OK**.  
  
8. Klicken Sie auf **Jetzt suchen**. Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.  
  
9. Suchen Sie den **IIS_IUSRS** Eintrag in der Spalte **Name (Relative Distinguished Name)** . Wählen Sie diesen Eintrag aus, und klicken Sie auf **OK** , um das Fenster Suchergebnisse zu schließen  
  
10. Klicken Sie auf **OK** , um das Fenster **Benutzer oder Gruppen auswählen** zu schließen.  
  
11. Klicken Sie auf **Freigeben** , um die Änderungen beizubehalten.  
  
12. Nachdem die Änderungen zum Aktivieren der Freigabe abgeschlossen sind, klicken Sie auf **Fertig** , um das Fenster **Dateifreigabe** zu schließen.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein  
  
1. Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Klicken Sie mit der rechten Maustaste auf den Ordner **Service Model Samples** , und klicken Sie dann auf **Freigabe und Sicherheit.**  
  
3. Klicken Sie auf die Registerkarte **Sicherheit** .  
  
4. Wenn Sie IIS 6,0 verwenden, überprüfen Sie im Feld **Gruppen-oder Benutzernamen** , ob das **Internet Gastkonto** aufgeführt ist.  
  
     Falls nicht, gehen Sie wie folgt vor:  
  
    1. Klicken Sie auf **Start** und anschließend auf **Systemsteuerung**.  
  
    2. Wenn das Symbol " **Benutzerkonten** " nicht angezeigt wird, klicken Sie auf **zur Kategorieansicht wechseln**.  
  
    3. Klicken Sie auf das Symbol **Benutzerkonten** .  
  
    4. Klicken Sie unter "oder wählen Sie ein System Steuerungs Symbol" auf **Benutzerkonten**.  
  
    5. Klicken Sie im Dialogfeld **Benutzerkonten** auf die Registerkarte **erweitert** .  
  
    6. Klicken Sie auf **Erweitert**.  
  
    7. Klicken Sie im Dialogfeld **lokale Benutzer und Gruppen** auf den Ordner **Benutzer** , um ihn zu erweitern.  
  
    8. Doppelklicken Sie im rechten Bereich auf **Internet Gastkonto**.  
  
    9. Kopieren Sie im Dialogfeld **Eigenschaften** den Namen, der als Internet Gastkonto verwendet wird. Standardmäßig beginnt der Name mit "USR_", gefolgt von dem Namen des Computers.  
  
    10. Schließen Sie das Dialogfeld **Eigenschaften** .  
  
    11. Schließen Sie das Dialogfeld **lokale Benutzer und Gruppen** .  
  
    12. Schließen Sie das Dialogfeld **Benutzerkonten** .  
  
    13. Schließen Sie das Dialogfeld andere **Benutzerkonten** .  
  
    14. Klicken Sie im Dialogfeld **Eigenschaften von Service Model Samples** auf der Registerkarte **Sicherheit** auf **Hinzufügen**.  
  
    15. Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich ein, und fügen Sie dann den Namen des Internet Benutzerkontos ein, z. b. myMachineName \\ % InternetGuestAccountName%.  
  
    16. Klicken Sie auf " **Namen überprüfen** ", um die Addition Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.  
  
5. Überprüfen Sie für IIS 6,0 auch, ob Netzwerkdienst im Feld **Gruppen-oder Benutzernamen** aufgeführt ist.  
  
     Wenn NETZWERKDIENST nicht vorhanden ist:  
  
    1. Klicken Sie auf **Hinzufügen**.  
  
    2. Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** den Namen des Computers ein, gefolgt von einem umgekehrten Schrägstrich.  
  
    3. Geben Sie **Dienst** nach dem umgekehrten Schrägstrich (ohne Leerzeichen) ein.  
  
    4. Klicken Sie auf **Namen überprüfen**.  
  
    5. Wenn mehrere Namen gefunden werden, wählen Sie **Netzwerkdienst** aus, und klicken Sie auf **OK**.  
  
    6. Klicken Sie auf **OK** , um das Dialogfeld **Benutzer oder Gruppen auswählen** zu schließen.  
  
6. Wenn Sie Windows XP SP2 mit IIS 5,1 verwenden, überprüfen Sie, ob im Feld **Gruppen-oder Benutzernamen** sowohl das Internet Gastkonto als auch das ASPNET aufgeführt sind.  
  
     Beachten Sie, dass der ASPNET-Benutzer möglicherweise Mitglied der Sicherheitsgruppe "integrierte **Benutzer** " ist. Wenn dies der Fall ist, müssen Sie, wenn die Gruppe " **Benutzer** " im Dialogfeld aufgeführt ist, Sie nicht als separates Element zur Liste zulässiger Benutzer hinzufügen.  
  
     So überprüfen Sie, ob ASPNET Teil der Sicherheitsgruppe " **Benutzer** " ist:  
  
    1. Klicken Sie im Menü **Start** auf **Systemsteuerung**.  
  
    2. Klicken Sie auf das Symbol **Benutzerkonten** .  
  
    3. Überprüfen Sie in der Spalte **Gruppe** , ob der Wert für **ASPNET** "Users" lautet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Hostinganweisungen des Internetinformationsdiensts](internet-information-service-hosting-instructions.md)
