---
title: Problembehandlung bei Nachrichtenwarteschlangen
ms.date: 03/30/2017
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
ms.openlocfilehash: 7990d4b9847ee2f35b9fe6269bb211763c4c80b6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095007"
---
# <a name="troubleshooting-queued-messaging"></a>Problembehandlung bei Nachrichtenwarteschlangen

Dieser Abschnitt enthält häufig gestellte Fragen und Hilfe zur Problembehandlung bei der Verwendung von Warteschlangen in Windows Communication Foundation (WCF).

## <a name="common-questions"></a>Häufig gestellte Fragen

**F:** Ich habe WCF Beta 1 verwendet und den MSMQ-Hotfix installiert. Muss ich den Hotfix entfernen?

**A:** Ja. Dieser Hotfix wird nicht mehr unterstützt. WCF funktioniert nun ohne hotfixanforderung in MSMQ.

**F:** Es gibt zwei Bindungen für MSMQ: <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Welche sollte ich wann verwenden?

**A:** Verwenden Sie die <xref:System.ServiceModel.NetMsmqBinding>, wenn Sie MSMQ als Transport für die Kommunikation in der Warteschlange zwischen zwei WCF-Anwendungen verwenden möchten. Verwenden Sie die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>, wenn Sie vorhandene MSMQ-Anwendungen für die Kommunikation mit neuen WCF-Anwendungen verwenden möchten.

**F:** Muss ich MSMQ aktualisieren, um die <xref:System.ServiceModel.NetMsmqBinding>-und `MsmqIntegration` Bindungen zu verwenden?

**A:** Nein. Beide Bindungen funktionieren mit MSMQ 3,0 unter Windows XP und Windows Server 2003. Bestimmte Funktionen der Bindungen werden verfügbar, wenn Sie ein Upgrade auf MSMQ 4,0 in Windows Vista durchführen.

**F:** Welche Features der <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> Bindungen sind in MSMQ 4,0 verfügbar, aber nicht in MSMQ 3,0?

**A:** Die folgenden Features sind in MSMQ 4,0 verfügbar, aber nicht in MSMQ 3,0:

- Benutzerdefinierte Warteschlange für unzustellbare Nachrichten wird nur in MSMQ 4.0 unterstützt.

- In MSMQ 3.0 und 4.0 werden nicht verarbeitbare Nachrichten unterschiedlich behandelt.

- Nur MSMQ 4.0 unterstützt remote durchgeführte Lesevorgänge.

Weitere Informationen finden Sie [unter Unterschiede in den Warteschlangen Funktionen in Windows Vista, Windows Server 2003 und Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).

**F:** Kann ich MSMQ 3,0 auf einer Seite einer Kommunikation in der Warteschlange und MSMQ 4,0 auf der anderen Seite verwenden?

**A:** Ja.

**F:** Ich möchte vorhandene MSMQ-Anwendungen in neue WCF-Clients oder-Server integrieren. Muss ich beide Seiten der MSMQ-Infrastruktur aktualisieren?

**A:** Nein. Sie müssen keine Seite auf MSMQ 4.0 aktualisieren.

## <a name="troubleshooting"></a>Problembehandlung

Dieser Abschnitt enthält Informationen zur Behandlung der häufigsten Probleme. Bei einigen Fragen handelt es sich um bekannte Einschränkungen, die auch in den Releasehinweisen erläutert werden.

**F:** Ich versuche, eine private Warteschlange zu verwenden, und erhalte die folgende Ausnahme: `System.InvalidOperationException`: die URL ist ungültig. Die URL für die Warteschlange darf das Zeichen '$' nicht enthalten. Verwenden Sie die Syntax in net.msmq://machine/private/queueName, um eine private Warteschlange anzugeben.

**A:** Überprüfen Sie die Warteschlangen Uniform Resource Identifier (URI) in der Konfiguration und im Code. Verwenden Sie kein "$"-Zeichen im URI. Wenn Sie beispielsweise eine private Warteschlange mit dem Namen ordersQueue adressieren möchten, geben Sie den URI als `net.msmq://localhost/private/ordersQueue`an.

**F:** Das Aufrufen von `ServiceHost.Open()` für meine Anwendung in der Warteschlange löst die folgende Ausnahme aus: `System.ArgumentException`: eine Basisadresse darf keine URI-Abfrage Zeichenfolge enthalten. Warum?

