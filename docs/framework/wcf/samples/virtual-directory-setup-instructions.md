---
title: Anleitung zum Einrichten eines virtuellen Verzeichnisses
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 3ff578b69590071ef2135e777b3105e7c226563e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806912"
---
# <a name="virtual-directory-setup-instructions"></a>Anleitung zum Einrichten eines virtuellen Verzeichnisses
Der Windows Communication Foundation (WCF)-Beispiele dienen zur eines gemeinsamen virtuellen Verzeichnisses mit dem Namen Servicemodelsamples, die das das dem Ordner %SystemDrive%\inetpub\wwwroot\servicemodelsamples zugeordnet ist.  
  
> [!NOTE]
>  % SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste (IIS) installiert ist.  
  
 Sie können die Dateien Setupvroot.bat und Cleanupvroot.bat aus ausführen, die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) beim Erstellen des virtuellen Verzeichnisses. Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>So erstellen Sie ein virtuelles Verzeichnis in IIS 7.0 oder 7.5  
  
1.  Aus der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.  
  
2.  Klicken Sie im linken Bereich, erweitern Sie den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Sites** Knoten.  
  
3.  Mit der rechten Maustaste **Default Web Site**, und wählen Sie dann **Anwendung hinzufügen** So öffnen die **hinzufügen Anwendungsfenster**.  
  
4.  Geben Sie im Fenster `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.  
  
5.  Erstellen Sie das folgende Verzeichnis: %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
6.  Legen Sie den physischen Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.  Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
7.  Klicken Sie auf **OK**. Die Webanwendung wird für die WCF-Beispiele erstellt.  
  
    > [!NOTE]
    >  Diese Aufgabe muss nur einmal ausgeführt werden, da alle WCF-Beispiele auf dem gleichen Namen Servicemodelsamples Webanwendung verwenden.  
  
    > [!NOTE]
    >  In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.  
  
     Zusätzlich zur Erstellung des virtuellen Verzeichnisses, müssen Sie auch die Eigenschaften zum Aktivieren der WCF-Dienste ausgeführt festlegen. Details finden Sie weiter unten.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster und geben `start inetmgr` auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.  
  
2.  Klicken Sie im linken Bereich, erweitern Sie den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Websites** Knoten.  
  
3.  Mit der rechten Maustaste **Default Web Site** , und wählen Sie **neue virtuelle Verzeichnis** zum Öffnen des Assistenten Erstellen eines virtuellen Verzeichnisses.  
  
4.  Geben Sie im Assistenten `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.  
  
5.  Legen Sie den Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest. Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.  
  
6.  Klicken Sie auf **Weiter**.  
  
7.  Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    -   **Lesen**  
  
    -   **Ausführen von Skripts (z. B. ASP)**  
  
8.  Klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen** um den Assistenten abzuschließen.  
  
    > [!NOTE]
    >  Diese Aufgabe muss nur einmal ausgeführt werden, da alle WCF-Beispiele verwenden Sie das virtuelle Verzeichnis des gleichen Servicemodelsamples.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Zum Festlegen von Eigenschaften der zusätzlich ein virtuelles Verzeichnis in IIS 7.0 oder 7.5  
  
1.  Klicken Sie auf den Knoten servicemodelsamples. Unten im Fenster sind zwei Ansichten aufgelistet. Wählen Sie **Ansicht "Features"** , wenn er nicht bereits ausgewählt ist.  
  
2.  Doppelklicken Sie auf den Eintrag für **Verzeichnissuche**.  
  
3.  Wählen Sie im Aktionsbereich die **aktivieren** Option. So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
 Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können. Details finden Sie weiter unten.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest  
  
1.  Mit der rechten Maustaste des Knotens Servicemodelsamples, und klicken Sie dann auf **Eigenschaften**.  
  
2.  Standardmäßig werden die folgenden Kontrollkästchen aktiviert:  
  
    -   **Lesen**  
  
    -   **Besuche protokollieren**  
  
    -   **Ressource indizieren**  
  
3.  Wählen Sie die **Verzeichnissuche** Kontrollkästchen. So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>So legen Sie die Sicherheitseigenschaften des Ordners in IIS 7.0 oder 7.5 fest  
  
1.  Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Mit der rechten Maustaste in des Ordners Servicemodelsamples, und klicken Sie auf **Freigabe** oder **freigeben für**.  
  
3.  Klicken Sie auf den Pfeil links neben der **hinzufügen** Schaltfläche.  
  
4.  Wählen Sie die **suchen** Eintrag. Die **Benutzer oder Gruppen auswählen** Fenster wird geöffnet.  
  
5.  Klicken Sie auf **erweiterte**.  
  
6.  Klicken Sie auf **Speicherorte**. Die **Speicherorte** Fenster ist jetzt geöffnet.  
  
7.  Wählen Sie den Eintrag für den verwendeten Computer aus. Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen. Nachdem Sie die Computer ausgewählt haben, klicken Sie auf **OK**.  
  
8.  Klicken Sie auf **Jetzt suchen**. Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.  
  
