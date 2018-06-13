---
title: Problembehandlung für das Lernprogramm "Erste Schritte"
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 12812bd1ef88eab14a8defed0b71657b0d33c618
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807787"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Problembehandlung für das Lernprogramm "Erste Schritte"
Dieses Thema enthält die beim Durcharbeiten des Lernprogramms "Erste Schritte" am häufigsten auftretenden Probleme sowie Möglichkeiten zur Problembehebung.  
  
1.  [Ich bin nicht die Projektdateien auf meiner Festplatte gefunden.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Beim Ausführen der dienstanwendung: HTTP URL nicht registrieren http://+:8000/ServiceModelSamples/Service/. Der Prozess verfügt nicht über die Zugriffsrechte für diesen Namespace.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Das Tool Svcutil.exe verwenden möchten: "Svcutil" wird nicht als ein interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Es wurde die Datei "App.config", die von Svcutil.exe generiert wurde gefunden.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [Beim Kompilieren der Clientanwendung: 'CalculatorClient' enthält keine Definition für '&lt;Methodennamen&gt;'und keine Erweiterungsmethode'&lt;Methodennamen&gt;"ein erstes Argument vom Typ 'CalculatorClient' akzeptiert gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [Beim Kompilieren der Clientanwendung: der Typ oder Namespace-Name 'CalculatorClient' konnte nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Der Client ausgeführt wird: nicht behandelte Ausnahme: System.ServiceModel.EndpointNotFoundException: konnte keine Verbindung mit http://localhost:8000/ServiceModelSamples/Service/CalculatorService. TCP-Fehlercode "10061": Es konnte keine Verbindung hergestellt werden, da vom Zielcomputer aktiv verweigert wurde.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## <a name="i-am-unable-to-find-the-project-files-on-my-hard-drive"></a>Ich kann die Projektdateien auf meiner Festplatte nicht finden.  
 Visual Studio speichert Projektdateien im c:\users\\< Benutzer Name\Documents\\< Visual Studio-Version\>\Projects [!INCLUDE[wv](../../../includes/wv-md.md)] und [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)], und c:\Documents and Settings\\< Benutzername \>\My Dokumente\\< Visual Studio-Version\>\Projects frühere Versionen von Windows.  
  
<a name="BKMK_q2"></a>   
## <a name="attempting-to-run-the-service-application-http-could-not-register-url-http8000servicemodelsamplesservice-your-process-does-not-have-access-rights-to-this-namespace"></a>Beim Ausführen der dienstanwendung: HTTP URL nicht registrieren http://+:8000/ServiceModelSamples/Service/. Der Prozess verfügt nicht über die Zugriffsrechte für diesen Namespace.  
 Der Prozess, der einen WCF-Dienst hostet, muss mit Administratorrechten ausgeführt werden. Wenn Sie den Dienst innerhalb von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] ausführen, müssen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] als Administrator ausführen. Klicken Sie hierzu **starten**, mit der rechten Maustaste [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] , und wählen Sie **als Administrator ausführen**. Wenn Sie den Dienst von einer Eingabeaufforderung aus ausführen, müssen Sie die Eingabeaufforderung ebenfalls als Administrator ausführen. Klicken Sie auf **starten**, mit der rechten Maustaste **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen**.  
  
<a name="BKMK_q3"></a>   
## <a name="attempting-to-use-the-svcutilexe-tool-svcutil-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file"></a>Beim Versuch, das Tool "Svcutil.exe" zu verwenden, wird Folgendes ausgegeben: "Der Befehl 'svcutil' ist entweder falsch geschrieben oder konnte nicht gefunden werden."  
 "Svcutil.exe" muss sich im Systempfad befinden. Die einfachste Lösung stellt die Verwendung der Eingabeaufforderung dar. Klicken Sie auf **starten**Option **Programme**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio-Tools**, und [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] **Eingabeaufforderung**. Durch diese Eingabeaufforderung wird der Systempfad auf die korrekten Speicherorte für alle Tools festgelegt, die im Lieferumfang von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] enthalten sind.  
  
