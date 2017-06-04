---
title: "Problembehandlung f&#252;r das Lernprogramm &quot;Erste Schritte&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Problembehandlung f&#252;r das Lernprogramm &quot;Erste Schritte&quot;
Dieses Thema enthält die beim Durcharbeiten des Lernprogramms "Erste Schritte" am häufigsten auftretenden Probleme sowie Möglichkeiten zur Problembehebung.  
  
1.  [Ich kann die Projektdateien auf meiner Festplatte nicht finden.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Beim Versuch, die Dienstanwendung auszuführen, wird Folgendes ausgegeben: "HTTP konnte URL 'http://+:8000/ServiceModelSamples/Service/' nicht registrieren.Der Prozess verfügt nicht über die Zugriffsrechte für diesen Namespace.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Beim Versuch, das Tool "Svcutil.exe" zu verwenden, wird Folgendes ausgegeben: "Der Befehl 'svcutil' ist entweder falsch geschrieben oder konnte nicht gefunden werden."](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Die von "Svcutil.exe" erstellte Datei "App.config" wurde nicht gefunden.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [Beim Kompilieren der Clientanwendung tritt der folgender Fehler auf: "'CalculatorClient' enthält keine Definition für '&lt;Methodenname&gt;', und es konnte keine Erweiterungsmethode '&lt;Methodenname&gt;' gefunden werden, die ein erstes Argument vom Typ 'CalculatorClient' akzeptiert. (Fehlt eine Using-Direktive oder ein Assemblyverweis?)"](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [Beim Kompilieren der Clientanwendung tritt folgender Fehler auf: "Der Typ- oder Namespacename 'CalculatorClient' konnte nicht gefunden werden. (Fehlt eine Using-Direktive oder ein Assemblyverweis?)"](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Beim Ausführen des Clients tritt folgender Fehler auf: Ausnahmefehler: System.ServiceModel.EndpointNotFoundException: Verbindung mit "http://localhost:8000/ServiceModelSamples/Service/CalculatorService" konnte nicht hergestellt werden.TCP-Fehlercode "10061": Es konnte keine Verbindung hergestellt werden, da der Zielcomputer die Verbindung verweigerte.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## Ich kann die Projektdateien auf meiner Festplatte nicht finden.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] speichert Projektdateien unter „C:\\Benutzer\\\<Benutzername\\Dokumente\\\<Visual Studio\-Version\>\\Projects“ \(unter [!INCLUDE[wv](../../../includes/wv-md.md)] und [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)]\) bzw. unter „C:\\Dokumente und Einstellungen\\\<Benutzername\>\\Eigene Dateien\\\<Visual Studio\-Version\>\\Projects“ \(ältere Windows\-Versionen\).  
  
<a name="BKMK_q2"></a>   
## Beim Versuch, die Dienstanwendung auszuführen, wird Folgendes ausgegeben: "HTTP konnte URL 'http:\/\/\+:8000\/ServiceModelSamples\/Service\/' nicht registrieren.Der Prozess verfügt nicht über die Zugriffsrechte für diesen Namespace.  
 Der Prozess, der einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst hostet, muss mit Administratorrechten ausgeführt werden.Wenn Sie den Dienst innerhalb von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] ausführen, müssen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] als Administrator ausführen.Klicken Sie hierzu auf **Start**, klicken Sie mit der rechten Maustaste auf [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], und wählen Sie **Als Administrator ausführen**.Wenn Sie den Dienst von einer Eingabeaufforderung aus ausführen, müssen Sie die Eingabeaufforderung ebenfalls als Administrator ausführen.Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.  
  
