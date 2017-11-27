---
title: Problembehandlung bei Nachrichtenwarteschlangen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c12f02bc40764c1e4acc70906c6145988103d9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-queued-messaging"></a>Problembehandlung bei Nachrichtenwarteschlangen
Dieser Abschnitt enthält allgemeine Fragen und Hinweise zur Problembehandlung bei der Verwendung von Warteschlangen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="common-questions"></a>Allgemeine Fragen  
 **F:** verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Beta 1, und ich den MSMQ-Hotfix installiert. Muss ich den Hotfix entfernen?  
  
 **A:** Ja. Dieser Hotfix wird nicht mehr unterstützt. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] funktioniert nun ohne Hotfix mit MSMQ.  
  
 **F:** stehen zwei Bindungen für MSMQ: <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Welche sollte ich wann verwenden?  
  
 **A:** verwenden die <xref:System.ServiceModel.NetMsmqBinding> Wenn Sie MSMQ als Transport für eine warteschlangenkommunikation zwischen zwei verwenden möchten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Anwendungen. Verwenden Sie <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>, wenn Sie vorhandene MSMQ-Anwendungen für die Kommunikation mit neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen verwenden möchten.  
  
 **F:** habe ich MSMQ zu verwenden, Aktualisieren der <xref:System.ServiceModel.NetMsmqBinding> und `MsmqIntegration` Bindungen?  
  
 **A:** No. Beide Bindungen funktionieren mit MSMQ 3.0 unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Bestimmte Funktionen der Bindungen werden verfügbar, wenn Sie in [!INCLUDE[wv](../../../../includes/wv-md.md)] ein Upgrade auf MSMQ 4.0 ausführen.  
  
 **F:** welche Funktionen von der <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> -Bindung sind in MSMQ 4.0 jedoch nicht in MSMQ 3.0 verfügbar?  
  
 **A:** die folgenden Funktionen sind in MSMQ 4.0 jedoch nicht in MSMQ 3.0 verfügbar:  
  
-   Benutzerdefinierte Warteschlange für unzustellbare Nachrichten wird nur in MSMQ 4.0 unterstützt.  
  
-   In MSMQ 3.0 und 4.0 werden nicht verarbeitbare Nachrichten unterschiedlich behandelt.  
  
-   Nur MSMQ 4.0 unterstützt remote durchgeführte Lesevorgänge.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Unterschiede in den Warteschlangenfunktionen in Windows Vista, WindowsServer 2003 und Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **F:** kann ich MSMQ 3.0 auf einer Seite der warteschlangenkommunikation und MSMQ 4.0 auf der anderen Seite verwenden?  
  
 **A:** Ja.  
  
 **F:** ich möchte vorhandene MSMQ-Anwendungen mit den neuen integrieren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clients oder Server. Muss ich beide Seiten der MSMQ-Infrastruktur aktualisieren?  
  
 **A:** No. Sie müssen keine Seite auf MSMQ 4.0 aktualisieren.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Dieser Abschnitt enthält Informationen zur Behandlung der häufigsten Probleme. Bei einigen Fragen handelt es sich um bekannte Einschränkungen, die auch in den Releasehinweisen erläutert werden.  
  
 **F:** ich versuche, eine private Warteschlange verwenden und erhalte ich mit folgenden Ausnahme: `System.InvalidOperationException`: die URL ist ungültig. Die URL für die Warteschlange darf das Zeichen '$' nicht enthalten. Verwenden Sie die Syntax in net.msmq://machine/private/queueName, um eine private Warteschlange anzugeben.  
  
 **A:** überprüfen Sie die Warteschlange Uniform Resource Identifier (URI) in der Konfiguration und Code. Verwenden Sie kein "$"-Zeichen im URI. Geben Sie z. B. zur Adressierung einer privaten Warteschlange mit dem Namen OrdersQueue den URI als net.msmq://localhost/private/ordersQueue an.  
  
 **F:** Aufrufen `ServiceHost.Open()` für meine in der Warteschlange stehende Anwendung löst eine die folgende Ausnahme: `System.ArgumentException`: eine Basisadresse darf keine URI-Abfragezeichenfolge enthalten. Warum?  
  
 **A:** überprüfen Sie den Warteschlangen-URI in der Konfigurationsdatei und im Code. Zwar wird in MSMQ-Warteschlangen die Verwendung von Fragezeichen ("?") unterstützt, diese werden von URIs jedoch als Beginn einer Zeichenfolgenabfrage interpretiert. Verwenden Sie deshalb Warteschlangennamen ohne Fragezeichen, um dieses Problem zu umgehen.  
  
 **F:** Sendevorgang war erfolgreich, jedoch wird beim Empfänger kein Dienstvorgang aufgerufen. Warum?  
  
 **A:** absolvieren, um die Antwort zu bestimmen, die folgende Liste:  
  
