---
title: WCF-Diensthost (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: e1e258015adc34edd4a109f3bc5a32b4bf6f0296
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807033"
---
# <a name="wcf-service-host-wcfsvchostexe"></a>WCF-Diensthost (WcfSvcHost.exe)
Windows Communication Foundation (WCF)-Diensthost (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um automatisch hosten, und Testen Sie einen Dienst implementiert wurden. Sie können dann testen Sie den Dienst mithilfe von WCF-Testclient (WcfTestClient.exe) oder Ihrem eigenen Client zum Suchen und potenzielle Fehler zu beheben.  
  
## <a name="wcf-service-host"></a>WCF-Diensthost  
 WCF-Diensthost listet die Dienste in einem WCF-Dienstprojekt, lädt die Projektkonfiguration und instanziiert einen Host für jeden gefundenen Dienst. Das Tool ist über die WCF-Dienstvorlage in Visual Studio integriert und wird beim Starten des Debuggen des Projekts aufgerufen.  
  
 Mithilfe von WCF-Diensthost können Sie einen WCF-Dienst (in einem WCF-Dienst-Bibliotheksprojekt) hosten, ohne zusätzlichen Code schreiben oder an einen bestimmten Host bei der Entwicklung bereitstellen.  
  
> [!NOTE]
>  WCF-Diensthost unterstützt teilweiser Vertrauenswürdigkeit nicht. Wenn Sie einen WCF-Dienst in einer teilweise vertrauenswürdigen verwenden möchten, verwenden Sie nicht die WCF-Dienstbibliotheksprojekt-Vorlage in Visual Studio zur Erstellung des Diensts. Erstellen Sie stattdessen eine neue WebSite in Visual Studio durch Auswählen der Vorlage für WCF-Service-WebSite, die den Dienst auf einem WebServer hosten kann auf denen WCF teilweise Vertrauenswürdigkeit unterstützt wird.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Vom WCF-Diensthost gehostete Projekttypen  
 WCF-Diensthost kann die folgenden WCF-Dienst-Bibliothek Projekttypen hosten: WCF-Dienstbibliothek, sequenzielle Workflowdienstbibliothek, Zustand-Workflowdienstbibliothek und Syndication-Dienstbibliothek. WCF-Diensthost können auch die Dienste, die einem Dienstbibliotheksprojekt mit hinzugefügt werden können hosten die **Element hinzufügen** Funktionalität. Dies schließt die WCF-Dienst, WF-Zustandsautomatdienst, Sequenzieller WF-Dienst, XAML-WF-Zustandsautomatdienst und sequenzieller XAML-WF-Dienst.  
  
 Beachten Sie jedoch, dass Sie mit dem Tool den Host nicht konfigurieren können. Zur Konfiguration müssen Sie die Datei App.config manuell bearbeiten. Mit dem Tool können Sie auch nicht benutzerdefinierte Konfigurationsdateien validieren.  
  
> [!CAUTION]
>  Sie sollten nicht WCF-Diensthost zum Hosten von Diensten in einer produktionsumgebung verwenden, da es nicht zu diesem Zweck konzipiert wurde.  WCF-Diensthost unterstützt nicht die Zuverlässigkeit, Sicherheit und verwaltbarkeit Anforderungen von einer solchen Umgebung. Verwenden Sie stattdessen den IIS, da er über optimale Zuverlässigkeit und Überwachungsfunktionen verfügt und die bevorzugte Lösung für Hostdienste ist. Nach Abschluss der Entwicklung der Dienste sollten Sie die Dienste von WCF-Diensthosts in IIS migrieren.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Szenarien für die Verwendung des WCF-Diensthosts in Visual Studio  
 Die folgende Tabelle enthält alle Parameter in der **Befehlszeilenargumente** (Dialogfeld), das sich von der rechten Maustaste auf das Projekt in **Projektmappen-Explorer** in Visual Studio auswählen **Eigenschaften**, wählen Sie dann die **Debuggen** Registerkarte und dann auf **Startprojekt**. Diese Parameter sind nützlich bei der Konfiguration des WCF-Diensthost.  
  
|Parameter|Bedeutung|  
|---------------|-------------|  
|`/client`|Ein optionaler Parameter, der den Pfad zu einer EXE-Datei bestimmt, die nach dem Hosten der Dienste ausgeführt werden soll. Dadurch wird die WCF-Testclient nach dem hosten.|  
|`/clientArg`|Legt eine Zeichenfolge als Argument fest, das an die benutzerdefinierte Clientanwendung geleitet wird.|  
|`/?`|Zeigt die Hilfe an.|  
  
#### <a name="using-wcf-test-client"></a>Verwenden des WCF-Testclients  
 Nachdem Sie ein neues Projekt für die WCF-Dienst erstellen, und drücken Sie F5, um den Debugger zu starten, startet WCF-Diensthost mit dem Hosten aller Dienste, die sie in Ihrem Projekt findet. WCF-Testclient öffnet automatisch und zeigt eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte. Vom Hauptfenster aus können Sie die Parameter testen und den Dienst aufrufen.  
  
 Um sicherzustellen, dass WCF-Testclient verwendet wird, Maustaste das Projekt in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und stellen Sie sicher, dass der Folgendes angezeigt wird der **Befehlszeilenargumente** (Dialogfeld).  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Verwenden eines benutzerdefinierten Clients  
 Um eine benutzerdefinierte Clienteinstellung verwenden zu können, Maustaste das Projekt in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und Bearbeiten der `/client` Parameter in der **Befehlszeilenargumente** im Dialogfeld auf den benutzerdefinierten Client zu zeigen, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe"`  
  
 Beim Drücken von F5, um den Dienst erneut starten wird in WCF-Diensthost automatisch den benutzerdefinierten Client gestartet, wenn Sie den Debugger starten.  
  
 Mit dem `/clientArg:`-Parameter können Sie auch eine Zeichenfolge als Argument festlegen, das an die benutzerdefinierte Clientanwendung geleitet wird, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 So können Sie beispielsweise bei Verwendung der Vorlage für die Syndication-Dienstbibliothek die folgenden Befehlszeilenargumente verwenden:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Keine Angabe des Clients  
 Um anzugeben, dass kein Client nach dem Hosten von WCF-Dienst verwendet wird, Maustaste das Projekt in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und lassen Sie die **Befehlszeilenargumente** Dialogfeld leer.  
  
#### <a name="using-a-custom-host"></a>Verwenden eines benutzerdefinierten Hosts  
 Um einen benutzerdefinierten Host verwenden, Maustaste das Projekt in **Projektmappen-Explorer** wählen Sie in Visual Studio **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **externes Startprogramm** und geben Sie den vollständigen Pfad zu den benutzerdefinierten Host. Sie können auch die **Befehlszeilenargumente** Dialogfeld Sie Argumente angeben, an den Host geleitet werden.  
  
## <a name="wcf-service-host-user-interface"></a>WCF-Diensthost-Benutzeroberfläche  
 Wenn Sie anfänglich aufrufen WCF-Diensthost (durch Drücken von F5 in Visual Studio), die **WCF-Diensthost** Fenster automatisch geöffnet wird. Wenn WCF-Diensthost ausgeführt wird, wird das Programm-Symbol im Infobereich angezeigt. Doppelklicken Sie auf das Symbol zum Öffnen der **WCF-Diensthost** Fenster  
  
 Auftreten von Fehlern während der Dienst gehostet wird, wird der WCF-Diensthost-Dialogfeld geöffnet, um relevante Informationen anzuzeigen.  
  
 Die **WCF-Diensthost** im Hauptfenster umfasst zwei Menüs:  
  
-   **Datei**: enthält die **schließen** und **beenden** Befehle. Beim Klicken auf **schließen**, **WCF-Diensthost** Dialogfeld wird geschlossen, aber der Dienst wird weiterhin gehostet werden. Beim Klicken auf **beenden**, WCF-Diensthost wird heruntergefahren. Dadurch werden auch alle gehosteten Dienste gestoppt.  
  
-   **Hilfe**: enthält die **zu** -Befehl, der Versionsinformationen enthält. Es enthält auch die **Hilfe** -Befehl, der eine Hilfedatei öffnen kann.  
  
 Die Main **WCF-Diensthost** umfasst zwei Bereiche:  
  
-   Der erste Bereich ist **Service**. Er enthält eine Liste mit grundlegenden Informationen zu allen Diensten. Zu diesen Informationen zählen:  
  
    -   **Dienst**: Listet alle Dienste.  
  
    -   **Status**: Listet den Status des Diensts. Gültige Werte sind "Gestartet", "Stopped" und "Error".  
  
    -   **Metadatenadresse**: Zeigt die Adresse der Metadaten der Dienste.  
  
-   Der zweite Bereich ist **Zusatzinformationen**. Eine ausführliche Erläuterung der Status des Diensts angezeigt, wenn der bestimmte Dienst Zeile, in ausgewählt ist der **Service** Bereich. Wenn der Status auf Fehler gesetzt ist, können Sie am Bildschirm die vollständige Fehlermeldung anzeigen.  
  
## <a name="stopping-wcf-service-host"></a>Beenden des WCF-Diensthostes  
 Sie können WCF-Diensthost in der folgenden vier Wege Herunterfahren:  
  
-   Beenden Sie die Debugsitzung in Visual Studio.  
  
-   Wählen Sie **beenden** aus der **Datei** im Menü der **WCF-Diensthost** Fenster.  
  
-   Wählen Sie **beenden** im Kontextmenü des WCF-Diensthost-Taskleistensymbols im systembenachrichtigungsbereich.  
  
-   WCF-Testclient zu beenden, wenn sie verwendet wird.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Verwenden des Diensthosts ohne Administratorberechtigung  
 Damit kann Benutzer ohne Administratorberechtigung zur Entwicklung von WCF-Diensten, erstellt eine ACL (Access Control List) für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können hinzufügen oder Entfernen von Benutzern diese ACL oder zusätzliche Ports öffnen. Diese ACL kann Benutzer die WCF-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne ihnen Administratorrechte zu gewähren.  
  
 Mit dem Tool netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Tools netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu netsh.exe, finden Sie unter "[wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
