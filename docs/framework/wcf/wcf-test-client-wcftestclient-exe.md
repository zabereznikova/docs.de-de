---
title: WCF-Testclient (WcfTestClient.exe)
description: Erfahren Sie mehr über den WCF-Test Client, der nahtlose Dienst Tests in Kombination mit dem WCF-Dienst Host ermöglicht. Übermitteln von Client Testwerten und Anzeigen von Dienst Antworten.
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: 4f636698c538809f89ee356159839a37b73adb57
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245660"
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF-Testclient (WcfTestClient.exe)
Windows Communication Foundation (WCF)-Test Client (WcfTestClient.exe) ist ein GUI-Tool, mit dem Benutzer Testparameter eingeben, die Eingabe an den Dienst senden und die vom Dienst zurück gesendete Antwort anzeigen können. Diese Funktion bietet eine nahtlose Dienst Testfunktion, wenn Sie mit dem WCF-Dienst Host kombiniert wird.

Der WCF-Test Client (WcfTestClient.exe) befindet sich in der Regel am folgenden Speicherort: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` -Community kann je nach installierter Ebene von Visual Studio "Enterprise", "Professional" oder "Community" lauten.

## <a name="scenarios-for-using-test-client"></a>Szenarien für das Verwenden des Testclients

In den folgenden Abschnitten werden die häufigsten Szenarien erläutert, in denen Sie den WCF-Test Client verwenden können, um Ihren Entwicklungsprozess zu optimieren.

### <a name="inside-visual-studio"></a>In Visual Studio

#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>Der WCF-Diensthost startet den WCF-Testclient mit einem einzelnen Dienst.

Nachdem Sie ein neues WCF-Dienstprojekt erstellt und F5 drücken, um den Debugger zu starten, beginnt der WCF-Dienst Host mit dem Hosten des Diensts in Ihrem Projekt. Anschließend wird der WCF-Test Client geöffnet, und es wird eine Liste der in der Konfigurationsdatei definierten Dienst Endpunkte angezeigt. Sie können die Parameter testen und den Dienst aufrufen und anschließend den Vorgang wiederholen, um den Dienst kontinuierlich zu testen und zu validieren.

#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>Der WCF-Diensthost startet den WCF-Testclient mit mehreren Diensten.

Sie können auch den WCF-Test Client verwenden, um ein Dienstprojekt zu debuggen, das mehrere Dienste enthält. Wenn der WCF-Test Client geöffnet wird, durchläuft er automatisch die Liste der Dienste in Ihrem Projekt und öffnet diese zum Testen.

### <a name="outside-visual-studio"></a>Außerhalb von Visual Studio

Sie können auch den WCF-Test Client (WcfTestClient.exe) außerhalb von Visual Studio aufrufen, um einen beliebigen Dienst im Internet zu testen. Das Tool befindet sich im folgenden Verzeichnis:

`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE`(wobei die Community abhängig davon, welche Ebene von Visual Studio auf dem Computer installiert ist, eine "Enterprise", "Professional" oder "Community" sein kann)

Doppelklicken Sie zum Verwenden des Tools auf den Dateinamen, um das Tool von dessen Verzeichnis aus zu öffnen, oder starten Sie das Tool mithilfe einer Befehlszeile.

Der WCF-Test Client nimmt eine beliebige Anzahl von URIs als Befehlszeilenargumente an.  Bei diesen handelt es sich um die URIs der Dienste, die getestet werden können.

`wcfTestClient.exe URI1 URI2 …`

Nachdem das Fenster WCF-Test Client geöffnet wurde, klicken Sie auf **Datei** -> **Dienst hinzufügen**, und geben Sie die Endpunkt Adresse des Dienstanbieter ein, den Sie öffnen möchten.

## <a name="wcf-test-client-user-interface"></a>WCF-Testclient-Benutzeroberfläche

Sie können den WCF-Test Client mit einem einzelnen Dienst oder mehreren Diensten verwenden.

### <a name="service-operations"></a>Dienstoperationen

Im linken Bereich des Hauptfensters des WCF-Test Clients werden alle verfügbaren Dienste zusammen mit den jeweiligen Endpunkten und Vorgängen aufgelistet.

Durch Doppelklicken auf einen Vorgang wird dessen Inhalt im rechten Bereich auf einer neuen Registerkarte angezeigt, die mit dem Namen des Vorgangs versehen ist.

Im linken Bereich werden auch die Clientkonfigurationsdateien aufgeführt. Doppelklicken Sie auf eines der Elemente, um den Inhalt der Datei im rechten Bereich in einem neuen Fenster mit Registerkarten anzuzeigen.

### <a name="entering-test-parameters"></a>Eingeben der Testparameter

Doppelklicken Sie zur Anzeige der Testparameter auf einen Vorgang, um ihn im rechten Bereich zu öffnen. Die Parameter werden standardmäßig in der **formatierten** Ansicht angezeigt, und Sie können beliebige Werte für die Parameter eingeben, um den Dienst zu testen.

Um den XML-Code der Nachricht anzuzeigen, klicken Sie auf **XML**. Klicken Sie auf **aufrufen**, um Sie an den Dienst zu senden.

Für einen Datasetparameter klicken Sie auf **...** Schaltfläche neben **Bearbeiten..** . , um Sie in einem neuen Fenster zu bearbeiten, das das DataGrid anzeigt. Beachten Sie die Darstellung der Schaltflächen **DataSet kopieren** und **DataSet einfügen** . Wenn das Schema des DataSet-Objekts bei der ersten Bearbeitung unbekannt ist, ist das DataGrid leer. Sie müssen ein DataSet-Objekt mit dem gleichen Schema in das aktuelle Objekt im DataGrid einfügen. (Beachten Sie, dass Sie das Schema vor dem Einfügevorgang von einem anderen Speicherort kopieren müssen.) Sie können auch ein DataSet-Objekt zur späteren Verwendung kopieren, indem Sie auf die Schaltfläche **DataSet kopieren** klicken.

Die Antwort des Dienstes wird unter den Testparametern angezeigt.

> [!NOTE]
> Ist der erwartete Rückgabewert eine Zeichenfolge, wird das Ergebnis als Zeichenfolge in Anführungszeichen angezeigt, auch wenn die Eingabe selbst nicht in Anführungszeichen angegeben wurde.

Wenn Sie einen bestimmten Vorgang beim Erstellen des Dienstvertrags als einseitig festgelegt haben, wird keine Dienstantwort angezeigt. Sobald die Nachricht für die Lieferung in die Warteschlange gestellt wird, wird ein Dialogfeld angezeigt, dass die Nachricht erfolgreich gesendet wurde.

### <a name="session-support"></a>Sitzungsunterstützung

Mit dem Kontrollkästchen **neuen Proxy starten** auf der Registerkarte eines Dienst Vorgangs können Sie die Sitzungsunterstützung umschalten. Dieses Kontrollkästchen ist in der Standardeinstellung deaktiviert.

Wenn Sie Testparameter für einen bestimmten Vorgang (oder einen anderen Vorgang im gleichen Dienst Endpunkt) eingeben und mehrmals auf **aufrufen** klicken, wenn das Kontrollkästchen deaktiviert ist, wird für diese Vorgänge ein Proxy gemeinsam genutzt, und der Dienststatus wird über mehrere Vorgänge hinweg beibehalten.

Wenn das Kontrollkästchen **neuen Proxy starten** aktiviert ist, wird für jeden **Aufruf**ein neuer Proxy gestartet, das vorherige Sitzungs Szenario wurde beendet, und der Dienststatus wird zurückgesetzt.

### <a name="editing-client-configuration"></a>Bearbeiten der Clientkonfiguration

Im linken Bereich des Hauptfensters des WCF-Test Clients werden die Client Konfigurationsdateien aufgelistet. Doppelklicken Sie auf eines der Elemente, um im rechten Bereich die Inhalte der Datei anzuzeigen.

#### <a name="edit-with-service-configuration-editor"></a>Bearbeiten mit dem Service Configuration Editor

Klicken Sie im linken Bereich mit der rechten Maustaste auf **Konfigurationsdatei** , und wählen Sie das Kontextmenü **mit SvcConfigEditor bearbeiten**aus. Der Service Configuration Editor wird mit dem Clientkonfigurationsinhalt gestartet. Sie können die Konfiguration bearbeiten und innerhalb des Tools speichern.

Nach dem Speichern der Datei im Dienstkonfigurations-Editor zeigt der WCF-Test Client eine Warnmeldung an, die Sie darüber informiert, dass die Datei außerhalb von geändert wurde, und fragt, ob Sie Sie erneut laden möchten.

Wenn Sie **Ja**auswählen, werden im Konfigurations Inhalt auf der Registerkarte "Client.dll.config" die im Editor vorgenommenen Änderungen angezeigt.

Wenn Sie **Nein**auswählen, bleibt der Konfigurations Inhalt auf der Registerkarte "Client.dll.config" unverändert, und der geänderte Inhalt wird automatisch in der Quelldatei gespeichert.

#### <a name="restore-to-default-configuration"></a>Wiederherstellen der Standardkonfiguration

Wenn Sie alle Änderungen abbrechen und in der standardmäßigen Client Konfiguration wiederherstellen möchten, klicken Sie im linken Bereich mit der rechten Maustaste auf **Konfigurationsdatei** , und wählen Sie das Kontextmenü in **Standardkonfiguration wiederherstellen**aus. Der Standard Konfigurations Wert wird geladen, und der Inhalt auf der Registerkarte "Client.dll.config" wird wieder hergestellt.

#### <a name="validate-changes"></a>Überprüfen von Änderungen

Wenn gespeicherte Änderungen in den WCF-Test Client geladen werden, wird die Konfiguration auf Gültigkeit des WCF-Schemas überprüft. Sind Fehler vorhanden, wird ein Dialogfeld mit Fehlerdetails angezeigt.

Während der Proxy Generierung, Binär Kompilierung oder Dienst Aufruf werden Menü Elemente, die die Bearbeitung unterstützen (d. h. "bearbeiten...", "wiederherstellen..." usw.), deaktiviert. Der Dienst Aufruf ist auch beim Laden der aktualisierten Konfiguration in den WCF-Test Client deaktiviert.

#### <a name="persist-client-configuration"></a>Beibehalten der Clientkonfiguration

Die **Tools** -> Registerkarte Extras**Optionen** -> **Client Konfiguration** enthält die Option **Konfiguration beim Starten von Diensten immer neu generieren** , die standardmäßig aktiviert ist. Diese Option gibt an, dass jedes Mal, wenn der WCF-Test Client einen Dienst lädt, eine Konfigurationsdatei auf der Grundlage des aktuellen Dienstvertrags und der Dienst App.config Dateien erneut generiert wird.

Wenn Sie die Client Konfiguration für den WCF-Dienst bearbeitet haben und diese aktualisierte Datei immer zum Debuggen des diensdienstanbieter verwenden möchten, können Sie die Option neu **generieren** deaktivieren. Auf diese Weise können Sie, selbst wenn Sie den Dienst aktualisieren und den WCF-Test Client erneut öffnen, die Client.dll.config Datei, die Sie zuvor aktualisiert haben, anstelle eines neu generierten Dienstanbieter.

Die Konfigurationsdatei muss jedoch möglicherweise bearbeitet werden, um sie mit dem neu generierten Proxy abzustimmen. Stimmen der neu generierte Proxy und die Konfigurationsdatei aufgrund eines aktualisierten Diensts nicht überein, treten beim Aufrufen des Diensts entsprechende Fehler auf.

> [!CAUTION]
> Für den Fall, dass Sie die Clientkonfigurationsdatei geändert haben und später wieder verwenden möchten, finden Sie die Datei im folgenden Verzeichnis:
>
> \Dokumente und Einstellungen \\ [Benutzerkonto] \Eigene documents\testclientprojekte.
>
> Aktualisierte Anmeldeinformationen, die in der Clientkonfigurationsdatei gespeichert sind, sind durch die Zugriffsteuerungsliste (Access Control List, ACL) dieses Ordners geschützt.

### <a name="adding-removing-and-refreshing-services"></a>Hinzufügen, Entfernen und Aktualisieren von Diensten

#### <a name="add-service"></a>Dienst hinzufügen

Klicken Sie auf **Datei** -> **Dienst hinzufügen** , um dem WCF-Test Client einen Dienst hinzuzufügen. Geben Sie anschließend den URI (die Endpunktadresse) des hinzuzufügenden Diensts ein. Bei der Adresse des Diensts kann es sich um eine mex-Adresse oder um eine WSDL-Adresse handeln.

Sie können auch eine Liste der 10 zuletzt hinzugefügten Dienst Endpunkte im Untermenü " **zuletzt verwendete Dienste** " finden. Wenn Sie einen dieser Werte auswählen, wird der angegebene Dienst dem WCF-Test Client hinzugefügt.

Sie können auch mit der rechten Maustaste auf den Stamm der Dienststruktur **meine Dienstprojekte**klicken und **Dienst hinzufügen** auswählen, um das gleiche Ergebnis zu erzielen.

Menüelemente, die das Hinzufügen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.

#### <a name="remove-service"></a>Entfernen eines Diensts

Klicken Sie mit der rechten Maustaste auf den Dienst Stamm des zu entfernenden Dienstes, und wählen Sie **Dienst entfernen** aus, um einen Dienst vom WCF-Test Client zu entfernen.

Menüelemente, die das Entfernen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.

#### <a name="refresh-service"></a>Aktualisieren eines Diensts

Wenn an dem Dienst eine Änderung vorgenommen wird, während der WCF-Test Client ausgeführt wird und Sie sicherstellen möchten, dass die Implementierung des WCF-Test Clients für diesen Dienst auf dem neuesten Stand ist, klicken Sie mit der rechten Maustaste auf den Dienst Stamm des Dienstanbieter, und wählen Sie **Dienst aktualisieren**aus. Der Dienststatus wird nach der Aktualisierung zurückgesetzt.

Menüelemente, die das Aktualisieren eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.

## <a name="location-of-files-generated-by-the-test-client"></a>Speicherort der vom Testclient generierten Dateien

Standardmäßig speichert der WCF-Test Client generierten Client Code und die Konfigurationsdateien im Ordner "%APPDATA%\Local\temp\Test Client Projects". Dieser Ordner wird gelöscht, nachdem der WCF-Test Client beendet wurde. Wenn eine Konfigurationsdatei im WCF-Test Client geändert wird und die Option **Konfiguration beim Starten von Diensten immer neu generieren** deaktiviert ist, wird die geänderte Datei in den Ordner "cachedconfig" unter "eigene Dateien\Test Client Projects" mit einer Zuordnungs-XML-Datei (Metadata-Address-to-File-Name) als Index kopiert.

Sie können den WCF-Test Client auch in einer Befehlszeile starten, den Schalter verwenden, `/ProjectPath` um einen neuen gewünschten Pfad zum Speichern generierter Dateien anzugeben, oder den-Schalter verwenden, `/RestoreProjectPath` um den Standard Speicherort wiederherzustellen. Die Syntax lautet wie folgt:

`wcfTestClient.exe /ProjectPath [desired location]`

Beim Ausführen dieses Befehls wird der WCF-Test Client nicht geöffnet. Nur der Speicherort des Ordners wird geändert. Sie können diesen Befehl ausführen, unabhängig davon, ob der WCF-Test Client ausgeführt wird oder nicht. Der neue Speicherort wird angewendet, wenn der WCF-Test Client neu gestartet wird. Die Speicherort Informationen können in der Registrierung oder in der Datei "WcfTestClient.exe. Option" im Ordner "%APPDATA%\Local\temp\Test Client Projects" gespeichert werden.

## <a name="features-supported-by-wcf-test-client"></a>Vom WCF-Testclient unterstützte Funktionen

Im folgenden finden Sie eine Liste der Funktionen, die vom WCF-Test Client unterstützt werden:

- Dienstaufruf: Anforderung/Antwort und unidirektionale Nachricht.

- Bindungen: alle von Svcutil.exe unterstützten Bindungen.

- Sitzungssteuerung

- Nachrichtenvertrag

- XML-Serialisierung

Im folgenden finden Sie eine Liste der Funktionen, die nicht vom WCF-Test Client unterstützt werden:

- Typen: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, Typen, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren, einschließlich des zugehörigen <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attributs, sowie die Typen <xref:System.Xml.Linq.XDocument> und <xref:System.Xml.Linq.XElement> und der ADO.NET-Typ <xref:System.Data.DataTable>.

- Duplexvertrag

- Transaktion

- Sicherheit: CardSpace, Zertifikat und Benutzername/Kennwort.

- Bindungen: WSFederationbinding, beliebige Kontextbindungen und HTTPS-Bindung, WebHttpbinding (Unterstützung von JSON-Antwortnachrichten).

## <a name="closing-wcf-test-client"></a>Schließen des WCF-Testclients

Sie können den WCF-Test Client auf folgende Weise schließen:

- Klicken Sie im Menü **Datei** auf **Beenden**. Alternativ können Sie im Hauptfenster des WCF-Test Clients auf **Schließen**klicken. Beide Aktionen beenden auch den automatischen WCF-Dienst Host und beenden den Visual Studio-Debugvorgang, wenn der WCF-Test Client von Visual Studio gestartet wurde.

- Klicken Sie im Benachrichtigungsbereich mit der rechten Maustaste auf das Symbol **WCF-Dienst Host** , und klicken Sie dann auf **beenden.** Dadurch wird der WCF-Dienst-Auto-Host und der WCF-Test Client heruntergefahren und der Visual Studio-Debugprozess beendet.

## <a name="see-also"></a>Weitere Informationen

- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
