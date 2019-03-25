---
title: Problembehandlung bei den Get Schritte mit Windows Communication Foundation-Lernprogramme
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 8089e0fee262d07be591069982b1aacfbeae2521
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410497"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Problembehandlung bei den Get Schritte mit Windows Communication Foundation-Lernprogramme

Dieser Artikel bietet Lösungen für die häufigsten Probleme und Fehler, die Sie möglicherweise stoßen, wenn Sie die Schritte in der [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md). 
  
## <a name="common-problems"></a>Häufige Probleme

**Die Projektdateien auf meiner Festplatte wurde nicht gefunden.**

 Speichert Projektdateien in Visual Studio *C:\Users\\&lt;Benutzernamen&gt;\source\repos*.  

**Nicht auffindbar der *"App.config"* von generierten Datei *Svcutil.exe*.**

 In Visual Studio die **vorhandenes Element hinzufügen** Fenster werden standardmäßig nur Dateien mit den folgenden Erweiterungen angezeigt: 
- *.cs* 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

Wählen Sie zum Anzeigen aller Dateitypen **alle Dateien (\*.\*)**  in der Dropdown-Liste in der unteren rechten Ecke des der **vorhandenes Element hinzufügen** Fenster.  
  
## <a name="common-errors"></a>Häufige Fehler

### <a name="compile-the-service-application"></a>Kompilieren Sie die dienstanwendung 

**Fehler-BC30420 'Sub Main' in 'GettingStartedHost.Module1' nicht gefunden.**

Der Einstiegspunkt ist für die Visual Basic-Anwendung unzulässig. Nehmen Sie folgende Änderung:

   1. In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStartedHost** Ordner, und wählen Sie dann **Eigenschaften** aus dem Kontextmenü.
    a. In der **GettingStartedHost** Fenster für **Startobjekt**Option **Service.Program** (oder den Einstiegspunkt für Ihre spezifische Anwendung) aus der Liste. 
    b. Wählen Sie im Hauptmenü **Datei** > **Alles speichern**.

### <a name="run-the-service-application"></a>Führen Sie die dienstanwendung 

**HTTP konnte URL nicht registrieren ' http:\// +: 8000/GettingStarted/CalculatorService '. Der Prozess verfügt nicht über die Zugriffsrechte für diesen Namespace.** 

 Starten Sie für den ordnungsgemäßen Zugriff der Hostprozess für den Windows Communication Foundation (WCF)-Dienst mit Administratorrechten aus:
- Für Visual Studio: Wählen Sie das Visual Studio-Programm in der **starten** Menü, und wählen Sie dann **weitere** > **als Administrator ausführen** aus dem Kontextmenü.
- Für ein Konsolenfenster: Wählen Sie **Eingabeaufforderung** in die **starten** Menü, und wählen Sie dann **weitere** > **Ausführen als Administrator** über die Verknüpfung ein Menü.
- Für Windows-Explorer: Wählen Sie die ausführbare Datei, und wählen Sie dann **als Administrator ausführen** aus dem Kontextmenü.

### <a name="compile-the-client-application"></a>Kompilieren Sie die Clientanwendung

**'CalculatorClient', enthält keine Definition für "\<Methodenname >' und keine Erweiterungsmethode '\<Methodenname >' akzeptieren ein erstes Argument vom Typ 'CalculatorClient' wurde gefunden (fehlt eine using Richtlinie oder ein der Assemblyverweis?)**  

Nur die Methoden, die Sie markieren, mit der `ServiceOperationAttribute` Attribut sind öffentlich verfügbar gemacht. Wenn Sie weglassen der `ServiceOperationAttribute` Attribut aus einer Methode in der `ICalculator` -Schnittstelle, Sie erhalten diese Fehlermeldung wird angezeigt, während der Kompilierung.  

**Der Typ oder Namespace-Name 'CalculatorClient' nicht gefunden werden konnte (möglicherweise fehlt eine using-Direktive oder ein Assemblyverweis?)**

 Sie erhalten diesen Fehler, wenn Sie nicht die *"generatedproxy.cs"* (oder *generatedProxy.vb*) Datei in das Clientprojekt, wenn Sie diese mit generiert die *Svcutil.exe* Tool .  

### <a name="run-the-client-application"></a>Führen Sie die Clientanwendung

**Nicht behandelte Ausnahme: System.ServiceModel.EndpointNotFoundException: Konnte keine Verbindung mit "http:\//localhost:8000/GettingStarted/CalculatorService '. TCP-Fehlercode "10061": Es konnte keine Verbindung hergestellt werden, da vom Zielcomputer aktiv verweigert wurde.**

Dieser Fehler tritt auf, wenn Sie die Clientanwendung ausführen, ohne den ersten Start des Diensts. Zunächst führen Sie die hostanwendung "zum Starten des Diensts, und führen Sie dann die Client-Anwendung.

### <a name="use-the-svcutilexe-tool"></a>Verwenden Sie das Svcutil.exe-tool
   
**'Svcutil' ist nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt.**

 *Svcutil.exe* muss im Systempfad. Die einfachste Lösung ist die Verwendung der Visual Studio-Eingabeaufforderung. Von der **starten** , wählen Sie im Menü der **Visual Studio \<Version >** Verzeichnis, und klicken Sie dann **Entwicklereingabeaufforderung für VS \<Version >**. Diese Eingabeaufforderung wird der Systempfad auf die korrekten Speicherorte für alle Tools, die im Lieferumfang von Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Führen Sie die Dienst und Client-Anwendungen

**System.ServiceModel.Security.SecurityNegotiationException: SOAP-Sicherheitsaushandlung mit ' http:\//localhost:8000/GettingStarted/CalculatorService ' für Ziel "http:\//localhost:8000/GettingStarted/CalculatorService" konnte nicht**  

Dieser Fehler tritt in eine Domäne eingebundenen Computer an, der nicht über eine Netzwerkverbindung verfügen. Verbinden Sie den Computer mit dem Netzwerk oder für den Dienst und Client-Sicherheit deaktivieren. 

Um Sicherheit zu deaktivieren:

- Ersetzen Sie für den Dienst, den Code, erstellt die `WSHttpBinding` durch den folgenden Code:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Für den Client, in die XML-Konfigurationsdatei aktualisieren die  **\<Sicherheit >** Element unter den  **\<Bindung >** -Element wie folgt:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit WCF-Anwendungen](getting-started-tutorial.md)  
 [Schnelleinstieg zur Problembehandlung in WCF](wcf-troubleshooting-quickstart.md)  
 [Problembehandlung bei der Installation](troubleshooting-setup-issues.md)
