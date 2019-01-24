---
title: Problembehandlung für das Lernprogramm "Erste Schritte"
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 5b8cd04ef4d98e522e255e1b7529e848351b2e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695659"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Problembehandlung für das Lernprogramm "Erste Schritte"
Dieses Thema enthält die beim Durcharbeiten des Lernprogramms "Erste Schritte" am häufigsten auftretenden Probleme sowie Möglichkeiten zur Problembehebung.  
  
**Ich kann die Projektdateien auf meiner Festplatte gefunden.**

 Visual Studio speichert Projektdateien im c:\users\\<user name>\Documents\\< Visual Studio-Version\>\Projects.  
  
**Versucht, die dienstanwendung auszuführen: HTTP konnte URL nicht registrieren `http://+:8000/ServiceModelSamples/Service/`.** 
 **Ihrem Prozess verfügt nicht über Zugriffsrechte für diesen Namespace.** 

 Der Prozess, der einen WCF-Dienst hostet, muss mit Administratorrechten ausgeführt werden. Wenn Sie den Dienst ausführen aus Visual Studio, Sie müssen Visual Studio als Administrator ausführen. Klicken Sie hierzu **starten**, mit der rechten Maustaste **Visual Studio \< *Version* >**  , und wählen Sie **als Administrator ausführen**. Wenn Sie den Dienst von einer Eingabeaufforderung in einem Konsolenfenster ausführen, müssen Sie das Konsolenfenster auf ähnliche Weise als Administrator starten. Klicken Sie auf **starten**, mit der rechten Maustaste **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen**.  
  
**Es wird versucht, das Tool Svcutil.exe verwenden: 'Svcutil' ist nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt.**

 "Svcutil.exe" muss sich im Systempfad befinden. Die einfachste Lösung stellt die Verwendung der Eingabeaufforderung dar. Klicken Sie auf **starten**Option **Programme**, **Visual Studio \< *Version*>**,  **Visual Studio-Tools**, und **Developer-Eingabeaufforderung für Visual Studio**. Diese Eingabeaufforderung wird der Systempfad auf die korrekten Speicherorte für alle Tools, die im Lieferumfang von Visual Studio.  

**Kann nicht zum Suchen der Datei "App.config"-Datei, die von Svcutil.exe generiert wurde.**

 Die **vorhandenes Element hinzufügen** zeigt das Dialogfeld nur Dateien mit den folgenden Erweiterungen standardmäßig: cs "," resx "," Settings "," XSD "," WSDL. Sie können angeben, dass Sie alle Dateitypen dazu finden Sie unter möchten **alle Dateien (\*.\*)**  im Dropdown-Listenfeld in der unteren rechten Ecke des der **vorhandenes Element hinzufügen** Dialogfeld.  


**Beim Kompilieren der Clientanwendung: 'CalculatorClient' enthält keine Definition für "\<Methodenname >' und keine Erweiterungsmethode '\<Methodenname >' akzeptieren ein erstes Argument vom Typ 'CalculatorClient' wurde gefunden (fehlt eine using Richtlinie oder ein der Assemblyverweis?)**  

Nur Methoden, die mit dem `ServiceOperationAttribute` markiert sind, werden für die Außenwelt verfügbar gemacht. Wenn Sie nicht angegeben. die `ServiceOperationAttribute` Attribut aus einer der Methoden in der `ICalculator` -Schnittstelle, Sie erhalten diese Fehlermeldung wird angezeigt, beim Kompilieren einer Clientanwendung, die den Vorgang ohne dieses Attribut aufruft.  

**Beim Kompilieren der Clientanwendung: Der Typ oder Namespace-Name 'CalculatorClient' nicht gefunden werden konnte (möglicherweise fehlt eine using-Direktive oder ein Assemblyverweis?)**

 Dieser Fehler tritt auf, wenn dem Clientprojekt die Datei "Proxy.cs" oder "Proxy.vb" nicht hinzugefügt wird.  

**Der Client ausgeführt wird: Ausnahmefehler: System.ServiceModel.EndpointNotFoundException: Konnte keine Verbindung mit `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. TCP-Fehlercode "10061": Es konnte keine Verbindung hergestellt werden, da vom Zielcomputer aktiv verweigert wurde.**

Dieser Fehler tritt auf, wenn Sie die Clientanwendung ausführen, ohne den Dienst auszuführen.  
  
**Nicht behandelte Ausnahme: System.ServiceModel.Security.SecurityNegotiationException: SOAP-Sicherheitsaushandlung mit `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` für Ziel `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` Fehler**  

Dieser Fehler tritt auf einem domänenverbundenen Computer auf, der nicht mit dem Netzwerk verbunden ist. Verbinden Sie den Computer entweder mit dem Netzwerk, oder deaktivieren Sie die Sicherheit für den Client oder den Dienst. Ändern Sie für den die WSHttpBinding-Bindung erstellenden Dienst den Code folgendermaßen ab.  
  
```csharp
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```

Für den Client Ändern der  **\<Sicherheit >** Element unter den  **\<Bindung >** Element der folgenden:  
  
```xml
<security mode="Node" />  
```  

## <a name="see-also"></a>Siehe auch
- [Tutorial mit ersten Schritten](../../../docs/framework/wcf/getting-started-tutorial.md)
- [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)
- [Behandeln von Setup-Problemen](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
