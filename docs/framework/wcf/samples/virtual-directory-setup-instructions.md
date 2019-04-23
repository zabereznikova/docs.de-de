---
title: Anleitung zum Einrichten eines virtuellen Verzeichnisses
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: fdff88026a49989870ee5c47f9a38a65ecad3c80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325344"
---
# <a name="virtual-directory-setup-instructions"></a>Anleitung zum Einrichten eines virtuellen Verzeichnisses
Die Windows Communication Foundation (WCF)-Beispiele dienen zum Freigeben von eines gemeinsamen virtuellen Verzeichnis mit dem Namen Servicemodelsamples, die das das dem Ordner %SystemDrive%\inetpub\wwwroot\servicemodelsamples zugeordnet ist.  
  
> [!NOTE]
>  % SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste (IIS) installiert ist.  
  
 Sie können die Dateien Setupvroot.bat und Cleanupvroot.bat aus ausführen, die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) zum Erstellen des virtuellen Verzeichnisses. Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>So erstellen ein virtuelles Verzeichnis in IIS 7.0 oder 7.5  
  
1. Von der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.  
  
2. Klicken Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Websites** Knoten.  
  
3. Mit der rechten Maustaste **Default Web Site**, und wählen Sie dann **Anwendung hinzufügen** zum Öffnen der **hinzufügen Anwendungsfenster**.  
  
4. Geben Sie im Fenster `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.  
  
5. Erstellen Sie das folgende Verzeichnis: %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
6. Legen Sie den physischen Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.  Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
7. Klicken Sie auf **OK**. Die Webanwendung wird für die WCF-Beispiele erstellt.  
  
    > [!NOTE]
    >  Diese Aufgabe muss nur einmal ausgeführt werden, da alle der WCF-Beispiele auf dem gleichen Namen Servicemodelsamples-Webanwendung verwenden.  
  
    > [!NOTE]
    >  In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.  
  
     Zusätzlich zum Erstellen des virtuellen Verzeichnisses, müssen Sie auch die Eigenschaften zum Aktivieren der WCF-Dienste zur Ausführung festlegen. Details finden Sie weiter unten.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0  
  
1. Öffnen Sie ein Eingabeaufforderungsfenster und geben `start inetmgr` auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.  
  
2. Klicken Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Websites** Knoten.  
  
3. Mit der rechten Maustaste **Default Web Site** , und wählen Sie **neu, virtuelles Verzeichnis** zum Öffnen des Assistenten Erstellen eines virtuellen Verzeichnisses.  
  
4. Geben Sie im Assistenten `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.  
  
5. Legen Sie den Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest. Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
6. Klicken Sie auf **Weiter**.  
  
7. Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    -   **Read**  
  
    -   **Ausführen von Skripts (z. B. ASP)**  
  
8. Klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen** um den Assistenten abzuschließen.  
  
    > [!NOTE]
    >  Diese Aufgabe muss nur einmal ausgeführt werden, da die WCF-Beispiele alle das gleiche virtuelle Verzeichnis Servicemodelsamples verwenden.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Um zusätzliche Eigenschaften virtueller Verzeichnisse in IIS 7.0 oder 7.5 festzulegen.  
  
1. Klicken Sie auf den Knoten servicemodelsamples. Unten im Fenster sind zwei Ansichten aufgelistet. Wählen Sie **Ansicht "Features"** , wenn sie nicht bereits ausgewählt ist.  
  
2. Doppelklicken Sie auf den Eintrag für **Verzeichnissuche**.  
  
3. Wählen Sie im Aktionsbereich die **aktivieren** Option. So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
 Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können. Details finden Sie weiter unten.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest  
  
1. Mit der rechten Maustaste des Knotens Servicemodelsamples, und klicken Sie dann auf **Eigenschaften**.  
  
2. Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    -   **Read**  
  
    -   **Besuche protokollieren**  
  
    -   **Ressource indizieren**  
  
3. Wählen Sie die **Verzeichnissuche** Kontrollkästchen. So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>So legen Sie die Sicherheitseigenschaften des Ordners in IIS 7.0 oder 7.5 fest  
  
1. Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Mit der rechten Maustaste in des Ordners Servicemodelsamples, und klicken Sie auf **Freigabe** oder **freigeben für**.  
  
3. Klicken Sie auf den Pfeil nach unten, links von der **hinzufügen** Schaltfläche.  
  
4. Wählen Sie die **finden** Eintrag. Die **Benutzer oder Gruppen auswählen** Fenster wird geöffnet.  
  
5. Klicken Sie auf **Erweitert**.  
  
6. Klicken Sie auf **Speicherorte**. Die **Speicherorte** Fenster wird geöffnet.  
  
7. Wählen Sie den Eintrag für den verwendeten Computer aus. Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen. Nachdem Sie die Computer ausgewählt haben, klicken Sie auf **OK**.  
  
8. Klicken Sie auf **Jetzt suchen**. Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.  
  