**A:** Überprüfen Sie den Warteschlangen-URI in der Konfigurationsdatei und im Code. Zwar wird in MSMQ-Warteschlangen die Verwendung von Fragezeichen ("?") unterstützt, diese werden von URIs jedoch als Beginn einer Zeichenfolgenabfrage interpretiert. Verwenden Sie deshalb Warteschlangennamen ohne Fragezeichen, um dieses Problem zu umgehen.

**F:** Der Sendevorgang war erfolgreich, aber für den Empfänger wurde kein Dienst Vorgang aufgerufen. Warum?

**A:** Um die Antwort zu ermitteln, können Sie die folgende Checkliste durcharbeiten:

- Überprüfen Sie, ob die Anforderungen der Transaktionswarteschlange mit den angegebenen Zusicherungen kompatibel sind. Beachten Sie die folgenden Prinzipien:

  - Sie können permanente Nachrichten (Datagramme und Sitzungen) mit "genau einmal"-Zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) nur an eine transaktionale Warteschlange senden.

  - Sitzungen können nur mit "genau einmal"-Zusicherungen gesendet werden.

  - Eine Transaktion ist erforderlich, um Nachrichten in einer Sitzung von einer Transaktionswarteschlange zu empfangen.

  - Sie können nur flüchtige oder dauerhafte Nachrichten (nur Datagramme) ohne Zusicherungen (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) an eine nicht transaktionale Warteschlange senden oder empfangen.

- Überprüfen Sie die Warteschlange für unzustellbare Nachrichten. Wenn Sie die Nachrichten dort finden, stellen Sie fest, warum sie nicht zugestellt wurden.

- Überprüfen Sie die ausgehenden Warteschlangen auf Konnektivitäts- oder Adressierungsprobleme.

**F:** Ich habe eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten angegeben, aber beim Starten der Absender Anwendung erhalte ich eine Ausnahme, dass entweder die Warteschlange für unzustellbare Nachrichten nicht gefunden wurde oder dass die sendende Anwendung keine Berechtigung für die Warteschlange für unzustellbare Nachrichten hat. Warum ist das so?

**A:** Der benutzerdefinierte URI der Warteschlange für unzustellbare Nachrichten muss einen "localhost" oder den Computernamen im ersten Segment enthalten, z. b. "net. MSMQ://localhost/private/myAppdead-Letter Queue".

**F:** Muss immer eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten definiert werden, oder gibt es eine Standard Warteschlange für unzustellbare Nachrichten?

**A:** Wenn Zusicherungen "genau einmal" (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) sind, und wenn Sie keine benutzerdefinierte Warteschlange für unzustellbare Nachrichten angeben, ist der Standardwert eine systemweite transaktionale Warteschlange für unzustellbare Nachrichten.

Wenn Zusicherungen keine (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) ist, ist der Standardwert keine Warteschlange für unzustellbare Nachrichten.

**F:** Der Dienst löst "svchost. Open" mit der Meldung "EndpointListener-Anforderungen können von der Listenerfactory nicht erfüllt werden" aus. Warum?

A. Überprüfen Sie den Dienstvertrag. Möglicherweise haben Sie vergessen, "IsOneWay =`true`" für alle Dienst Vorgänge zu platzieren. Warteschlangen unterstützen nur unidirektionale Dienstvorgänge.

**F:** Es sind Nachrichten in der Warteschlange vorhanden, es wird jedoch kein Dienst Vorgang aufgerufen. Welches Problem liegt vor?

**A:** Stellen Sie fest, ob der Dienst Host fehlerhaft ist. Sie können das feststellen, indem Sie die Ablaufverfolgung überprüfen oder `IErrorHandler` implementieren. Der Diensthost schlägt standardmäßig fehl, wenn eine nicht verarbeitbare Nachrichten erkannt wird.

**F:** Es befinden sich Nachrichten in der Warteschlange, aber mein im Internet gehosteter Dienst in der Warteschlange wird nicht aktiviert. Warum?

**A:** Der häufigste Grund hierfür sind Berechtigungen.

1. Stellen Sie sicher, dass der `NetMsmqActivator`-Prozess ausgeführt wird und die Identität des `NetMsmqActivator`-Prozesses Lese- und Suchberechtigungen für die Warteschlange besitzt.

2. Wenn `NetMsmqActivator` Warteschlangen auf einem Remotecomputer überwacht, stellen Sie sicher, dass `NetMsmqActivator` unter keinem eingeschränkten Token ausgeführt wird. So führen Sie `NetMsmqActivator` mit einem uneingeschränkten Token aus:

    ```console
    sc sidtype NetMsmqActivator unrestricted
    ```

