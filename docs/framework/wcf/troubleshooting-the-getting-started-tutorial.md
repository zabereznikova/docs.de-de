---
title: Beheben der Ersten Schritte mit Windows Communication Foundation-Tutorials
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 92e986370fe1b6e067d9f8aebc73179c1ac6a20f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183089"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Beheben der Ersten Schritte mit Windows Communication Foundation-Tutorials

Dieser Artikel enthält Lösungen für die häufigsten Probleme und Fehler, die auftreten können, wenn Sie die Schritte im [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md)ausführen.
  
## <a name="common-problems"></a>Häufiger auftretende Probleme

**Ich kann die Projektdateien auf meiner Festplatte nicht finden.**

 Visual Studio speichert Projektdateien in *C:'Users-Benutzername\\&lt;&gt;'source'repos*'  

**Ich kann die *app.config-Datei,* die von *Svcutil.exe*generiert wurde, nicht finden.**

 In Visual Studio zeigt das Fenster **Vorhandene Elemente hinzufügen** standardmäßig nur Dateien mit den folgenden Erweiterungen an:

- *.cs*
- *RESX-Datei*
- *.settings*
- *.xsd*
- *.wsdl*

Um alle Dateitypen anzuzeigen, wählen Sie in der Dropdown-Liste in der unteren rechten Ecke des Fensters Vorhandene Elemente **hinzufügen** **alle Dateien (\*.\*)** aus.  
  
## <a name="common-errors"></a>Häufige Fehler

### <a name="compile-the-service-application"></a>Kompilieren der Dienstanwendung

**Fehler BC30420 'Sub Main' wurde in 'GettingStartedHost.Module1' nicht gefunden.**

Der Einstiegspunkt ist für die Visual Basic-Anwendung falsch. Nehmen Sie die folgende Änderung vor:

   1. Wählen Sie im **Projektmappen-Explorer-Fenster** den Ordner **GettingStartedHost** aus, und wählen Sie dann **Eigenschaften** im Kontextmenü aus.
    a. Wählen Sie im Fenster **GettingStartedHost** für **das Startobjekt** **Service.Program** (oder den Einstiegspunkt für Ihre jeweilige Anwendung) aus der Liste aus.
    b. Wählen Sie im Hauptmenü **Datei** > **speichern alle**aus.

### <a name="run-the-service-application"></a>Ausführen der Dienstanwendung

**HTTP konnte die URL\/'http: /+:8000/GettingStarted/CalculatorService' nicht registrieren. Ihr Prozess verfügt nicht über Zugriffsrechte auf diesen Namespace.**

 Für einen ordnungsgemäßen Zugriff starten Sie den Prozess, der den Windows Communication Foundation (WCF)-Dienst mit Administratorrechten hostet:

- Für Visual Studio: Wählen Sie das Visual Studio-Programm im **Startmenü** aus, und wählen Sie dann im Kontextmenü **Mehr** > **Ausführen als Administrator** aus.
- Für ein Konsolenfenster: Wählen Sie im **Startmenü** **die Eingabeaufforderung** aus, und wählen Sie dann im Kontextmenü **Mehr** > **Ausführen als Administrator** aus.
- Für Windows Explorer: Wählen Sie die ausführbare Datei aus, und wählen Sie dann im Kontextmenü **ausführen als Administrator** aus.

### <a name="compile-the-client-application"></a>Kompilieren der Clientanwendung

**'CalculatorClient', enthält keine Definition\<für 'Methodenname>'\<und es konnte keine Erweiterungsmethode 'Methodenname>' gefunden werden, die ein erstes Argument vom Typ 'CalculatorClient' akzeptiert (fehlen eine Usinger Direktive oder ein Assemblyverweis?)**  

Nur die Methoden, die `ServiceOperationAttribute` Sie mit dem Attribut markieren, werden öffentlich verfügbar gemacht. Wenn Sie das `ServiceOperationAttribute` Attribut von einer `ICalculator` Methode in der Schnittstelle weglassen, wird diese Fehlermeldung während der Kompilierung angezeigt.  

**Der Typ oder Namespacename 'CalculatorClient' konnte nicht gefunden werden (fehlen Ihnen eine Usinger Direktive oder ein Assemblyverweis?)**

 Dieser Fehler wird angezeigt, wenn Sie die *Datei generatedProxy.cs* (oder *generatedProxy.vb*) nicht zu Ihrem Clientprojekt hinzufügen, wenn Sie sie mit dem Tool *Svcutil.exe* generiert haben.  

### <a name="run-the-client-application"></a>Ausführen der Clientanwendung

**Unbehandelte Ausnahme: System.ServiceModel.EndpointNotFoundException: Konnte keine\/Verbindung mit 'http: /localhost:8000/GettingStarted/CalculatorService' herstellen. TCP-Fehlercode 10061: Es konnte keine Verbindung hergestellt werden, da der Zielcomputer sie aktiv abgelehnt hat.**

Dieser Fehler tritt auf, wenn Sie die Clientanwendung ausführen, ohne den Dienst zuvor zu starten. Führen Sie zunächst die Hostanwendung aus, um den Dienst zu starten, und führen Sie dann die Clientanwendung aus.

### <a name="use-the-svcutilexe-tool"></a>Verwenden des Werkzeugs Svcutil.exe

**'Svcutil' wird nicht als interner oder externer Befehl, bedienbares Programm oder Batchdatei erkannt.**

 *Svcutil.exe* muss sich im Systempfad befinden. Die einfachste Lösung besteht darin, die Eingabeaufforderung für die Visual Studio-Eingabeaufforderung zu verwenden. Wählen Sie im **Menü Start** die **Visual Studio-Version \<>-Verzeichnis** aus, und wählen Sie dann Developer Command Prompt für **VS-Version \<>** aus. Diese Eingabeaufforderung legt den Systempfad auf die richtigen Speicherorte für alle Tools fest, die als Teil von Visual Studio ausgeliefert werden.  
  
### <a name="run-the-service-and-client-applications"></a>Ausführen der Dienst- und Clientanwendungen

**System.ServiceModel.Security.SecurityNegotiationException: SOAP-Sicherheitsaushandlung\/mit 'http: /localhost:8000/GettingStarted/CalculatorService' für Ziel 'http:\//localhost:8000/GettingStarted/CalculatorService' fehlgeschlagen**  

Dieser Fehler tritt auf einem Mitcomputer mit einer Domäne auf, der über keine Netzwerkkonnektivität verfügt. Verbinden Sie den Computer mit dem Netzwerk, oder deaktivieren Sie die Sicherheit sowohl für den Dienst als auch für den Client.

So deaktivieren Sie die Sicherheit:

- Ersetzen Sie für den Dienst `WSHttpBinding` den Code, der den erstellt, durch den folgenden Code:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Aktualisieren Sie für den Client in der Konfigurationsdatei das ** \<Sicherheitselement>** unter dem ** \<>-Element** wie folgt:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Weitere Informationen  
 [Erste Schritte mit WCF-Anwendungen](getting-started-tutorial.md)  
 [WCF-Fehlerbehebungs-Schnellstart](wcf-troubleshooting-quickstart.md)  
 [Beheben von Setup-Problemen](troubleshooting-setup-issues.md)