<a name="BKMK_q4"></a>   
## <a name="unable-to-find-the-appconfig-file-generated-by-svcutilexe"></a>Die von "Svcutil.exe" erstellte Datei "App.config" wurde nicht gefunden.  
 Die **vorhandenes Element hinzufügen** Dialogfeld werden standardmäßig nur Dateien mit den folgenden Erweiterungen angezeigt: cs "," resx "," Settings "", "XSD", "WSDL". Sie können angeben, dass alle Dateitypen dazu angezeigt werden soll **alle Dateien (\*.\*)**  im Dropdown-Listenfeld in der unteren rechten Ecke des der **vorhandenes Element hinzufügen** (Dialogfeld).  
  
<a name="BKMK_q5"></a>   
## <a name="compiling-the-client-application-calculatorclient-does-not-contain-a-definition-for-method-name-and-no-extension-method-method-name-accepting-a-first-argument-of-type-calculatorclient-could-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Beim Kompilieren der Clientanwendung: 'CalculatorClient' enthält keine Definition für "\<Methodenname >' und keine Erweiterungsmethode '\<Methodenname >' ein erstes Argument vom Typ 'CalculatorClient' akzeptiert gefunden (Sie sind fehlt eine using-Direktive oder ein Assemblyverweis?)  
 Nur Methoden, die mit dem `ServiceOperationAttribute` markiert sind, werden für die Außenwelt verfügbar gemacht. Wenn Sie das `ServiceOperationAttribute`-Attribut bei einer der Methoden in der `ICalculator`-Schnittstelle vergessen haben, wird beim Kompilieren einer Clientanwendung, die ohne dieses Attribut einen Aufruf an den Vorgang sendet, diese Fehlermeldung ausgegeben.  
  
<a name="BKMK_q6"></a>   
## <a name="compiling-the-client-application-the-type-or-namespace-name-calculatorclient-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Beim Kompilieren der Clientanwendung tritt folgender Fehler auf: "Der Typ- oder Namespacename 'CalculatorClient' konnte nicht gefunden werden. (Fehlt eine Using-Direktive oder ein Assemblyverweis?)"  
 Dieser Fehler tritt auf, wenn dem Clientprojekt die Datei "Proxy.cs" oder "Proxy.vb" nicht hinzugefügt wird.  
  
<a name="BKMK_q7"></a>   
## <a name="running-the-client-unhandled-exception-systemservicemodelendpointnotfoundexception-could-not-connect-to-httplocalhost8000servicemodelsamplesservicecalculatorservice-tcp-error-code-10061-no-connection-could-be-made-because-the-target-machine-actively-refused-it"></a>Der Client ausgeführt wird: nicht behandelte Ausnahme: System.ServiceModel.EndpointNotFoundException: konnte keine Verbindung mit http://localhost:8000/ServiceModelSamples/Service/CalculatorService. TCP-Fehlercode "10061": Es konnte keine Verbindung hergestellt werden, da der Zielcomputer die Verbindung verweigerte.  
 Dieser Fehler tritt auf, wenn Sie die Clientanwendung ausführen, ohne den Dienst auszuführen.  
  
<a name="BKMK_q8"></a>   
## <a name="unhandled-exception-systemservicemodelsecuritysecuritynegotiationexception-soap-security-negotiation-with-httplocalhost8000servicemodelsamplesservicecalculatorservice-for-target-httplocalhost8000servicemodelsamplesservicecalculatorservice-failed"></a>Nicht behandelte Ausnahme: System.ServiceModel.Security.SecurityNegotiationException: SOAP-Sicherheitsaushandlung mit 'http://localhost:8000/ServiceModelSamples/Service/CalculatorService'für Ziel"http://localhost:8000/ServiceModelSamples/Service/CalculatorService' fehlgeschlagen  
 Dieser Fehler tritt auf einem domänenverbundenen Computer auf, der nicht mit dem Netzwerk verbunden ist. Verbinden Sie den Computer entweder mit dem Netzwerk, oder deaktivieren Sie die Sicherheit für den Client oder den Dienst. Ändern Sie für den die WSHttpBinding-Bindung erstellenden Dienst den Code folgendermaßen ab.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```  
  
 Ändern Sie für den Client die  **\<Sicherheit >** Element unter den  **\<Bindung >** -Element folgendermaßen:  
  
```xml  
<security mode="Node" />  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tutorial mit ersten Schritten](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [Behandeln von Setup-Problemen](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