<a name="BKMK_q3"></a>   
## Beim Versuch, das Tool "Svcutil.exe" zu verwenden, wird Folgendes ausgegeben: "Der Befehl 'svcutil' ist entweder falsch geschrieben oder konnte nicht gefunden werden."  
 "Svcutil.exe" muss sich im Systempfad befinden.Die einfachste Lösung stellt die Verwendung der Eingabeaufforderung dar.Klicken Sie auf **Start**, wählen Sie **Alle Programme**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio Tools** und dann [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]**Eingabeaufforderung** aus.Durch diese Eingabeaufforderung wird der Systempfad auf die korrekten Speicherorte für alle Tools festgelegt, die im Lieferumfang von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] enthalten sind.  
  
<a name="BKMK_q4"></a>   
## Die von "Svcutil.exe" erstellte Datei "App.config" wurde nicht gefunden.  
 Im Dialogfeld **Vorhandenes Element hinzufügen** werden standardmäßig nur Dateien mit den folgenden Erweiterungen angezeigt: "CS", "RESX", "SETTINGS", "XSD", "WSDL".Sie können angeben, dass alle Dateitypen angezeigt werden sollen. Wählen Sie hierzu im Dropdown\-Listenfeld in der rechten unteren Ecke des Dialogfelds **Vorhandenes Element hinzufügen** die Option **Alle Dateien \(\*.\*\)** aus.  
  
<a name="BKMK_q5"></a>   
## Beim Kompilieren der Clientanwendung tritt der folgender Fehler auf: "'CalculatorClient' enthält keine Definition für '\<Methodenname\>', und es konnte keine Erweiterungsmethode '\<Methodenname\>' gefunden werden, die ein erstes Argument vom Typ 'CalculatorClient' akzeptiert. \(Fehlt eine Using\-Direktive oder ein Assemblyverweis?\)"  
 Nur Methoden, die mit dem `ServiceOperationAttribute` markiert sind, werden für die Außenwelt verfügbar gemacht.Wenn Sie das `ServiceOperationAttribute`\-Attribut bei einer der Methoden in der `ICalculator`\-Schnittstelle vergessen haben, wird beim Kompilieren einer Clientanwendung, die ohne dieses Attribut einen Aufruf an den Vorgang sendet, diese Fehlermeldung ausgegeben.  
  
<a name="BKMK_q6"></a>   
## Beim Kompilieren der Clientanwendung tritt folgender Fehler auf: "Der Typ\- oder Namespacename 'CalculatorClient' konnte nicht gefunden werden. \(Fehlt eine Using\-Direktive oder ein Assemblyverweis?\)"  
 Dieser Fehler tritt auf, wenn dem Clientprojekt die Datei "Proxy.cs" oder "Proxy.vb" nicht hinzugefügt wird.  
  
<a name="BKMK_q7"></a>   
## Beim Ausführen des Clients tritt folgender Fehler auf: Ausnahmefehler: System.ServiceModel.EndpointNotFoundException: Verbindung mit "http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService" konnte nicht hergestellt werden.TCP\-Fehlercode "10061": Es konnte keine Verbindung hergestellt werden, da der Zielcomputer die Verbindung verweigerte.  
 Dieser Fehler tritt auf, wenn Sie die Clientanwendung ausführen, ohne den Dienst auszuführen.  
  
<a name="BKMK_q8"></a>   
## Ausnahmefehler: System.ServiceModel.Security.SecurityNegotiationException: Fehler bei SOAP\-Sicherheitsaushandlung mit 'http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService' für Ziel 'http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService'.  
 Dieser Fehler tritt auf einem domänenverbundenen Computer auf, der nicht mit dem Netzwerk verbunden ist.Verbinden Sie den Computer entweder mit dem Netzwerk, oder deaktivieren Sie die Sicherheit für den Client oder den Dienst.Ändern Sie für den die WSHttpBinding\-Bindung erstellenden Dienst den Code folgendermaßen ab.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
  
```  
  
 Ändern Sie für diesen Client im Element **\<Bindung\>** das Element **\<Sicherheit\>** folgendermaßen:  
  
```  
<security mode="Node" />  
```  
  
## Siehe auch  
 [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)   
 [Behandeln von Setup\-Problemen](../../../docs/framework/wcf/troubleshooting-setup-issues.md)