Informationen zu Webhost Problemen, die nicht sicherheitsrelevant sind, finden Sie unter: [Webhosting einer Anwendung in der Warteschlange](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).

**F:** Was ist die einfachste Möglichkeit, um auf Sitzungen zuzugreifen?

**A:** Legen Sie AutoComplete =`true` für den Vorgang fest, der der letzten Meldung in der Sitzung entspricht, und legen Sie AutoComplete =`false` für alle verbleibenden Dienst Vorgänge fest.

**F:** Warum löst der Dienst beim Lesen aus einer Warteschlange, die sowohl Sitzungsnachrichten in Warteschlangen als auch in der Warteschlange befindliche Datagrammnachrichten enthält, eine `ProtocolException` aus?

**A:** Es gibt einen grundlegenden Unterschied bei der Zusammenstellung von Sitzungsnachrichten in der Warteschlange und in der Warteschlange befindliche Datagrammnachrichten. Deshalb kann ein Dienst, der eine Sitzungsnachricht in einer Warteschlange lesen soll, keine Datagrammnachricht empfangen, und kann ein Dienst, der eine Datagrammnachricht in einer Warteschlange lesen soll, keine Sitzungsnachricht empfangen. Bei dem Versuch, beide Nachrichtentypen in derselben Warteschlange zu lesen, wird die folgende Ausnahme ausgelöst:

```console
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.
```

Bei der systemweiten Warteschlange für unzustellbare Nachrichten und auch bei benutzerdefinierten Warteschlangen für unzustellbare Nachrichten tritt dieses Problem schnell auf, wenn eine Anwendung Sitzungsnachrichten und Datagrammnachrichten in Warteschlangen vom selben Computer aus sendet. Wenn eine Nachricht nicht erfolgreich gesendet werden kann, wird sie in die Warteschlange für unzustellbare Nachrichten verschoben. Aus diesem Grund kann es vorkommen, dass sich sowohl Sitzung- als auch Datagrammnachrichten in der Warteschlange für unzustellbare Nachrichten befinden. Es gibt keine Möglichkeit, die beiden Nachrichtentypen beim Lesen einer Warteschlange zur Laufzeit zu trennen. Deshalb sollten Anwendungen Sitzungsnachrichten und Datagrammnachrichten in Warteschlangen nicht vom selben Computer aus senden.

### <a name="msmq-integration-specific-troubleshooting"></a>MSMQ-Integration: Spezielle Problembehandlung

**F:** Wenn ich eine Nachricht Sende, oder wenn ich den Dienst Host öffne, erhalte ich eine Fehlermeldung, die angibt, dass das Schema falsch ist. Warum?

**A:** Wenn Sie die MSMQ-Integrations Bindung verwenden, müssen Sie das Schema "MSMQ. Format Name" verwenden. Beispiel: msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Wenn Sie jedoch die benutzerdefinierte Warteschlange für unzustellbare Nachrichten angeben, müssen Sie das net.msmq-Schema verwenden.

**F:** Wenn ich einen öffentlichen oder privaten Format Namen verwende und den Dienst Host unter Windows Vista öffne, erhalte ich eine Fehlermeldung. Warum?

**A:** Der WCF-Integrationskanal unter Windows Vista prüft, ob eine unter Warteschlange für die Haupt Anwendungs Warteschlange für die Behandlung nicht verarbeitbarer Nachrichten geöffnet werden kann. Der Name der unter Warteschlange wird von einem MSMQ. formatname-URI abgeleitet, der an den Listener weitergegeben wurde. Der Name der unter Warteschlange in MSMQ kann nur ein direkter Format Name sein. Deshalb tritt der Fehler auf. Ändern Sie den Warteschlangen-URI in einen direkten Formatnamen.

**F:** Wenn eine Nachricht von einer MSMQ-Anwendung empfangen wird, befindet sich die Nachricht in der Warteschlange und wird von der empfangenden WCF-Anwendung nicht gelesen. Warum?

**A:** Überprüfen Sie, ob die Nachricht einen Text enthält. Ohne Nachrichtentext ignoriert der MSMQ-Integrationskanal die Nachricht. Implementieren Sie `IErrorHandler`, um bei Ausnahmen benachrichtigt zu werden, und überprüfen Sie die Ablaufverfolgungen.

### <a name="security-related-troubleshooting"></a>Sicherheitsrelevante Problembehandlung

