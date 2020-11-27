---
title: Behandeln von Problemen mit den Tutorials für die ersten Schritte mit Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 4d471372419996c5bc490c2d0fdd83927428a41e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281338"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Behandeln von Problemen mit den Tutorials für die ersten Schritte mit Windows Communication Foundation

Dieser Artikel bietet Lösungen für die häufigsten Probleme und Fehler, die auftreten können, wenn Sie die Schritte im [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md)ausführen.
  
## <a name="common-problems"></a>Häufige Probleme

**Ich kann die Projektdateien auf der Festplatte nicht finden.**

 Visual Studio speichert Projektdateien unter *c:\Benutzer \\ &lt; Benutzername &gt; \source\repos*.  

**Ich kann die von *Svcutil.exe* generierte *App.config* Datei nicht finden.**

 In Visual Studio werden im Fenster **Vorhandenes Element hinzufügen** standardmäßig nur Dateien mit den folgenden Erweiterungen angezeigt:

- *.cs*
- *. resx*
- *. Settings*
- *. xsd*
- *WSDL*

Um alle Dateitypen anzuzeigen, wählen Sie in der Dropdown Liste in der Dropdown Liste in der unteren rechten Ecke des Fensters **Vorhandenes Element hinzufügen** die Option **alle Dateien ( \* . \* )** aus.  
  
## <a name="common-errors"></a>Häufige Fehler

### <a name="compile-the-service-application"></a>Kompilieren der Dienst Anwendung

**Fehler BC30420 "Sub Main" wurde in "gettingstartedhost. Module1" nicht gefunden.**

Der Einstiegspunkt für die Visual Basic-Anwendung ist falsch. Nehmen Sie folgende Änderung vor:

   1. Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **gettingstartedhost** aus, und klicken Sie dann im Kontextmenü auf **Eigenschaften** .
    a. Wählen Sie im Fenster **gettingstartedhost** für **Start Objekt** den Eintrag **Service. Program** (oder den Einstiegspunkt für die jeweilige Anwendung) aus der Liste aus.
    b. Klicken Sie im Hauptmenü auf **Datei**  >  **Alle speichern**.

### <a name="run-the-service-application"></a>Ausführen der Dienst Anwendung

**Http konnte die URL "http: \/ /+: 8000/GettingStarted/CalculatorService" nicht registrieren. Der Prozess verfügt nicht über Zugriffsrechte für diesen Namespace.**

 Um ordnungsgemäßen Zugriff zu erhalten, starten Sie den Prozess, der den Windows Communication Foundation (WCF)-Dienst mit Administratorrechten gehostet:

- Für Visual Studio: Wählen Sie das Visual Studio-Programm im **Startmenü** aus, und wählen Sie dann im Kontextmenü die Option **Weitere**  >  **als Administrator ausführen** aus.
- Für ein Konsolenfenster: Wählen Sie im Menü **Start** die Option **Eingabeaufforderung** aus, und wählen Sie dann im Kontextmenü die Option **Weitere**  >  **als Administrator ausführen** aus.
- Für Windows-Explorer: Wählen Sie die ausführbare Datei aus, und wählen Sie dann im Kontextmenü die Option **als Administrator ausführen** aus.

### <a name="compile-the-client-application"></a>Kompilieren der Client Anwendung

**' CalculatorClient ' enthält keine Definition für ' ', \<method name> und es konnte keine Erweiterungsmethode ' \<method name> ' verwendet werden, die ein erstes Argument vom Typ ' CalculatorClient ' akzeptiert. (fehlt eine using-Direktive oder ein Assemblyverweis?)**  

Nur die Methoden, die Sie mit dem-Attribut markieren, `ServiceOperationAttribute` werden öffentlich verfügbar gemacht. Wenn Sie das- `ServiceOperationAttribute` Attribut aus einer Methode in der- `ICalculator` Schnittstelle weglassen, erhalten Sie diese Fehlermeldung während der Kompilierung.  

**Der Typ-oder Namespace Name ' CalculatorClient ' konnte nicht gefunden werden. (fehlt eine using-Direktive oder ein Assemblyverweis?)**

 Sie erhalten diesen Fehler, wenn Sie die Datei *generatedProxy.cs* (oder *GeneratedProxy. vb*) nicht zum Client Projekt hinzufügen, wenn Sie Sie mit dem *Svcutil.exe* Tool generiert haben.  

### <a name="run-the-client-application"></a>Ausführen der Clientanwendung

**Unbehandelte Ausnahme: System. Service Model. EndpointNotFoundException: Es konnte keine Verbindung mit "http: \/ /localhost: 8000/GettingStarted/CalculatorService" hergestellt werden. TCP-Fehlercode 10061: Es konnte keine Verbindung hergestellt werden, da diese vom Zielcomputer aktiv verweigert wurde.**

Dieser Fehler tritt auf, wenn Sie die Client Anwendung ausführen, ohne den Dienst zu starten. Führen Sie zuerst die Host Anwendung aus, um den Dienst zu starten, und führen Sie dann die Client Anwendung aus.

### <a name="use-the-svcutilexe-tool"></a>Verwenden des Svcutil.exe Tools

**"Svcutil" wird nicht als interner oder externer Befehl, ausführbares Programm oder eine Batchdatei erkannt.**

 *Svcutil.exe* muss sich im Systempfad befinden. Die einfachste Lösung ist die Verwendung der Visual Studio-Eingabeaufforderung. Wählen Sie erst im Menü **Start** das Verzeichnis **Visual Studio\<version>** und anschließend **Developer-Eingabeaufforderung für Visual Studio \<version>** aus. Diese Eingabeaufforderung legt den Systempfad für alle Tools, die als Teil von Visual Studio ausgeliefert werden, auf die richtigen Speicherorte fest.  
  
### <a name="run-the-service-and-client-applications"></a>Ausführen von Dienst-und Client Anwendungen

**System. Service Model. Security. securityaushandationexception: die SOAP-Sicherheitsaus Handlung mit "http: \/ /localhost: 8000/GettingStarted/CalculatorService" für das Ziel "http: \/ /localhost: 8000/GettingStarted/CalculatorService" ist fehlgeschlagen.**  

Dieser Fehler tritt auf einem in die Domäne eingebundenen Computer auf, der nicht über eine Netzwerk Konnektivität verfügt. Verbinden Sie Ihren Computer mit dem Netzwerk, oder deaktivieren Sie die Sicherheit für den Dienst und den Client.

So deaktivieren Sie die Sicherheit:

- Ersetzen Sie für den-Dienst den Code, der das erstellt, `WSHttpBinding` durch den folgenden Code:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Aktualisieren Sie für den Client in der Konfigurationsdatei das- **\<security>** Element unter dem- **\<binding>** Element wie folgt:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator">
      <security mode="None" />
    </binding
    ```  

## <a name="see-also"></a>Weitere Informationen  

 [Einstieg in WCF-Anwendungen](getting-started-tutorial.md)  
 [Schnellstart zur WCF-Problembehandlung](wcf-troubleshooting-quickstart.md)  
 [Problembehandlung bei Setup Problemen](troubleshooting-setup-issues.md)
