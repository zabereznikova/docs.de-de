---
title: WCF-Diensthost (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: 6f719756688af066a42c3f73a860038dad1e5a53
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43565307"
---
# <a name="wcf-service-host-wcfsvchostexe"></a>WCF-Diensthost (WcfSvcHost.exe)
Windows Communication Foundation (WCF)-Diensthost (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um automatisch zu hosten und Testen einen Dienst, den Sie implementiert haben. Anschließend können Sie den Dienst mithilfe von WCF-Testclient (WcfTestClient.exe) oder Ihre eigenen-Clients zum Suchen und beheben potenzielle Fehler testen.  
  
## <a name="wcf-service-host"></a>WCF-Diensthost  
 WCF-Diensthost listet die Dienste in einem WCF-Dienst-Projekt, lädt die Projektkonfiguration und instanziiert einen Host für die einzelnen Dienste, die es findet. Das Tool ist über die WCF-Dienstvorlage in Visual Studio integriert und wird aufgerufen, wenn Sie damit beginnen, das Debuggen des Projekts.  
  
 Verwenden Sie WCF-Diensthost, können Sie einen WCF-Dienst (in einem WCF-Dienstbibliotheksprojekt) hosten, ohne zusätzlichen Code schreiben oder einen bestimmten Host bei der Entwicklung.  
  
> [!NOTE]
>  WCF-Diensthost unterstützt teilweiser Vertrauenswürdigkeit nicht. Wenn Sie einen WCF-Dienst bei teilweiser Vertrauenswürdigkeit verwenden möchten, verwenden Sie nicht die WCF-Dienstbibliotheksprojekt-Vorlage in Visual Studio zur Erstellung des Diensts. Erstellen Sie stattdessen eine neue WebSite in Visual Studio durch Auswählen der Vorlage für WCF-Service-WebSite, die der Dienst auf einem WebServer hosten kann auf denen WCF teilweise Vertrauenswürdigkeit unterstützt wird.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Vom WCF-Diensthost gehostete Projekttypen  
 WCF-Diensthost kann die folgenden WCF-Dienst-Bibliothek Projekttypen hosten: WCF-Dienstbibliothek, sequenzielle Workflowdienstbibliothek, Status-Workflowdienstbibliothek und Syndication-Dienstbibliothek. WCF-Diensthost kann auch hosten, die Dienste, die einem Dienstbibliotheksprojekt mit hinzugefügt werden können die **Element hinzufügen** Funktionalität. Dies schließt die WCF-Dienst, WF-Zustandsautomatdienst, Sequenzieller WF-Dienst, XAML-WF-Zustandsautomatdienst und sequenzieller XAML-WF-Dienst.  
  
 Beachten Sie jedoch, dass Sie mit dem Tool den Host nicht konfigurieren können. Zur Konfiguration müssen Sie die Datei App.config manuell bearbeiten. Mit dem Tool können Sie auch nicht benutzerdefinierte Konfigurationsdateien validieren.  
  
> [!CAUTION]
>  Sie sollten nicht WCF-Diensthost zum Hosten von Diensten in einer produktionsumgebung verwenden, da es nicht für diesen Zweck konzipiert wurde.  WCF-Diensthost unterstützt nicht die Zuverlässigkeit, Sicherheit und verwaltbarkeit von Anforderungen für eine solche Umgebung. Verwenden Sie stattdessen den IIS, da er über optimale Zuverlässigkeit und Überwachungsfunktionen verfügt und die bevorzugte Lösung für Hostdienste ist. Nach der Entwicklung der Dienste abgeschlossen ist, sollten Sie die Dienste von WCF-Diensthosts in IIS migrieren.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Szenarien für die Verwendung des WCF-Diensthosts in Visual Studio  
 Die folgende Tabelle enthält alle Parameter in der **Befehlszeilenargumente** gefunden werden kann, mit der rechten Maustaste in das Projekt im Dialogfeld **Projektmappen-Explorer** in Visual Studio auswählen **Eigenschaften**, wählen Sie dann die **Debuggen** Registerkarte und auf **Startprojekt**. Diese Parameter sind nützlich bei der Konfiguration von WCF-Diensthost.  
  
|Parameter|Bedeutung|  
|---------------|-------------|  
|`/client`|Ein optionaler Parameter, der den Pfad zu einer EXE-Datei bestimmt, die nach dem Hosten der Dienste ausgeführt werden soll. Dadurch wird die WCF-Testclient nach dem hosten.|  
|`/clientArg`|Legt eine Zeichenfolge als Argument fest, das an die benutzerdefinierte Clientanwendung geleitet wird.|  
|`/?`|Zeigt die Hilfe an.|  
  
#### <a name="using-wcf-test-client"></a>Verwenden des WCF-Testclients  
 Nach dem Erstellen eines neuen WCF-Dienst-Projekts und drücken Sie F5, um den Debugger zu starten, startet WCF-Diensthost mit dem Hosten aller Dienste, die sie in Ihrem Projekt findet. WCF-Testclient öffnet automatisch und zeigt eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte. Vom Hauptfenster aus können Sie die Parameter testen und den Dienst aufrufen.  
  
 Um sicherzustellen, dass WCF-Testclient verwendet wird, klicken Sie in Ihrem Projekt aus, in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und stellen Sie sicher, dass der folgende, in angezeigt der **Befehlszeilenargumente** Dialogfeld.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Verwenden eines benutzerdefinierten Clients  
 Um eine benutzerdefinierte Clienteinstellung verwenden zu können, klicken Sie in Ihr Projekt aus, in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und Bearbeiten der `/client` Parameter in der **Befehlszeilenargumente** im Dialogfeld, um auf den benutzerdefinierten Client zu verweisen, wie im folgenden Beispiel angegeben.  
  
 `/client:"path/CustomClient.exe"`  
  
 Beim Drücken von F5, um den Dienst erneut starten, beginnt der WCF-Diensthost automatisch den benutzerdefinierten Client, wenn Sie den Debugger starten.  
  
 Mit dem `/clientArg:`-Parameter können Sie auch eine Zeichenfolge als Argument festlegen, das an die benutzerdefinierte Clientanwendung geleitet wird, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 So können Sie beispielsweise bei Verwendung der Vorlage für die Syndication-Dienstbibliothek die folgenden Befehlszeilenargumente verwenden:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Keine Angabe des Clients  
 Um anzugeben, dass kein Client nach dem WCF-Dienst gehostet wird, klicken Sie in Ihrem Projekt aus, in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und lassen Sie die **Befehlszeilenargumente** Dialogfeld ist leer.  
  
#### <a name="using-a-custom-host"></a>Verwenden eines benutzerdefinierten Hosts  
 Um einen benutzerdefinierten Host zu verwenden, klicken Sie in Ihrem Projekt aus, in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **externes Startprogramm** , und geben Sie den vollständigen Pfad zum benutzerdefinierten Host. Sie können auch die **Befehlszeilenargumente** -Dialogfelds Argumente an den Host übergeben werden soll.  
  
## <a name="wcf-service-host-user-interface"></a>WCF-Diensthost-Benutzeroberfläche  
 Wenn Sie anfänglich aufrufen, WCF-Diensthost (durch Drücken von F5 in Visual Studio), die **WCF-Diensthost** Fenster automatisch geöffnet wird. Wenn WCF-Diensthost ausgeführt wird, wird das Symbol des Programms im Infobereich der Taskleiste angezeigt. Doppelklicken Sie auf das Symbol zum Öffnen der **WCF-Diensthost** Fenster  
  
 Wenn Fehler auftreten, während der Dienst gehostet wird, wird WCF-Diensthost-Dialogfeld geöffnet, um relevante Informationen anzuzeigen.  
  
 Die **WCF-Diensthost** Hauptfenster umfasst zwei Menüs:  
  
-   **Datei**: enthält die **schließen** und **beenden** Befehle. Beim Klicken auf **schließen**, **WCF-Diensthost** Dialogfeld wird geschlossen, aber der Dienst wird weiterhin gehostet werden. Beim Klicken auf **beenden**, WCF-Diensthost wird heruntergefahren. Dadurch werden auch alle gehosteten Dienste gestoppt.  
  
-   **Hilfe**: enthält die **zu** -Befehl, der Versionsinformationen enthält. Es enthält auch die **Hilfe** -Befehl, der eine Hilfedatei öffnen kann.  
  
 Die Main **WCF-Diensthost** umfasst zwei Bereiche:  
  
-   Der erste Bereich ist **Service**. Er enthält eine Liste mit grundlegenden Informationen zu allen Diensten. Zu diesen Informationen zählen:  
  
    -   **Dienst**: Listet alle Dienste.  
  
    -   **Status**: Listet den Status des Diensts. Gültige Werte sind "Gestartet", "Beendet" und "Error".  
  
    -   **Metadatenadresse**: Zeigt die Adresse der Metadaten der Dienste.  
  
-   Der zweite Bereich ist **Zusatzinformationen**. Eine ausführliche Erläuterung der Status angezeigt, wenn die entsprechende dienstzeile im ausgewählt ist die **Service** Bereich. Wenn der Status auf Fehler gesetzt ist, können Sie am Bildschirm die vollständige Fehlermeldung anzeigen.  
  
## <a name="stopping-wcf-service-host"></a>Beenden des WCF-Diensthostes  
 Sie können WCF-Diensthost in der folgenden vier Wege Herunterfahren:  
  
-   Beenden Sie die Debugsitzung in Visual Studio.  
  
-   Wählen Sie **beenden** aus der **Datei** im Menü der **WCF-Diensthost** Fenster.  
  
-   Wählen Sie **beenden** im Kontextmenü des WCF-Diensthost-Taskleistensymbols im systembenachrichtigungsbereich.  
  
-   WCF-Testclient zu beenden, wenn sie verwendet wird.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Verwenden des Diensthosts ohne Administratorberechtigung  
 Um Benutzer ohne Administratorrechte zum Entwickeln von WCF-Dienste zu aktivieren, wird eine ACL (Access Control List) erstellt, für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können hinzufügen oder Benutzer aus dieser ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können Benutzer die WCF-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne ihnen Administratorrechte zu gewähren.  
  
 Mit dem Tool netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Tools netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zum netsh.exe, finden Sie unter "[wie mit dem Netsh.exe-Tool und die Befehlszeilenoptionen](https://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
