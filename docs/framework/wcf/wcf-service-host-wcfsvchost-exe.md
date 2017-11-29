---
title: WCF-Diensthost (WcfSvcHost.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 709e73b0fe665d836dfa50a630de35d955e110eb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-service-host-wcfsvchostexe"></a>WCF-Diensthost (WcfSvcHost.exe)
Mit dem [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Diensthost (WcfSvcHost.exe) können Sie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Debugger (F5) starten, um automatisch einen implementierten Dienst zu hosten und zu testen. Anschließend können Sie den Dienst mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu identifizieren und zu beheben.  
  
## <a name="wcf-service-host"></a>WCF-Diensthost  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost listet die Dienste in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstprojekt auf, lädt die Projektkonfiguration und instanziiert einen Host für jeden gefundenen Dienst. Das Tool wird über die [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Dienstvorlage in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] integriert und beim Debuggen des Projekts aufgerufen.  
  
 Wenn Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost verwenden, können Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst (in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksprojekt) hosten, ohne zusätzlichen Code schreiben oder einen bestimmten Host bei der Entwicklung bereitstellen zu müssen.  
  
> [!NOTE]
>  Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost unterstützt teilweise Vertrauenswürdigkeit nicht. Wenn Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst in einer teilweise vertrauenswürdigen Umgebung verwenden möchten, dürfen Sie zur Erstellung des Diensts nicht die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksprojektvorlage in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden. Erstellen Sie stattdessen in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eine neue Website, indem Sie die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstwebsitevorlage auswählen, die den Dienst auf einem Webserver hosten kann, für den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] teilweise Vertrauenswürdigkeit unterstützt.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Vom WCF-Diensthost gehostete Projekttypen  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost kann als Host für die folgenden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksprojekttypen fungieren: [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek, sequenzielle Workflowdienstbibliothek, Zustandsautomat-Workflowdienstbibliothek und Syndication-Dienstbibliothek. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]Diensthost können auch die Dienste, die einem Dienstbibliotheksprojekt mit hinzugefügt werden können hosten die **Element hinzufügen** Funktionalität. Dazu gehören [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst, WF-Zustandsautomatdienst, sequenzieller WF-Dienst, XAML-WF-Zustandsautomatdienst und sequenzieller XAML-WF-Dienst.  
  
 Beachten Sie jedoch, dass Sie mit dem Tool den Host nicht konfigurieren können. Zur Konfiguration müssen Sie die Datei App.config manuell bearbeiten. Mit dem Tool können Sie auch nicht benutzerdefinierte Konfigurationsdateien validieren.  
  
> [!CAUTION]
>  Verwenden Sie zum Hosten von Diensten in einer Produktionsumgebung nicht den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost, da dieser nicht für diesen Zweck konzipiert wurde.  Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost unterstützt nicht die Anforderungen hinsichtlich Zuverlässigkeit, Sicherheit und Verwaltung für eine solche Umgebung. Verwenden Sie stattdessen den IIS, da er über optimale Zuverlässigkeit und Überwachungsfunktionen verfügt und die bevorzugte Lösung für Hostdienste ist. Nachdem die Entwicklung der Dienste abgeschlossen ist, sollten Sie die Dienste vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost zum IIS migrieren.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Szenarien für die Verwendung des WCF-Diensthosts in Visual Studio  
 Die folgende Tabelle enthält alle Parameter in der **Befehlszeilenargumente** (Dialogfeld), das sich von der rechten Maustaste auf das Projekt in **Projektmappen-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], auswählen **Eigenschaften**, wählen Sie dann die **Debuggen** Registerkarte und dann auf **Startprojekt**. Diese Parameter sind nützlich bei der Konfiguration des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthosts.  
  
|Parameter|Bedeutung|  
|---------------|-------------|  
|`/client`|Ein optionaler Parameter, der den Pfad zu einer EXE-Datei bestimmt, die nach dem Hosten der Dienste ausgeführt werden soll. Nach dem Hosten wird der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient gestartet.|  
|`/clientArg`|Legt eine Zeichenfolge als Argument fest, das an die benutzerdefinierte Clientanwendung geleitet wird.|  
|`/?`|Zeigt die Hilfe an.|  
  
#### <a name="using-wcf-test-client"></a>Verwenden des WCF-Testclients  
 Nachdem Sie ein neues [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstprojekt erstellt und zum Starten des Debuggers auf F5 gedrückt haben, beginnt der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost mit dem Hosten aller Dienste in Ihrem Projekt. Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient öffnet automatisch eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte. Vom Hauptfenster aus können Sie die Parameter testen und den Dienst aufrufen.  
  
 Um sicherzustellen, dass [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Testclient dient der rechten Maustaste auf das Projekt in **Projektmappen-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]Option **Eigenschaften**, und wählen Sie dann die **Debuggen**Registerkarte. Klicken Sie auf **Startprojekt** und stellen Sie sicher, dass der Folgendes angezeigt wird der **Befehlszeilenargumente** (Dialogfeld).  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Verwenden eines benutzerdefinierten Clients  
 Um eine benutzerdefinierte Clienteinstellung verwenden zu können, Maustaste das Projekt in **Projektmappen-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]Option **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und Bearbeiten der `/client` Parameter in der **Befehlszeilenargumente** im Dialogfeld auf den benutzerdefinierten Client zu zeigen, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe"`  
  
 Wenn Sie die Taste F5 drücken, um den Dienst erneut zu starten, startet der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost automatisch den benutzerdefinierten Client, wenn Sie den Debugger aufrufen.  
  
 Mit dem `/clientArg:`-Parameter können Sie auch eine Zeichenfolge als Argument festlegen, das an die benutzerdefinierte Clientanwendung geleitet wird, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 So können Sie beispielsweise bei Verwendung der Vorlage für die Syndication-Dienstbibliothek die folgenden Befehlszeilenargumente verwenden:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Keine Angabe des Clients  
 Um anzugeben, dass kein Client nach verwendet werden soll [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service hosting der rechten Maustaste auf das Projekt in **Projektmappen-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]Option **Eigenschaften**, wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **Startprojekt** und lassen Sie die **Befehlszeilenargumente** Dialogfeld leer.  
  
#### <a name="using-a-custom-host"></a>Verwenden eines benutzerdefinierten Hosts  
 Um einen benutzerdefinierten Host verwenden, Maustaste das Projekt in **Projektmappen-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]Option **Eigenschaften**, und wählen Sie dann die **Debuggen** Registerkarte. Klicken Sie auf **externes Startprogramm** und geben Sie den vollständigen Pfad zu den benutzerdefinierten Host. Sie können auch die **Befehlszeilenargumente** Dialogfeld Sie Argumente angeben, an den Host geleitet werden.  
  