9. Suchen der **IIS_IUSRS** Eintrag in der **Namen (Relative Distinguished Name)** Spalte. Wählen Sie den Eintrag, und klicken Sie auf **OK** So schließen Sie die Suche die Ergebnisse im Fenster.  
  
10. Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** Fenster.  
  
11. Klicken Sie auf **Freigabe** , die Änderungen beizubehalten.  
  
12. Nachdem die Änderungen zum Aktivieren der Freigabe abgeschlossen sind, klicken Sie auf **Fertig** schließen die **Dateifreigabe** Fenster.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein  
  
1. Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Mit der rechten Maustaste die **Servicemodelsamples** Ordner, und klicken Sie dann auf **Freigabe und Sicherheit.**  
  
3. Klicken Sie auf die Registerkarte **Sicherheit** .  
  
4. Bei Verwendung von IIS 6.0 in der **Gruppen-oder Benutzernamen** Feld überprüfen, ob **Internetgastkonto** aufgeführt ist.  
  
     Falls der Eintrag nicht vorhanden ist:  
  
    1.  Klicken Sie auf **Start** und anschließend auf **Systemsteuerung**.  
  
    2.  Wenn Sie nicht sehen die **Benutzerkonten** Symbol, klicken Sie auf **zur Kategorieansicht wechseln**.  
  
    3.  Klicken Sie auf die **Benutzerkonten** Symbol.  
  
    4.  Klicken Sie unter ", oder wählen Sie ein Systemsteuerungssymbol" klicken Sie auf **Benutzerkonten**.  
  
    5.  In der **Benutzerkonten** Dialogfeld klicken Sie auf die **erweitert** Registerkarte.  
  
    6.  Klicken Sie auf **Erweitert**.  
  
    7.  In der **lokale Benutzer und Gruppen** (Dialogfeld), klicken Sie zum Erweitern der **Benutzer** Ordner.  
  
    8.  Doppelklicken Sie im rechten Bereich auf **Internetgastkonto**.  
  
    9. In der **Eigenschaften** Dialogfeld Kopieren der Namen ein, die mit dem Internet-Gastkonto. Standardmäßig beginnt der Name mit "USR_", gefolgt von dem Namen des Computers.  
  
    10. Schließen der **Eigenschaften** Dialogfeld.  
  
    11. Schließen der **lokale Benutzer und Gruppen** Dialogfeld.  
  
    12. Schließen der **Benutzerkonten** Dialogfeld.  
  
    13. Schließen Sie das andere **Benutzerkonten** Dialogfeld.  
  
    14. In der **Eigenschaften von Servicemodelsamples** Dialogfeld auf die **Sicherheit** auf **hinzufügen**.  
  
    15. Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich, und fügen Sie dann den Namen des Internetbenutzerkontos, z. B. MyMachineName\\InternetGuestAccountName %  
  
    16. Klicken Sie auf **Namen überprüfen** um den Namen zu überprüfen. Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.  
  
5. Für IIS 6.0 auch überprüfen, NETWORK SERVICE aufgeführt sein, die **Gruppen-oder Benutzernamen** Feld.  
  
     Wenn NETZWERKDIENST nicht vorhanden ist:  
  
    1.  Klicken Sie auf **Hinzufügen**.  
  
    2.  In der **Benutzer oder Gruppen auswählen** im Dialogfeld Typ den Namen des Computers gefolgt von einem umgekehrten Schrägstrich.  
  
    3.  Typ **Service** nach dem umgekehrten Schrägstrich (ohne Leerzeichen).  
  
    4.  Klicken Sie auf **Namen überprüfen**.  
  
    5.  Wenn mehrere Namen gefunden werden, wählen Sie **Netzwerkdienst** , und klicken Sie auf **OK**.  
  
    6.  Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** Dialogfeld.  
  
6. Wenn Sie Windows XP SP2 mit IIS 5.1 verwenden, überprüfen Sie, dass sowohl Internetgastkonto und ASPNET vorhanden sind die **Gruppen-oder Benutzernamen** Feld.  
  
     Beachten Sie, dass der ASPNET-Benutzer ein Mitglied der integrierten möglicherweise **Benutzer** Sicherheitsgruppe. Wenn dies der Fall ist, dann, wenn die **Benutzer** Gruppe, die im Dialogfeld aufgelistet ist, Sie müssen nicht als separates Element zur Liste der zugelassenen Benutzer hinzufügen.  
  
     Zum Überprüfen, ob ASPNET Teil ist die **Benutzer** Sicherheitsgruppe:  
  
    1.  Auf der **starten** Menü klicken Sie auf **Systemsteuerung**.  
  
    2.  Klicken Sie auf die **Benutzerkonten** Symbol.  
  
    3.  In der **Gruppe** Spalte überprüfen, ob der Wert für **ASPNET** ist "Benutzer".  
  
## <a name="see-also"></a>Siehe auch

- [Hostinganweisungen des Internetinformationsdiensts](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