9. Suchen der **IIS_IUSRS** Eintrag in der **Namen (Relative Distinguished Name)** Spalte. Wählen Sie diesen Eintrag, und klicken Sie auf **OK** Ergebnisfenster schließen die Suche.  
  
10. Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** Fenster.  
  
11. Klicken Sie auf **Freigabe** damit die Änderungen beibehalten.  
  
12. Nachdem die Änderungen so aktivieren Sie die Freigabe abgeschlossen sind, klicken Sie auf **Fertig** schließen die **Dateifreigabe** Fenster.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein  
  
1.  Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Mit der rechten Maustaste die **Servicemodelsamples** Ordner, und klicken Sie dann auf **Freigabe und Sicherheit.**  
  
3.  Klicken Sie auf die Registerkarte **Sicherheit** .  
  
4.  Bei Verwendung von IIS 6.0, in der **Gruppen-oder Benutzernamen** Feld überprüfen, ob **Internetgastkonto** aufgeführt ist.  
  
     Falls der Eintrag nicht vorhanden ist:  
  
    1.  Klicken Sie auf **starten** , und klicken Sie dann auf **Systemsteuerung**.  
  
    2.  Wenn Sie nicht sehen die **Benutzerkonten** Symbol, klicken Sie auf **zur Kategorieansicht wechseln**.  
  
    3.  Klicken Sie auf die **Benutzerkonten** Symbol.  
  
    4.  Klicken Sie unter ", oder wählen Sie ein Symbol" Systemsteuerung "," klicken Sie auf **Benutzerkonten**.  
  
    5.  In der **Benutzerkonten** (Dialogfeld), klicken Sie auf die **erweitert** Registerkarte.  
  
    6.  Klicken Sie auf **erweiterte**.  
  
    7.  In der **lokale Benutzer und Gruppen** (Dialogfeld), klicken Sie zum Erweitern der **Benutzer** Ordner.  
  
    8.  Doppelklicken Sie im rechten Bereich auf **Internetgastkonto**.  
  
    9. In der **Eigenschaften** (Dialogfeld), die Kopie wird der Name als Internetgastkonto verwendet. Standardmäßig beginnt der Name mit "USR_", gefolgt von dem Namen des Computers.  
  
    10. Schließen der **Eigenschaften** (Dialogfeld).  
  
    11. Schließen der **lokale Benutzer und Gruppen** (Dialogfeld).  
  
    12. Schließen der **Benutzerkonten** (Dialogfeld).  
  
    13. Schließen Sie das andere **Benutzerkonten** (Dialogfeld).  
  
    14. In der **Eigenschaften von Servicemodelsamples** Dialogfeld auf die **Sicherheit** auf **hinzufügen**.  
  
    15. Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich ein, und fügen Sie den Namen des Internetbenutzerkontos, z. B. MyMachineName\\"% InternetGuestAccountName"  
  
    16. Klicken Sie auf **Namen überprüfen** um das Hinzufügen zu überprüfen. Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.  
  
5.  Für IIS 6.0 auch überprüfen Sie, ob Netzwerkdienst wird die **Gruppen-oder Benutzernamen** Feld.  
  
     Wenn NETZWERKDIENST nicht vorhanden ist:  
  
    1.  Klicken Sie auf **Hinzufügen**.  
  
    2.  In der **Benutzer oder Gruppen auswählen** Geben Sie im Dialogfeld der Namen des Computers einen umgekehrten Schrägstrich.  
  
    3.  Typ **Service** nach dem umgekehrten Schrägstrich (ohne Leerzeichen).  
  
    4.  Klicken Sie auf **Namen überprüfen**.  
  
    5.  Wenn mehrere Namen gefunden werden, wählen Sie **Netzwerkdienst** , und klicken Sie auf **OK**.  
  
    6.  Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** (Dialogfeld).  
  
6.  Wenn Sie Windows XP SP2 mit IIS 5.1 verwenden, überprüfen Sie, ob Internetgastkonto und ASPNET vorhanden sind die **Gruppen-oder Benutzernamen** Feld.  
  
     Beachten Sie, dass das ASPNET-Benutzer ein Mitglied der integrierten **Benutzer** Sicherheitsgruppe. Wenn dies der Fall ist, dann wird bei der **Benutzer** Gruppe im Dialogfeld aufgeführt ist, müssen Sie nicht als separates Element der Liste der zugelassenen Benutzer hinzufügen.  
  
     Zum Überprüfen, ob ASPNET Teil ist die **Benutzer** Sicherheitsgruppe:  
  
    1.  Auf der **starten** Menü klicken Sie auf **Systemsteuerung**.  
  
    2.  Klicken Sie auf die **Benutzerkonten** Symbol.  
  
    3.  In der **Gruppe** Spalte, überprüfen Sie, ob der Wert für **ASPNET** ist "Benutzer".  
  
## <a name="see-also"></a>Siehe auch  
 [Hostinganweisungen des Internetinformationsdiensts](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
