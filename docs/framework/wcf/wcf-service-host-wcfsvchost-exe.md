---
title: "WCF-Diensthost (WcfSvcHost.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# WCF-Diensthost (WcfSvcHost.exe)
Mit dem [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Diensthost \(WcfSvcHost.exe\) können Sie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\-Debugger \(F5\) starten, um automatisch einen implementierten Dienst zu hosten und zu testen.Anschließend können Sie den Dienst mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient \(WcfTestClient.exe\) oder Ihrem eigenen Client testen, um potenzielle Fehler zu identifizieren und zu beheben.  
  
## WCF\-Diensthost  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost listet die Dienste in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstprojekt auf, lädt die Projektkonfiguration und instanziiert einen Host für jeden gefundenen Dienst.Das Tool wird über die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstvorlage in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] integriert und beim Debuggen des Projekts aufgerufen.  
  
 Wenn Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost verwenden, können Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst \(in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheksprojekt\) hosten, ohne zusätzlichen Code schreiben oder einen bestimmten Host bei der Entwicklung bereitstellen zu müssen.  
  
> [!NOTE]
>  Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost unterstützt teilweise Vertrauenswürdigkeit nicht.Wenn Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst in einer teilweise vertrauenswürdigen Umgebung verwenden möchten, dürfen Sie zur Erstellung des Diensts nicht die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheksprojektvorlage in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden.Erstellen Sie stattdessen in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eine neue Website, indem Sie die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstwebsitevorlage auswählen, die den Dienst auf einem Webserver hosten kann, für den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] teilweise Vertrauenswürdigkeit unterstützt.  
  
## Vom WCF\-Diensthost gehostete Projekttypen  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost kann als Host für die folgenden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheksprojekttypen fungieren: [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliothek, sequenzielle Workflowdienstbibliothek, Zustandsautomat\-Workflowdienstbibliothek und Syndication\-Dienstbibliothek.Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost kann auch als Host für solche Dienste fungieren, die einem Dienstbibliotheksprojekt mit der Funktion **Element hinzufügen** hinzugefügt werden können.Dazu gehören [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst, WF\-Zustandsautomatdienst, sequenzieller WF\-Dienst, XAML\-WF\-Zustandsautomatdienst und sequenzieller XAML\-WF\-Dienst.  
  
 Beachten Sie jedoch, dass Sie mit dem Tool den Host nicht konfigurieren können.Zur Konfiguration müssen Sie die Datei App.config manuell bearbeiten.Mit dem Tool können Sie auch nicht benutzerdefinierte Konfigurationsdateien validieren.  
  
> [!CAUTION]
>  Verwenden Sie zum Hosten von Diensten in einer Produktionsumgebung nicht den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost, da dieser nicht für diesen Zweck konzipiert wurde.Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost unterstützt nicht die Anforderungen hinsichtlich Zuverlässigkeit, Sicherheit und Verwaltung für eine solche Umgebung.Verwenden Sie stattdessen den IIS, da er über optimale Zuverlässigkeit und Überwachungsfunktionen verfügt und die bevorzugte Lösung für Hostdienste ist.Nachdem die Entwicklung der Dienste abgeschlossen ist, sollten Sie die Dienste vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost zum IIS migrieren.  
  
## Szenarien für die Verwendung des WCF\-Diensthosts in Visual Studio  
 Die folgende Tabelle enthält alle Parameter des Dialogfelds **Befehlszeilenargumente**, das Sie aufrufen können, indem Sie mit der rechten Maustaste im **Projektmappen\-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf Ihr Projekt klicken und aus dem Kontextmenü **Eigenschaften** wählen. Öffnen Sie dann die Registerkarte **Debuggen**, und klicken Sie auf **Startprojekt**.Diese Parameter sind nützlich bei der Konfiguration des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthosts.  
  
|Parameter|Bedeutung|  
|---------------|---------------|  
|`/client`|Ein optionaler Parameter, der den Pfad zu einer EXE\-Datei bestimmt, die nach dem Hosten der Dienste ausgeführt werden soll.Nach dem Hosten wird der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient gestartet.|  
|`/clientArg`|Legt eine Zeichenfolge als Argument fest, das an die benutzerdefinierte Clientanwendung geleitet wird.|  
|`/?`|Zeigt die Hilfe an.|  
  