**F:** Wenn das Beispiel ausgeführt wird, das eine Standard Bindung im Arbeitsgruppen Modus verwendet, scheinen die Nachrichten gesendet zu werden, werden jedoch nie vom Empfänger empfangen.

**A:** Standardmäßig werden Nachrichten mithilfe eines internen MSMQ-Zertifikats signiert, für das der Active Directory Directory-Dienst erforderlich ist. Da Active Directory im Arbeitsgruppenmodus nicht verfügbar ist, verursacht das Signieren der Nachricht einen Fehler. Daher wird die Nachricht in der Warteschlange für unzustellbare Nachrichten angezeigt, und es wird eine Fehlerursache wie "Ungültige Signatur" angezeigt.

Sie können das Problem beheben, indem Sie die Sicherheit deaktivien. Dies erfolgt durch Festlegen <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A> = <xref:System.ServiceModel.NetMsmqSecurityMode.None>, damit Sie im Arbeitsgruppen Modus funktioniert.

Eine weitere Möglichkeit besteht darin, <xref:System.ServiceModel.MsmqTransportSecurity> aus der <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>-Eigenschaft abzurufen und auf <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> festzulegen und dann das Clientzertifikat festzulegen.

Sie können das Problem auch beheben, indem Sie MSMQ mit Active Directory-Integration installieren.

**F:** Wenn eine Nachricht mit der Standard Bindung (Transportsicherheit aktiviert) in Active Directory an eine Warteschlange gesendet wird, erhalte ich die Meldung "internes Zertifikat wurde nicht gefunden". Wie kann ich dies korrigieren?

**A:** Dies bedeutet, dass das Zertifikat in Active Directory für den Absender erneuert werden muss. Öffnen Sie hierzu die **Systemsteuerung**, **Verwaltung**, **Computer Verwaltung**, klicken Sie mit der rechten Maustaste auf **MSMQ**, und wählen Sie **Eigenschaften**aus. Wählen Sie die Registerkarte **Benutzerzertifikat** aus, und klicken Sie auf **erneuern** .

**F:** Beim Senden einer Nachricht mithilfe <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> und angeben des zu verwendenden Zertifikats erhalte ich die Meldung "Ungültiges Zertifikat". Wie kann ich dies korrigieren?

**A:** Ein Zertifikat Speicher für lokale Computer kann nicht mit dem Zertifikat Modus verwendet werden. Sie müssen das Zertifikat mit dem Zertifikat-Snap-In aus dem Zertifikatspeicher des Computers in den Speicher des aktuellen Benutzers kopieren. So rufen Sie das Zertifikat-Snap-In auf:

1. Klicken Sie im **Startmenü**auf **Ausführen**, geben Sie `mmc`ein, und klicken Sie auf **OK**.

2. Öffnen Sie in der **Microsoft Management Console**das Menü **Datei** , und wählen Sie **Snap-in hinzufügen/entfernen**aus.

3. Klicken Sie im Dialogfeld **Snap-in hinzufügen/entfernen** auf die Schaltfläche **Hinzufügen** .

4. Wählen Sie im Dialogfeld **eigenständiges Snap-in hinzufügen** Zertifikate aus, und klicken Sie auf **Hinzufügen**.

5. Wählen Sie im Dialogfeld **Zertifikate** -Snap-in die Option eigenes **Benutzerkonto aus,** und klicken Sie auf **Fertig**stellen.

6. Fügen Sie als nächstes ein zweites Zertifikat-Snap-in mit den vorherigen Schritten hinzu. Wählen Sie dieses Mal jedoch **Computer Konto** aus, und klicken Sie auf **weiter**.

7. Klicken Sie auf **Lokaler Computer**, und klicken Sie dann auf **Fertig stellen**. Sie können jetzt Zertifikate per Drag &amp; Drop aus dem Computerzertifikatspeicher in den Speicher des aktuellen Benutzers verschieben.

**F:** Wenn mein Dienst aus einer Warteschlange auf einem anderen Computer im Arbeitsgruppen Modus liest, wird eine Ausnahme vom Typ "Zugriff verweigert" angezeigt.

**A:** Im Arbeitsgruppen Modus muss die Anwendung über die Berechtigung verfügen, auf die Warteschlange zuzugreifen, damit eine Remote Anwendung Zugriff auf die Warteschlange erhält. Fügen Sie der Zugriffs Steuerungs Liste (ACL) der Warteschlange "anonyme Anmeldung" hinzu, und erteilen Sie Ihr die Leseberechtigung.