-   Überprüfen Sie, ob die Anforderungen der Transaktionswarteschlange mit den angegebenen Zusicherungen kompatibel sind. Beachten Sie die folgenden Prinzipien:  
  
    -   Sie können senden permanente Nachrichten (Datagramme und Sitzungen) mit "genau einmal"-zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) nur an eine transaktionale Warteschlange.  
  
    -   Sitzungen können nur mit "genau einmal"-Zusicherungen gesendet werden.  
  
    -   Eine Transaktion ist erforderlich, um Nachrichten in einer Sitzung von einer Transaktionswarteschlange zu empfangen.  
  
    -   Sie können senden oder Empfangen von temporäre oder permanente Nachrichten (nur Datagramme) ohne zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) nur an eine nicht transaktionale Warteschlange.  
  
-   Überprüfen Sie die Warteschlange für unzustellbare Nachrichten. Wenn Sie die Nachrichten dort finden, stellen Sie fest, warum sie nicht zugestellt wurden.  
  
-   Überprüfen Sie die ausgehenden Warteschlangen auf Konnektivitäts- oder Adressierungsprobleme.  
  
 **F:** ich eine benutzerdefinierte Warteschlange für unzustellbare angegeben haben, aber wenn ich die absenderanwendung zu starten, erhalte ich eine Ausnahme, die entweder an die Dead Letter-Warteschlange nicht gefunden wird, oder die sendende Anwendung hat keine Berechtigung für die Dead Letter-Warteschlange. Warum geschieht das?  
  
 **A:** die benutzerdefinierte Warteschlange für unzustellbare URI muss ein "Localhost" oder den Computernamen in das erste Segment, z. B. MSMQ://localhost/private/meineunzustwarteschlange enthalten.  
  
 **F:** ist es immer erforderlich ist, eine benutzerdefinierte Warteschlange für unzustellbare definieren, oder gibt es eine standardmäßige Warteschlange für unzustellbare?  
  
 **A:** Wenn "genau einmal"-zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), und wenn Sie eine benutzerdefinierte Warteschlange für unzustellbare nicht angeben, wird der Standardwert ist eine systemweite transaktionale Dead Letter-Warteschlange.  
  
 Wenn zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), wird standardmäßig keine Funktionalität Dead Letter-Warteschlange.  
  
 **F:** Mein Dienst löst bei Svchost.Open Ausnahme mit der eine Nachricht "EndpointListener-Anforderungen können nicht erfüllt werden durch die ListenerFactory". Warum?  
  
 A. Überprüfen Sie den Dienstvertrag. Sie möglicherweise haben Sie vergessen "IsOneWay =`true`" für alle Dienstvorgänge. Warteschlangen unterstützen nur unidirektionale Dienstvorgänge.  
  
 **F:** Nachrichten in der Warteschlange vorhanden sind, aber kein Dienstvorgang aufgerufen wird. Wo liegt das Problem?  
  
 **A:** zu bestimmen, ob der Diensthost fehlerhaft ist. Sie können das feststellen, indem Sie die Ablaufverfolgung überprüfen oder `IErrorHandler` implementieren. Der Diensthost schlägt standardmäßig fehl, wenn eine nicht verarbeitbare Nachrichten erkannt wird.  
  
 **F:** Nachrichten in der Warteschlange vorhanden sind, aber in der Warteschlange im Internet gehosteten Dienst ist nicht aktiviert. Warum?  
  
 **A:** der häufigste Grund ist die Berechtigungen.  
  
1.  Stellen Sie sicher, dass der `NetMsmqActivator`-Prozess ausgeführt wird und die Identität des `NetMsmqActivator`-Prozesses Lese- und Suchberechtigungen für die Warteschlange besitzt.  
  
