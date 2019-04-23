---
title: Problembehandlung bei Nachrichtenwarteschlangen
ms.date: 03/30/2017
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
ms.openlocfilehash: c85b0701c870fe2b4a3c11dc384e890e1ed001dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977287"
---
# <a name="troubleshooting-queued-messaging"></a>Problembehandlung bei Nachrichtenwarteschlangen
Dieser Abschnitt enthält häufig gestellte Fragen und Hilfe zur Problembehandlung für die Verwendung von Warteschlangen in Windows Communication Foundation (WCF).  
  
## <a name="common-questions"></a>Allgemeine Fragen  
 **Q:** Den MSMQ-Hotfix installiert, und ich habe die WCF-Beta 1 verwendet. Muss ich den Hotfix entfernen?  
  
 **Antwort:** Ja. Dieser Hotfix wird nicht mehr unterstützt. WCF funktioniert nun ohne Hotfix MSMQ.  
  
 **Q:** Es gibt zwei Bindungen für MSMQ: <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Welche sollte ich wann verwenden?  
  
 **Antwort:** Verwenden Sie die <xref:System.ServiceModel.NetMsmqBinding> Wenn Sie MSMQ als Transport für eine warteschlangenkommunikation zwischen zwei WCF-Anwendungen verwenden möchten. Verwenden Sie die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> Wenn Sie vorhandene MSMQ-Anwendungen, die zur Kommunikation mit der neuen WCF-Anwendungen verwenden möchten.  
  
 **Q:** Muss ich MSMQ verwendet ein upgrade der <xref:System.ServiceModel.NetMsmqBinding> und `MsmqIntegration` Bindungen?  
  
 **Antwort:** Nein. Beide Bindungen funktionieren mit MSMQ 3.0 unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Bestimmte Funktionen der Bindungen werden verfügbar, wenn Sie in [!INCLUDE[wv](../../../../includes/wv-md.md)] ein Upgrade auf MSMQ 4.0 ausführen.  
  
 **Q:** Welche Features von der <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> Bindungen sind nur in MSMQ 4.0 und nicht in MSMQ 3.0 verfügbar?  
  
 **Antwort:** Die folgenden Features sind in MSMQ 4.0 jedoch nicht in MSMQ 3.0 verfügbar:  
  
-   Benutzerdefinierte Warteschlange für unzustellbare Nachrichten wird nur in MSMQ 4.0 unterstützt.  
  
-   In MSMQ 3.0 und 4.0 werden nicht verarbeitbare Nachrichten unterschiedlich behandelt.  
  
-   Nur MSMQ 4.0 unterstützt remote durchgeführte Lesevorgänge.  
  
 Weitere Informationen finden Sie unter [Unterschiede in Queuing-Funktionen in Windows Vista, Windows Server 2003 und Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **Q:** Kann ich MSMQ 3.0 auf einer Seite einer warteschlangenkommunikation und MSMQ 4.0 auf der anderen Seite verwenden?  
  
 **Antwort:** Ja.  
  
 **Q:** Ich möchte vorhandene MSMQ-Anwendungen in der neuen WCF-Clients oder Server zu integrieren. Muss ich beide Seiten der MSMQ-Infrastruktur aktualisieren?  
  
 **Antwort:** Nein. Sie müssen keine Seite auf MSMQ 4.0 aktualisieren.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Dieser Abschnitt enthält Informationen zur Behandlung der häufigsten Probleme. Bei einigen Fragen handelt es sich um bekannte Einschränkungen, die auch in den Releasehinweisen erläutert werden.  
  
 **Q:** Ich versuche, eine private Warteschlange verwenden, und ich erhalte die folgende Ausnahme: `System.InvalidOperationException`: Die URL ist ungültig. Die URL für die Warteschlange darf das Zeichen '$' nicht enthalten. Verwenden Sie die Syntax in net.msmq://machine/private/queueName, um eine private Warteschlange anzugeben.  
  
 **Antwort:** Überprüfen Sie die Warteschlange Uniform Resource Identifier (URI) in der Konfiguration und den Code ein. Verwenden Sie kein "$"-Zeichen im URI. Geben Sie z. B. zur Adressierung einer privaten Warteschlange mit dem Namen OrdersQueue den URI als net.msmq://localhost/private/ordersQueue an.  
  
 **Q:** Aufrufen von `ServiceHost.Open()` für meine Anwendung mit Queuing löst den folgenden Fehler: `System.ArgumentException`: Eine Basisadresse darf keine URI-Abfragezeichenfolge enthalten. Warum?  
  
 **Antwort:** Überprüfen Sie den Warteschlangen-URI in der Konfigurationsdatei und in Ihrem Code. Zwar wird in MSMQ-Warteschlangen die Verwendung von Fragezeichen ("?") unterstützt, diese werden von URIs jedoch als Beginn einer Zeichenfolgenabfrage interpretiert. Verwenden Sie deshalb Warteschlangennamen ohne Fragezeichen, um dieses Problem zu umgehen.  
  
 **Q:** Sendevorgang war erfolgreich, aber beim Empfänger kein Dienstvorgang aufgerufen. Warum?  
  
 **Antwort:** Um die Antwort zu bestimmen, arbeiten Sie über die folgende Liste:  
  
-   Überprüfen Sie, ob die Anforderungen der Transaktionswarteschlange mit den angegebenen Zusicherungen kompatibel sind. Beachten Sie die folgenden Prinzipien:  
  
    -   Sie können senden permanente Nachrichten (Datagramme und Sitzungen) mit "genau einmal"-zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) nur an eine Transaktionswarteschlange.  
  
    -   Sitzungen können nur mit "genau einmal"-Zusicherungen gesendet werden.  
  
    -   Eine Transaktion ist erforderlich, um Nachrichten in einer Sitzung von einer Transaktionswarteschlange zu empfangen.  
  
    -   Sie können Nachrichten senden oder empfangen beispielsweise flüchtiger oder permanente (nur Datagramme) ohne zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) nur für eine nicht transaktionale Warteschlange.  
  