**F:** Wenn ein Netzwerkdienst Client (oder ein Client, der nicht über ein Domänen Konto verfügt) eine Nachricht in der Warteschlange sendet, schlägt der Sendevorgang mit einem ungültigen Zertifikat fehl. Wie kann ich dies korrigieren?

**A:** Überprüfen Sie die Bindungs Konfiguration. Für die Standardbindung ist die MSMQ-Transportsicherheit zum Signieren der Nachricht aktiviert. Deaktivieren Sie sie.

### <a name="remote-transacted-receives"></a>Remote durchgeführte Empfangsvorgänge

**F:** Wenn eine Warteschlange auf Computer a vorhanden ist, und ein WCF-Dienst, der Nachrichten aus einer Warteschlange auf Computer B (dem transaktiven Remote Empfangs Szenario) liest, werden Nachrichten nicht aus der Warteschlange gelesen. Ablauf Verfolgungs Informationen geben an, dass der Empfangs Fehler mit der Meldung "die Transaktion kann nicht importiert werden". Wie kann ich dieses Problem beheben?

**A:** Hierfür gibt es drei mögliche Gründe:

- Im Domänenmodus ist für remote durchgeführte Empfangsvorgänge ein MSDTC-Netzwerkzugriff (Microsoft Distributed Transaction Coordinator) erforderlich. Sie können dies mithilfe von **Komponenten hinzufügen/entfernen**aktivieren.

  ![Screenshot, der das Aktivieren des DTC-Netzwerk Zugriffs anzeigt](./media/troubleshooting-queued-messaging/enable-distributed-transaction-coordinator-access.jpg)

- Überprüfen Sie den Authentifizierungsmodus für die Kommunikation mit dem Transaktions-Manager. Wenn Sie sich im Arbeitsgruppen Modus befinden, muss "keine Authentifizierung erforderlich" ausgewählt werden. Wenn Sie sich im Domänen Modus befinden, muss die Option "gegenseitige Authentifizierung erforderlich" ausgewählt werden.

  ![Aktivieren von XA-Transaktionen](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-AFAC-75f8860d2bb0")

- Stellen Sie sicher, dass MSDTC in der Liste der Ausnahmen in den Firewalleinstellungen für die **Internet Verbindung** enthalten ist.

- Stellen Sie sicher, dass Sie Windows Vista verwenden. MSMQ unter Windows Vista unterstützt Remote transaktive Lesevorgänge. MSMQ in früheren Windows-Releases unterstützt keine remote durchgeführten Lesevorgänge.

**F:** Warum wird beim Lesen aus der Warteschlange eine Ausnahme vom Typ "Zugriff verweigert" ausgelöst, wenn der Dienst, der aus der Warteschlange liest, ein Netzwerkdienst ist, beispielsweise in einem Webhost.

**A:** Der Netzwerkdienst Lesezugriff muss der Warteschlangen-ACL hinzugefügt werden, um sicherzustellen, dass ein Netzwerkdienst aus der Warteschlange lesen kann.

**F:** Kann ich den MSMQ-Aktivierungs Dienst zum Aktivieren von Anwendungen auf der Grundlage von Nachrichten in einer Warteschlange auf einem Remote Computer verwenden?

**A:** Ja. Sie müssen dazu den MSMQ-Aktivierungsdienst als Netzwerkdienst konfigurieren und der Warteschlange auf dem Remotecomputer den Netzwerkdienstzugriff hinzufügen.

## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Verwenden von benutzerdefinierten MSMQ-Bindungen mit aktiviertem ReceiveContext

Bei Verwendung einer benutzerdefinierten MSMQ-Bindung mit aktiviertem <xref:System.ServiceModel.Channels.ReceiveContext> wird bei der Verarbeitung einer eingehenden Nachricht ein Thread Pool Thread verwendet, da Native MSMQ keine e/a-Vervollständigung für asynchrone <xref:System.ServiceModel.Channels.ReceiveContext> empfangene Vorgänge unterstützt. Dies liegt daran, dass bei der Verarbeitung einer solchen Nachricht interne Transaktionen für <xref:System.ServiceModel.Channels.ReceiveContext> verwendet werden und MSMQ die asynchrone Verarbeitung nicht unterstützt. Um dieses Problem zu umgehen, können Sie dem Endpunkt eine <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> hinzufügen, um die synchrone Verarbeitung zu erzwingen oder <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> auf 1 festzulegen.