2.  Wenn `NetMsmqActivator` Warteschlangen auf einem Remotecomputer überwacht, stellen Sie sicher, dass `NetMsmqActivator` unter keinem eingeschränkten Token ausgeführt wird. So führen Sie `NetMsmqActivator` mit einem uneingeschränkten Token aus:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 Nicht sicherheitsrelevantes verwandte Web hostprobleme finden Sie unter: [Webhosting einer Anwendung in der Warteschlange](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).  
  
 **F:** was die einfachste Möglichkeit, Access-Sitzungen ist?  
  
 **A:** AutoVervollständigen festgelegt =`true` auf den Vorgang, der dem letzten Nachricht in der Sitzung, und legen Sie AutoComplete =`false` für alle verbleibenden Dienstvorgänge.  
  
 **F:** Wo finde ich Antworten auf häufig gestellte Fragen zu MSMQ?  
  
 **A:** [!INCLUDE[crabout](../../../../includes/crabout-md.md)] MSMQ, finden Sie unter [Microsoft Message Queuing](http://go.microsoft.com/fwlink/?LinkId=87810).  
  
 **F:** Warum löst der Dienst eine `ProtocolException` beim Lesen aus einer Warteschlange, die sowohl sitzungsnachrichten und datagrammnachrichten in Warteschlangen?  
  
 **A:** es ist ein wesentlicher Unterschied in der sitzungsnachrichten und Datagrammnachricht Nachrichten bestehen aus. Deshalb kann ein Dienst, der eine Sitzungsnachricht in einer Warteschlange lesen soll, keine Datagrammnachricht empfangen, und kann ein Dienst, der eine Datagrammnachricht in einer Warteschlange lesen soll, keine Sitzungsnachricht empfangen. Bei dem Versuch, beide Nachrichtentypen in derselben Warteschlange zu lesen, wird die folgende Ausnahme ausgelöst:  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 Bei der systemweiten Warteschlange für unzustellbare Nachrichten und auch bei benutzerdefinierten Warteschlangen für unzustellbare Nachrichten tritt dieses Problem schnell auf, wenn eine Anwendung Sitzungsnachrichten und Datagrammnachrichten in Warteschlangen vom selben Computer aus sendet. Wenn eine Nachricht nicht erfolgreich gesendet werden kann, wird sie in die Warteschlange für unzustellbare Nachrichten verschoben. Aus diesem Grund kann es vorkommen, dass sich sowohl Sitzung- als auch Datagrammnachrichten in der Warteschlange für unzustellbare Nachrichten befinden. Es gibt keine Möglichkeit, die beiden Nachrichtentypen beim Lesen einer Warteschlange zur Laufzeit zu trennen. Deshalb sollten Anwendungen Sitzungsnachrichten und Datagrammnachrichten in Warteschlangen nicht vom selben Computer aus senden.  
  
### <a name="msmq-integration-specific-troubleshooting"></a>MSMQ-Integration: Spezielle Problembehandlung  
 **F:** , wenn eine Nachricht zu senden, oder wenn ich den Diensthost öffne, erhalte ich die eine Fehlermeldung, der angibt, das Schema falsch ist. Warum?  
  
 **A:** Wenn Sie die Bindung für die MSMQ-Integration verwenden, müssen Sie das msmq.formatname-Schema verwenden. Beispiel: msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Wenn Sie jedoch die benutzerdefinierte Warteschlange für unzustellbare Nachrichten angeben, müssen Sie das net.msmq-Schema verwenden.  
  
 **F:** Wenn ich einen öffentlichen oder privaten Formatnamen verwenden, und Öffnen des Diensthosts auf [!INCLUDE[wv](../../../../includes/wv-md.md)], eine Fehlermeldung. Warum?  
  
 **A:** der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Integrationskanal unter [!INCLUDE[wv](../../../../includes/wv-md.md)] prüft, ob eine Unterwarteschlange kann, für die Hauptassembly der Anwendungswarteschlange geöffnet werden für unzustellbare Nachrichten zu verarbeiten. Der Name der untergeordneten Warteschlange wird von einem an den Listener übergebenen msmq.formatname-URI abgeleitet. Der Name der untergeordneten Warteschlange kann in MSMQ nur ein direkter Formatname sein. Deshalb tritt der Fehler auf. Ändern Sie den Warteschlangen-URI in einen direkten Formatnamen.  
  
 **F:** beim Empfang einer Nachricht aus einer MSMQ-Anwendung die Nachricht befindet sich in der Warteschlange und wird nicht gelesen werden, von der empfangenden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Anwendung. Warum?  
  
 **A:** Kontrollkästchen, um festzustellen, ob die Nachricht einen Text enthält. Ohne Nachrichtentext ignoriert der MSMQ-Integrationskanal die Nachricht. Implementieren Sie `IErrorHandler`, um bei Ausnahmen benachrichtigt zu werden, und überprüfen Sie die Ablaufverfolgungen.  
  
### <a name="security-related-troubleshooting"></a>Sicherheitsrelevante Problembehandlung  
 **F:** beim Ausführen des Beispiels, die eine standardbindung im Arbeitsgruppenmodus verwendet wird, werden Nachrichten scheinbar gesendet, kommen jedoch nie beim Empfänger empfangen werden.  
  
 **A:** standardmäßig Nachrichten signiert werden mit einem internen MSMQ-Zertifikat, die die Active Directory-Verzeichnisdienst erforderlich sind. Da Active Directory im Arbeitsgruppenmodus nicht verfügbar ist, verursacht das Signieren der Nachricht einen Fehler. Daher kommt die Nachricht in die Dead Letter-Warteschlange sowie Fehlerursache, z. B. "Ungültige Signatur" angegeben werden.  
  
 Sie können das Problem beheben, indem Sie die Sicherheit deaktivien. Dies erfolgt durch Festlegen von <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None> im Arbeitsgruppenmodus funktionieren.  
  
 Eine weitere Möglichkeit besteht darin, <xref:System.ServiceModel.MsmqTransportSecurity> aus der <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>-Eigenschaft abzurufen und auf <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> festzulegen und dann das Clientzertifikat festzulegen.  
  
 Sie können das Problem auch beheben, indem Sie MSMQ mit Active Directory-Integration installieren.  
  
 **F:** beim Senden einer Nachricht mit standardbindung (bei aktivierter transportsicherheit) in Active Directory an eine Warteschlange, die Meldung "Internes Zertifikat wurde nicht gefunden". Wie kann ich das Problem beheben?  
  
 **A:** Dies bedeutet, dass das Zertifikat in Active Directory für den Absender erneuert werden muss. Öffnen Sie hierzu **Systemsteuerung**, **Verwaltung**, **Computerverwaltung**, mit der rechten Maustaste **MSMQ**, und wählen Sie **Eigenschaften**. Wählen Sie die **Benutzerzertifikat** Registerkarte, und klicken Sie auf die **erneuern** Schaltfläche.  
  
 **F:** beim Senden einer Nachricht mit <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> und das zu verwendende Zertifikat angeben, die Meldung "Ungültiges Zertifikat". Wie kann ich das Problem beheben?  
  
 **A:** einen Zertifikatspeicher des lokalen Computers mit zertifikatmodus nicht verwendet werden können. Sie müssen das Zertifikat mit dem Zertifikat-Snap-In aus dem Zertifikatspeicher des Computers in den Speicher des aktuellen Benutzers kopieren. So rufen Sie das Zertifikat-Snap-In auf:  
  
1.  Klicken Sie auf **starten**Option **ausführen**, Typ `mmc`, und klicken Sie auf **OK**.  
  
2.  In der **Microsoft Management Console**öffnen die **Datei** Menü **Snap-In hinzufügen/entfernen**.  
  
3.  In der **Snap-In hinzufügen/entfernen** (Dialogfeld), klicken Sie auf die **hinzufügen** Schaltfläche.  
  
4.  In der **Standalone-Snap-in hinzufügen** (Dialogfeld), wählen Sie Zertifikate und klicken Sie auf **hinzufügen**.  
  
5.  In der **Zertifikate** wählen Sie im Snap-in-Dialogfeld **eigenes Benutzerkonto** , und klicken Sie auf **Fertig stellen**.  
  
6.  Als Nächstes fügen Sie ein zweites Zertifkat-Snap-in mit den vorherigen Schritten, aber diesmal wählen **Computerkonto** , und klicken Sie auf **Weiter**.  
  
7.  Wählen Sie **Sicherheitszertifikate** , und klicken Sie auf **Fertig stellen**. Sie können jetzt Zertifikate per Drag & Drop aus dem Computerzertifikatspeicher in den Speicher des aktuellen Benutzers verschieben.  
  
 **F:** wenn mein Dienst liest aus einer Warteschlange auf einem anderen Computer im Arbeitsgruppenmodus, erhalte ich eine Ausnahme von "Zugriff verweigert".  
  
 **A:** im Arbeitsgruppenmodus für eine Remoteanwendung für den Zugriff auf die Warteschlange muss die Anwendung über die Berechtigung, auf die Warteschlange zuzugreifen. Zugriffssteuerungsliste (ACL) für die Warteschlange "Anonyme Anmeldung" hinzu, und weisen Sie ihm die Berechtigung Lesen.  
  
 **F:** , wenn ein netzwerkdienstclient (oder jeder Client, der kein Domänenkonto) eine in der Warteschlange stehende Nachricht sendet, das Senden eines ungültigen Zertifikats tritt bei. Wie kann ich das Problem beheben?  
  
 **A:** überprüfen Sie die Bindungskonfiguration. Für die Standardbindung ist die MSMQ-Transportsicherheit zum Signieren der Nachricht aktiviert. Deaktivieren Sie sie.  
  
### <a name="remote-transacted-receives"></a>Remote durchgeführte Empfangsvorgänge  
 **F:** Wenn ich eine Warteschlange auf Computer A haben und ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst, liest Nachrichten aus einer Warteschlange auf Computer B (Szenario "die Remote durchgeführter Empfangsvorgänge"), Nachrichten aus der Warteschlange nicht gelesen werden. Ablaufverfolgungsinformationen gibt an, bei der der Empfang der Nachricht "Transaktion kann nicht importiert werden." Was kann ich tun, um dieses Problem zu beheben?  
  
 **A:** gibt es drei mögliche Ursachen dafür sind:  
  
-   Im Domänenmodus ist für remote durchgeführte Empfangsvorgänge ein MSDTC-Netzwerkzugriff (Microsoft Distributed Transaction Coordinator) erforderlich. Sie können dies mithilfe von **Komponenten hinzufügen/entfernen**.  
  
     ![Aktivieren des DTC-Netzwerkzugriffs](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")  
  
-   Überprüfen Sie den Authentifizierungsmodus für die Kommunikation mit dem Transaktions-Manager. Wenn Sie im Arbeitsgruppenmodus ausgeführt werden, muss "Keine Authentifizierung erforderlich" ausgewählt. Wenn Sie im Domänenmodus sind, muss "Gegenseitige Authentifizierung erforderlich" ausgewählt.  
  
     ![Aktivieren von XA-Transaktionen](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")  
  
-   Stellen Sie sicher, dass MSDTC in der Liste der Ausnahmen in ist die **Internetverbindungsfirewall** Einstellungen.  
  
-   Stellen Sie sicher, dass Sie [!INCLUDE[wv](../../../../includes/wv-md.md)] verwenden. MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt remote durchgeführte Lesevorgänge. MSMQ in früheren Windows-Releases unterstützt keine remote durchgeführten Lesevorgänge.  
  
 **F:** wird der Dienst beim Lesen aus der Warteschlange Netzwerkdienst, z. B. in einem Web Host, warum ich eine Zugriff verweigert-Ausnahme erhalte wird ausgelöst, wenn aus der Warteschlange zu lesen?  
  
 **A:** Lesezugriff des Netzwerkdiensts muss der Warteschlangen-ACL, um sicherzustellen, dass ein Netzwerkdienst aus der Warteschlange lesen kann hinzugefügt werden.  
  
 **F:** können die MSMQ-Aktivierungsdienst zum Aktivieren von Anwendungen auf Grundlage von Nachrichten in einer Warteschlange auf einem Remotecomputer verwenden?  
  
 **A:** Ja. Sie müssen dazu den MSMQ-Aktivierungsdienst als Netzwerkdienst konfigurieren und der Warteschlange auf dem Remotecomputer den Netzwerkdienstzugriff hinzufügen.  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Verwenden von benutzerdefinierten MSMQ-Bindungen mit aktiviertem ReceiveContext  
 Bei Verwendung einer benutzerdefinierten MSMQ-Bindung mit aktiviertem <xref:System.ServiceModel.Channels.ReceiveContext> wird eine eingehende Nachricht mit einem Thread aus einem Threadpool verarbeitet, da das systemeigene MSMQ keine E/A-Vervollständigung für den asynchronen <xref:System.ServiceModel.Channels.ReceiveContext>-Empfang unterstützt. Dies liegt daran, dass bei der Verarbeitung einer solchen Nachricht interne Transaktionen für <xref:System.ServiceModel.Channels.ReceiveContext> verwendet werden und MSMQ keine asynchrone Verarbeitung unterstützt. Um dieses Problem zu umgehen, können Sie dem Endpunkt ein <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> hinzufügen, um die asynchrone Verarbeitung zu erzwingen, oder Sie können <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> auf 1 festlegen.