## <a name="wcf-service-host-user-interface"></a>WCF-Diensthost-Benutzeroberfläche  
 Wenn Sie sich das erste Mal aufrufen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Diensthost (durch Drücken von F5 in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]), wird die **WCF-Diensthost** Fenster automatisch geöffnet wird. Wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost ausgeführt wird, wird im Benachrichtigungsbereich das Anwendungssymbol angezeigt. Doppelklicken Sie auf das Symbol zum Öffnen der **WCF-Diensthost** Fenster  
  
 Wenn beim Hosten des Dienstes Fehler auftreten, wird das Dialogfeld [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost mit den entsprechenden Informationen geöffnet.  
  
 Die **WCF-Diensthost** im Hauptfenster umfasst zwei Menüs:  
  
-   **Datei**: enthält die **schließen** und **beenden** Befehle. Beim Klicken auf **schließen**, **WCF-Diensthost** Dialogfeld wird geschlossen, aber der Dienst wird weiterhin gehostet werden. Beim Klicken auf **beenden**, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Diensthost wird heruntergefahren. Dadurch werden auch alle gehosteten Dienste gestoppt.  
  
-   **Hilfe**: enthält die **zu** -Befehl, der Versionsinformationen enthält. Es enthält auch die **Hilfe** -Befehl, der eine Hilfedatei öffnen kann.  
  
 Die Main **WCF-Diensthost** umfasst zwei Bereiche:  
  
-   Der erste Bereich ist **Service**. Er enthält eine Liste mit grundlegenden Informationen zu allen Diensten. Zu diesen Informationen zählen:  
  
    -   **Dienst**: Listet alle Dienste.  
  
    -   **Status**: Listet den Status des Diensts. Gültige Werte sind "Gestartet", "Stopped" und "Error".  
  
    -   **Metadatenadresse**: Zeigt die Adresse der Metadaten der Dienste.  
  
-   Der zweite Bereich ist **Zusatzinformationen**. Eine ausführliche Erläuterung der Status des Diensts angezeigt, wenn der bestimmte Dienst Zeile, in ausgewählt ist der **Service** Bereich. Wenn der Status auf Fehler gesetzt ist, können Sie am Bildschirm die vollständige Fehlermeldung anzeigen.  
  
## <a name="stopping-wcf-service-host"></a>Beenden des WCF-Diensthostes  
 Sie können den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost auf einem der folgenden vier Wege beenden:  
  
-   Beenden Sie die Debuggen-Sitzung in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
-   Wählen Sie **beenden** aus der **Datei** im Menü der **WCF-Diensthost** Fenster.  
  
-   Wählen Sie **beenden** im Kontextmenü des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Diensthost-Taskleistensymbols im systembenachrichtigungsbereich.  
  
-   Beenden Sie ggf. den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Verwenden des Diensthosts ohne Administratorberechtigung  
 Damit auch Benutzer ohne Administratorberechtigung [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste entwickeln können, wird während der Installation von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eine ACL (Access Control List) für den Namespace "http://+:8731/Design_Time_Addresses" erstellt. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL haben Benutzer die Möglichkeit, den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host ("wcfSvcHost.exe") zu verwenden, ohne dass ihnen Administratorberechtigungen zugewiesen werden müssen.  
  
 Mit dem Tool netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Tools netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu netsh.exe, finden Sie unter "[wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