-   Überprüfen Sie die Warteschlange für unzustellbare Nachrichten. Wenn Sie die Nachrichten dort finden, stellen Sie fest, warum sie nicht zugestellt wurden.  
  
-   Überprüfen Sie die ausgehenden Warteschlangen auf Konnektivitäts- oder Adressierungsprobleme.  
  
 **Q:** Eine benutzerdefinierte Warteschlange für unzustellbare angegeben ist, aber wenn ich die senderanwendung zu starten, erhalte ich eine Ausnahme, die entweder über die Warteschlange für unzustellbare Nachrichten nicht gefunden wird oder die sendende Anwendung hat keine Berechtigung für die Warteschlange für unzustellbare Nachrichten. Warum geschieht das?  
  
 **Antwort:** Die benutzerdefinierte Warteschlange für unzustellbare URI muss ein "Localhost" oder den Computernamen in das erste Segment, z. B. MSMQ://localhost/private/meineunzustwarteschlange enthalten.  
  
 **Q:** Ist es immer erforderlich ist, definieren eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten als unzustellbar zu kennzeichnen, oder gibt es eine Standard-Warteschlange für unzustellbare Nachrichten?  
  
 **Antwort:** Wenn "genau einmal"-zusicherungen werden (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), und wenn Sie eine benutzerdefinierte Warteschlange für unzustellbare nicht angeben, wird der Standardwert ist eine systemweite transaktionale Dead Letter-Warteschlange.  
  
 Wenn zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), dann die Standardeinstellung keine Funktionalität Dead Letter-Warteschlange ist.  
  
 **Q:** Mein Dienst löst auf SvcHost.Open mit einer Nachricht "EndpointListener-Anforderungen können nicht erfüllt werden durch die ListenerFactory" aus. Warum?  
  
 A. Überprüfen Sie den Dienstvertrag. Sie möglicherweise haben Sie vergessen "IsOneWay =`true`" auf alle Dienstvorgänge. Warteschlangen unterstützen nur unidirektionale Dienstvorgänge.  
  
 **Q:** Nachrichten in die Warteschlange vorhanden sind, aber kein Dienstvorgang aufgerufen wird. Wo liegt das Problem?  
  
 **Antwort:** Bestimmt, ob der Diensthost fehlerhaft ist. Sie können das feststellen, indem Sie die Ablaufverfolgung überprüfen oder `IErrorHandler` implementieren. Der Diensthost schlägt standardmäßig fehl, wenn eine nicht verarbeitbare Nachrichten erkannt wird.  
  
 **Q:** Nachrichten in die Warteschlange vorhanden sind, aber meine im Internet gehosteten in der Warteschlange befindlichen Dienst ist nicht aktiviert. Warum?  
  
 **Antwort:** Der häufigste Grund sind die Berechtigungen.  
  
1. Stellen Sie sicher, dass der `NetMsmqActivator`-Prozess ausgeführt wird und die Identität des `NetMsmqActivator`-Prozesses Lese- und Suchberechtigungen für die Warteschlange besitzt.  
  