#### Verwenden des WCF\-Testclients  
 Nachdem Sie ein neues [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstprojekt erstellt und zum Starten des Debuggers auf F5 gedrückt haben, beginnt der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost mit dem Hosten aller Dienste in Ihrem Projekt.Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient öffnet automatisch eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte.Vom Hauptfenster aus können Sie die Parameter testen und den Dienst aufrufen.  
  
 Um sicherzustellen, dass der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient verwendet wird, klicken Sie mit der rechten Maustaste im **Projektmappen\-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf das Projekt, und wählen Sie aus dem Kontextmenü **Eigenschaften**, und klicken Sie dann auf die Registerkarte **Debuggen**.Klicken Sie auf **Startprojekt**, und stellen Sie sicher, dass im Dialogfeld **Befehlszeilenargumente** Folgendes angezeigt wird.  
  
 `/client:WcfTestClient.exe`  
  
#### Verwenden eines benutzerdefinierten Clients  
 Um einen benutzerdefinierten Client zu verwenden, klicken Sie im **Projektmappen\-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf das Projekt, wählen Sie aus dem Kontextmenü **Eigenschaften**, und klicken Sie dann auf die Registerkarte **Debuggen**.Klicken Sie auf **Startprojekt**, und bearbeiten Sie die `/client`\-Parameter im Dialogfeld **Befehlszeilenargumente**, um auf den benutzerdefinierten Client zu zeigen, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe"`  
  
 Wenn Sie die Taste F5 drücken, um den Dienst erneut zu starten, startet der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost automatisch den benutzerdefinierten Client, wenn Sie den Debugger aufrufen.  
  
 Mit dem `/clientArg:`\-Parameter können Sie auch eine Zeichenfolge als Argument festlegen, das an die benutzerdefinierte Clientanwendung geleitet wird, wie im folgenden Beispiel gezeigt.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 So können Sie beispielsweise bei Verwendung der Vorlage für die Syndication\-Dienstbibliothek die folgenden Befehlszeilenargumente verwenden:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### Keine Angabe des Clients  
 Um anzugeben, dass kein Client nach dem Hosten des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensts verwendet wird, klicken Sie mit der rechten Maustaste im **Projektmappen\-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf das Projekt, und wählen Sie aus dem Kontextmenü **Eigenschaften**, und klicken Sie dann auf die Registerkarte **Debuggen**.Klicken Sie auf **Startprojekt**, und lassen Sie das Dialogfeld **Befehlszeilenargumente** leer.  
  
#### Verwenden eines benutzerdefinierten Hosts  
 Um einen benutzerdefinierten Host zu verwenden, klicken Sie im **Projektmappen\-Explorer** in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf das Projekt, wählen Sie aus dem Kontextmenü **Eigenschaften**, und klicken Sie dann auf die Registerkarte **Debuggen**.Klicken Sie auf **Externes Programm starten**, und geben Sie den vollständigen Pfad zum benutzerdefinierten Host ein.Über das Dialogfeld **Befehlszeilenargumente** können Sie Argumente angeben, die an den Host geleitet werden.  
  
## WCF\-Diensthost\-Benutzeroberfläche  
 Wenn Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost das erste Mal aufrufen \(durch Drücken der Taste F5 in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\), wird das Fenster **WCF\-Diensthost** automatisch geöffnet.Wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost ausgeführt wird, wird im Benachrichtigungsbereich das Anwendungssymbol angezeigt.Doppelklicken Sie auf das Symbol, um das Fenster **WCF\-Diensthost** zu öffnen.  
  
 Wenn beim Hosten des Dienstes Fehler auftreten, wird das Dialogfeld [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost mit den entsprechenden Informationen geöffnet.  
  
 Das Hauptfenster **WCF\-Diensthost** umfasst zwei Menüs:  
  
-   **Datei**: Enthält die Befehle **Schließen** und **Beenden**.Wenn Sie auf **Schließen** klicken, wird das Dialogfeld **WCF\-Diensthost** geschlossen, aber der Dienst wird weiterhin gehostet.Wenn Sie auf **Beenden** klicken, wird auch der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost geschlossen.Dadurch werden auch alle gehosteten Dienste gestoppt.  
  
-   **Hilfe**: Enthält den Befehl **Info**, mit dem Versionsinformationen aufgerufen werden.Es enthält auch den Befehl **Hilfe**, über den Sie eine Hilfedatei öffnen können.  
  
 Das Hauptfenster **WCF\-Diensthost** umfasst zwei Bereiche:  
  
-   Der erste Bereich ist der Bereich **Dienst**.Er enthält eine Liste mit grundlegenden Informationen zu allen Diensten.Zu diesen Informationen zählen:  
  
    -   **Dienst**: Listet alle Dienste auf.  
  
    -   **Status**: Listet den Status des Dienstes auf.Gültige Werte sind: “Gestartet”, “Beendet” und “Fehler”.  
  
    -   **Metadatenadresse**: Zeigt die Metadatenadresse des Dienstes an.  
  
-   Der zweite Bereich ist der Bereich **Zusätzliche Informationen**.Er enthält eine detaillierte Beschreibung zum Status des Dienstes, wenn die entsprechende Dienstzeile im Bereich **Dienst** ausgewählt ist.Wenn der Status auf Fehler gesetzt ist, können Sie am Bildschirm die vollständige Fehlermeldung anzeigen.  
  
## Beenden des WCF\-Diensthostes  
 Sie können den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost auf einem der folgenden vier Wege beenden:  
  
-   Beenden Sie die Debuggen\-Sitzung in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
-   Wählen Sie im Fenster **WCF\-Diensthost** aus dem Menü **Datei** den Befehl **Beenden**.  
  
-   Wählen Sie den Befehl **Beenden** aus dem Kontextmenü des Taskleistensymbols im Systembenachrichtigungsbereich des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthosts.  
  
-   Beenden Sie ggf. den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient.  
  
## Verwenden des Diensthosts ohne Administratorberechtigung  
 Damit auch Benutzer ohne Administratorberechtigung [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienste entwickeln können, wird während der Installation von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eine ACL \(Access Control List\) für den Namespace "http:\/\/\+:8731\/Design\_Time\_Addresses" erstellt.Die ACL wird auf \(UI\) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden.Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL haben Benutzer die Möglichkeit, den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst\-Auto\-Host \("wcfSvcHost.exe"\) zu verwenden, ohne dass ihnen Administratorberechtigungen zugewiesen werden müssen.  
  
 Mit dem Tool netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern.Das folgende Beispiel veranschaulicht die Verwendung des Tools netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zum Tool netsh.exe finden Sie unter [Verwenden des Tools "Netsh.exe" und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877) \(möglicherweise in englischer Sprache\).  
  
## Siehe auch  
 [WCF\-Testclient \(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)