2. Wenn `NetMsmqActivator` Warteschlangen auf einem Remotecomputer überwacht, stellen Sie sicher, dass `NetMsmqActivator` unter keinem eingeschränkten Token ausgeführt wird. So führen Sie `NetMsmqActivator` mit einem uneingeschränkten Token aus:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 Web-Host der sicherheitsrelevanter Probleme finden Sie unter: [Webhosting einer Anwendung mit Queuing](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).  
  
 **Q:** Was ist am einfachsten auf Sitzungen zugegriffen?  
  
 **Antwort:** Festlegen von AutoVervollständigen =`true` für den Vorgang, der die dem letzten Nachricht in der Sitzung, und legen Sie die automatische Vervollständigung =`false` auf alle verbleibenden Dienstvorgänge.  
  
 **Q:** Wo finde ich Antworten auf häufig gestellte Fragen zu MSMQ?  
  
 **Antwort:** Weitere Informationen zu MSMQ finden Sie unter [Microsoft Message Queuing](https://go.microsoft.com/fwlink/?LinkId=87810).  
  
 **Q:** Warum löst der Dienst eine `ProtocolException` beim Lesen aus einer Warteschlange, die beide enthält sitzungsnachrichten und datagrammnachrichten in Warteschlangen?  
  
 **Antwort:** Es ist ein wesentlicher Unterschied in der sitzungsnachrichten und in der Warteschlange datagrammnachrichten. Deshalb kann ein Dienst, der eine Sitzungsnachricht in einer Warteschlange lesen soll, keine Datagrammnachricht empfangen, und kann ein Dienst, der eine Datagrammnachricht in einer Warteschlange lesen soll, keine Sitzungsnachricht empfangen. Bei dem Versuch, beide Nachrichtentypen in derselben Warteschlange zu lesen, wird die folgende Ausnahme ausgelöst:  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 Bei der systemweiten Warteschlange für unzustellbare Nachrichten und auch bei benutzerdefinierten Warteschlangen für unzustellbare Nachrichten tritt dieses Problem schnell auf, wenn eine Anwendung Sitzungsnachrichten und Datagrammnachrichten in Warteschlangen vom selben Computer aus sendet. Wenn eine Nachricht nicht erfolgreich gesendet werden kann, wird sie in die Warteschlange für unzustellbare Nachrichten verschoben. Aus diesem Grund kann es vorkommen, dass sich sowohl Sitzung- als auch Datagrammnachrichten in der Warteschlange für unzustellbare Nachrichten befinden. Es gibt keine Möglichkeit, die beiden Nachrichtentypen beim Lesen einer Warteschlange zur Laufzeit zu trennen. Deshalb sollten Anwendungen Sitzungsnachrichten und Datagrammnachrichten in Warteschlangen nicht vom selben Computer aus senden.  
  
### <a name="msmq-integration-specific-troubleshooting"></a>MSMQ-Integration: Informationen zur Fehlerbehebung  
 **Q:** Wenn ich eine Nachricht senden, oder wenn ich den Diensthost öffne, erhalte ich eine Fehlermeldung, die angibt, dass das Schema falsch ist. Warum?  
  
 **Antwort:** Wenn Sie die MSMQ-Integration-Bindung verwenden, müssen Sie das msmq.formatname-Schema verwenden. Beispiel: msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Wenn Sie jedoch die benutzerdefinierte Warteschlange für unzustellbare Nachrichten angeben, müssen Sie das net.msmq-Schema verwenden.  
  
 **Q:** Wenn ich einen öffentlichen oder privaten Formatnamen verwenden, und Öffnen des Diensthosts auf [!INCLUDE[wv](../../../../includes/wv-md.md)], ich erhalte einen Fehler. Warum?  
  
 **Antwort:** Der WCF-Integration-Kanal auf [!INCLUDE[wv](../../../../includes/wv-md.md)] überprüft, ob eine untergeordnete Warteschlange für die hauptanwendung Warteschlange für die Behandlung nicht verarbeitbarer Nachrichten geöffnet werden kann. Der Name der untergeordneten Warteschlange wird von einem an den Listener übergebenen msmq.formatname-URI abgeleitet. Der Name der untergeordneten Warteschlange kann in MSMQ nur ein direkter Formatname sein. Deshalb tritt der Fehler auf. Ändern Sie den Warteschlangen-URI in einen direkten Formatnamen.  
  
 **Q:** Beim Empfang einer Nachricht von einer MSMQ-Anwendung wird die Nachricht in der Warteschlange befindet und nicht von der empfangenden WCF-Anwendung gelesen wird. Warum?  
  
 **Antwort:** Überprüfen Sie, ob die Nachricht einen Text enthält. Ohne Nachrichtentext ignoriert der MSMQ-Integrationskanal die Nachricht. Implementieren Sie `IErrorHandler`, um bei Ausnahmen benachrichtigt zu werden, und überprüfen Sie die Ablaufverfolgungen.  
  
### <a name="security-related-troubleshooting"></a>Sicherheitsrelevante Problembehandlung  
 **Q:** Beim Ausführen des Beispiels, die eine standardbindung im Arbeitsgruppenmodus verwendet, werden Nachrichten scheinbar gesendet wird, erhalten jedoch nie vom Empfänger empfangen werden.  
  
 **Antwort:** Standardmäßig werden Nachrichten mit einem internen MSMQ-Zertifikat, das von den Active Directory-Verzeichnisdienst erfordert signiert. Da Active Directory im Arbeitsgruppenmodus nicht verfügbar ist, verursacht das Signieren der Nachricht einen Fehler. Daher kommt die Nachricht in die Warteschlange für unzustellbare Nachrichten und Fehlerursache, wie z. B. "Ungültige Signatur" wird angezeigt.  
  
 Sie können das Problem beheben, indem Sie die Sicherheit deaktivien. Dies erfolgt durch Festlegen von <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None> , damit im Arbeitsgruppenmodus funktioniert.  
  
 Eine weitere Möglichkeit besteht darin, <xref:System.ServiceModel.MsmqTransportSecurity> aus der <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>-Eigenschaft abzurufen und auf <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> festzulegen und dann das Clientzertifikat festzulegen.  
  
 Sie können das Problem auch beheben, indem Sie MSMQ mit Active Directory-Integration installieren.  
  
 **Q:** Beim Senden einer Nachricht mit standardbindung (bei aktivierter transportsicherheit) in Active Directory an eine Warteschlange, die Meldung "Internes Zertifikat wurde nicht gefunden". Wie kann ich das Problem beheben?  
  
 **Antwort:** Dies bedeutet, dass das Zertifikat in Active Directory für den Absender erneuert werden muss. Öffnen Sie zu diesem Zweck **Systemsteuerung**, **Verwaltung**, **Computerverwaltung**, mit der rechten Maustaste **MSMQ**, und wählen Sie **Eigenschaften**. Wählen Sie die **Benutzerzertifikat** Registerkarte, und klicken Sie auf die **erneuern** Schaltfläche.  
  
 **Q:** Beim Senden einer Nachricht mit <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> und das zu verwendende Zertifikat angeben, wird die Meldung "Ungültiges Zertifikat". Wie kann ich das Problem beheben?  
  
 **Antwort:** Sie können keinen Zertifikatspeicher des lokalen Computers mit dem zertifikatmodus verwenden. Sie müssen das Zertifikat mit dem Zertifikat-Snap-In aus dem Zertifikatspeicher des Computers in den Speicher des aktuellen Benutzers kopieren. So rufen Sie das Zertifikat-Snap-In auf:  
  
1. Klicken Sie auf **starten**Option **ausführen**, Typ `mmc`, und klicken Sie auf **OK**.  
  
2. In der **Microsoft Management Console**öffnen die **Datei** Menü **Snap-In hinzufügen/entfernen**.  
  
3. In der **Snap-In hinzufügen/entfernen** Dialogfeld klicken Sie auf die **hinzufügen** Schaltfläche.  
  
4. In der **Standalone-Snap-in hinzufügen** (Dialogfeld), auf Zertifikate aus, und klicken Sie auf **hinzufügen**.  
  
5. In der **Zertifikate** wählen Sie im Snap-in-Dialogfeld **mein Benutzerkonto** , und klicken Sie auf **Fertig stellen**.  
  
6. Fügen Sie ein zweites Zertifkat-Snap-in der obigen Schritte, aber diesmal wählen **Computerkonto** , und klicken Sie auf **Weiter**.  
  
7. Wählen Sie **lokalen Computer** , und klicken Sie auf **Fertig stellen**. Sie können jetzt Zertifikate per Drag &amp; Drop aus dem Computerzertifikatspeicher in den Speicher des aktuellen Benutzers verschieben.  
  
 **Q:** Wenn mein Dienst aus einer Warteschlange auf einem anderen Computer im Arbeitsgruppenmodus liest, erhalte ich ein "Zugriff verweigert"-Ausnahme aus.  
  
 **Antwort:** Im Arbeitsgruppenmodus ausgeführt, damit eine Remoteanwendung für den Zugriff auf die Warteschlange, muss die Anwendung die Berechtigung Zugriff auf die Warteschlange. Zugriffssteuerungsliste (ACL) für die Warteschlange "Anonyme Anmeldung" hinzugefügt, und geben sie die read-Berechtigung.  
  
 **Q:** Wenn ein netzwerkdienstclient (oder jeder Client, der nicht über ein Domänenkonto verfügt), eine Nachricht in der Warteschlange sendet, schlägt der Sendevorgang wegen eines ungültigen Zertifikats fehl. Wie kann ich das Problem beheben?  
  
 **Antwort:** Überprüfen Sie die Bindungskonfiguration. Für die Standardbindung ist die MSMQ-Transportsicherheit zum Signieren der Nachricht aktiviert. Deaktivieren Sie sie.  
  
### <a name="remote-transacted-receives"></a>Remote durchgeführte Empfangsvorgänge  
 **Q:** Bei einer Warteschlange auf Computer ein, und ein WCF-Dienst, der liest Nachrichten aus einer Warteschlange auf Computer B (für die Remote durchgeführte Empfangsvorgänge Szenario), Nachrichten nicht aus der Warteschlange gelesen. Ablaufverfolgungsinformationen gibt an, die bei der der Empfang der Nachricht "Transaktion kann nicht importiert werden." Was kann ich tun, um dieses Problem zu beheben?  
  
 **Antwort:** Für dieses Problem gibt es drei mögliche Ursachen:  
  
-   Im Domänenmodus ist für remote durchgeführte Empfangsvorgänge ein MSDTC-Netzwerkzugriff (Microsoft Distributed Transaction Coordinator) erforderlich. Sie können dies mit **Komponenten hinzufügen/entfernen**.  
  
     ![Screenshot mit Aktivieren der Netzwerk-DTC Zugriff.](./media/troubleshooting-queued-messaging/enable-distributed-transaction-coordinator-access.jpg)  
  
-   Überprüfen Sie den Authentifizierungsmodus für die Kommunikation mit dem Transaktions-Manager. Wenn Sie im Arbeitsgruppenmodus ausgeführt sind, muss "Keine Authentifizierung erforderlich" ausgewählt werden. Wenn Sie im Domänenmodus sind, muss "Gegenseitige Authentifizierung erforderlich" ausgewählt werden.  
  
     ![Aktivieren von XA-Transaktionen](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")  
  
-   Stellen Sie sicher, dass MSDTC in der Liste der Ausnahmen in der **Internetverbindungsfirewall** Einstellungen.  
  
-   Stellen Sie sicher, dass Sie [!INCLUDE[wv](../../../../includes/wv-md.md)] verwenden. MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt remote durchgeführte Lesevorgänge. MSMQ in früheren Windows-Releases unterstützt keine remote durchgeführten Lesevorgänge.  
  
 **Q:** Wenn der Dienst, der aus der Warteschlange liest einen Netzwerkdienst ist, wird z. B. in einer Web-Host, warum ich eine zugriffsverweigerung-Ausnahme erhalte ausgelöst, wenn aus der Warteschlange zu lesen?  
  
 **Antwort:** Lesezugriff des Netzwerkdiensts muss hinzugefügt werden, zu der Warteschlangen-ACL, um sicherzustellen, dass ein Dienst aus der Warteschlange lesen kann.  
  
 **Q:** Kann ich den MSMQ-Aktivierungsdienst verwenden, um Anwendungen, die basierend auf Nachrichten in einer Warteschlange auf einem Remotecomputer zu aktivieren?  
  
 **Antwort:** Ja. Sie müssen dazu den MSMQ-Aktivierungsdienst als Netzwerkdienst konfigurieren und der Warteschlange auf dem Remotecomputer den Netzwerkdienstzugriff hinzufügen.  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Verwenden von benutzerdefinierten MSMQ-Bindungen mit aktiviertem ReceiveContext  
 Bei Verwendung einer benutzerdefinierten MSMQ-Bindung mit aktiviertem <xref:System.ServiceModel.Channels.ReceiveContext> wird eine eingehende Nachricht mit einem Thread aus einem Threadpool verarbeitet, da das systemeigene MSMQ keine E/A-Vervollständigung für den asynchronen <xref:System.ServiceModel.Channels.ReceiveContext>-Empfang unterstützt. Dies liegt daran, dass bei der Verarbeitung einer solchen Nachricht interne Transaktionen für <xref:System.ServiceModel.Channels.ReceiveContext> verwendet werden und MSMQ keine asynchrone Verarbeitung unterstützt. Um dieses Problem zu umgehen, können Sie dem Endpunkt ein <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> hinzufügen, um die asynchrone Verarbeitung zu erzwingen, oder Sie können <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> auf 1 festlegen.
