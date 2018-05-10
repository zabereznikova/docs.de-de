---
title: WCF-Testclient (WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: 78be40268b46c4c85ee034db67d67ee0fbf2158f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF-Testclient (WcfTestClient.exe)
Windows Communication Foundation (WCF)-Testclient (WcfTestClient.exe) ist ein GUI-Tool, das ermöglicht Benutzern die Eingabe Testparameter, die Eingabe an den Dienst senden, und zeigen die Antwort, die der Dienst zurücksendet. Es bietet eine nahtlose diensttest mit WCF-Diensthost kombiniert.  
  
 Finden Sie in der Regel die WCF-Testclient (WcfTestClient.exe) an folgendem Speicherort: C:\Program Files (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE - Community ist möglicherweise eine der "Enterprise", "Professional" oder "Community" abhängig von der Ebene von Visual Studio installiert ist.
  
## <a name="scenarios-for-using-test-client"></a>Szenarien für das Verwenden des Testclients  
 Den folgenden Abschnitten werden die häufigsten Szenarien, in denen Sie WCF-Testclient verwenden können, um Ihren Entwicklungsprozess zu optimieren.  
  
### <a name="inside-visual-studio"></a>In Visual Studio  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>Der WCF-Diensthost startet den WCF-Testclient mit einem einzelnen Dienst.  
 Nachdem Sie ein neues Projekt für die WCF-Dienst erstellen, und drücken Sie F5, um den Debugger zu starten, startet den WCF-Diensthost zum Hosten des Diensts in Ihrem Projekt. Klicken Sie dann WCF-Testclient geöffnet und zeigt eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte. Sie können die Parameter testen und den Dienst aufrufen und anschließend den Vorgang wiederholen, um den Dienst kontinuierlich zu testen und zu validieren.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>Der WCF-Diensthost startet den WCF-Testclient mit mehreren Diensten.  
 WCF-Testclient können auch ein Dienstprojekt Debuggen, die mehrere Dienste enthält. Wenn WCF-Testclient geöffnet wird, durchläuft die Liste der Dienste in Ihrem Projekt wird automatisch an und öffnet sie zum Testen.  
  
### <a name="outside-visual-studio"></a>Außerhalb von Visual Studio  
 Sie können auch die WCF-Testclient (WcfTestClient.exe) außerhalb von Visual Studio So testen Sie einen beliebigen Dienst im Internet aufrufen. Das Tool befindet sich im folgenden Verzeichnis:  
  
 C:\Programme\Microsoft Visual Studio&#160;9.0\Common7\IDE\  
  
 Doppelklicken Sie zum Verwenden des Tools auf den Dateinamen, um das Tool von dessen Verzeichnis aus zu öffnen, oder starten Sie das Tool mithilfe einer Befehlszeile.  
  
 WCF-Testclient nimmt eine beliebige Anzahl von URIs als Befehlszeilenargumente an.  Bei diesen handelt es sich um die URIs der Dienste, die getestet werden können.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Nachdem das Fenster des WCF-Testclient geöffnet wird, klicken Sie auf **Datei**->**Dienst hinzufügen**, und geben Sie die Endpunktadresse des Diensts, die Sie öffnen möchten.  
  
## <a name="wcf-test-client-user-interface"></a>WCF-Testclient-Benutzeroberfläche  
 Sie können WCF-Testclient mit einem einzelnen Dienst oder mehrere Dienste verwenden.  
  
### <a name="service-operations"></a>Dienstvorgänge  
 Linke Bereich des Hauptfensters WCF-Testclient Listet alle verfügbaren Dienste sowie die entsprechenden Endpunkte und Vorgänge.  
  
 Durch Doppelklicken auf einen Vorgang wird dessen Inhalt im rechten Bereich auf einer neuen Registerkarte angezeigt, die mit dem Namen des Vorgangs versehen ist.  
  
 Im linken Bereich werden auch die Clientkonfigurationsdateien aufgeführt. Doppelklicken Sie auf eines der Elemente, um den Inhalt der Datei im rechten Bereich in einem neuen Fenster mit Registerkarten anzuzeigen.  
  
### <a name="entering-test-parameters"></a>Eingeben der Testparameter  
 Doppelklicken Sie zur Anzeige der Testparameter auf einen Vorgang, um ihn im rechten Bereich zu öffnen. Die Parameter werden im gezeigten **formatiert** Ansicht standardmäßig, und Sie können beliebige Werte für die Parameter für den Dienst zu testen eingeben.  
  
 Um die Nachricht XML anzuzeigen, klicken Sie auf **XML**. Um sie an den Dienst zu senden, klicken Sie auf **Invoke**.  
  
 Für einen datasetparameter, klicken Sie auf der **...** neben **bearbeiten...** So bearbeiten Sie es in einem neuen Fenster, dem das DataGrid angezeigt. Beachten Sie die Darstellung der **DataSet kopieren** und **DataSet einfügen** Schaltflächen. Wenn das Schema des DataSet-Objekts bei der ersten Bearbeitung unbekannt ist, ist das DataGrid leer. Sie müssen ein DataSet-Objekt mit dem gleichen Schema in das aktuelle Objekt im DataGrid einfügen. (Beachten Sie, dass Sie das Schema vor dem Einfügevorgang an anderer Stelle kopieren müssen.) Sie können auch ein Dataset-Objekt für die zukünftige Verwendung kopieren, indem Sie auf die **DataSet kopieren** Schaltfläche.  
  
 Die Antwort des Dienstes wird unter den Testparametern angezeigt.  
  
> [!NOTE]
>  Ist der erwartete Rückgabewert eine Zeichenfolge, wird das Ergebnis als Zeichenfolge in Anführungszeichen angezeigt, auch wenn die Eingabe selbst nicht in Anführungszeichen angegeben wurde.  
  
 Wenn Sie einen bestimmten Vorgang beim Erstellen des Dienstvertrags als einseitig festgelegt haben, wird keine Dienstantwort angezeigt. Sobald die Nachricht für die Lieferung in die Warteschlange gestellt wird, wird ein Dialogfeld angezeigt, dass die Nachricht erfolgreich gesendet wurde.  
  
### <a name="session-support"></a>Sitzungsunterstützung  
 Die **neuen Proxy starten** Kontrollkästchen in einem Dienstvorgang Registerkarte ermöglicht es Ihnen sitzungsunterstützung. Dieses Kontrollkästchen ist in der Standardeinstellung deaktiviert.  
  
 Wenn Sie Testparameter für einen bestimmten Vorgang (oder ein anderer Vorgang im gleichen Dienstendpunkt) eingeben, und klicken Sie auf **Invoke** mehrmals mit dem das Kontrollkästchen deaktiviert ist, diese Vorgänge gleiche Proxy und der Dienststatus über mehrere Vorgänge hinweg beibehalten.  
  
 Wenn die **neuen Proxy starten** das Kontrollkästchen aktiviert ist, wird ein neuer Proxy gestartet für jede **Invoke**, das vorherige sitzungsszenario wird beendet, und der Dienststatus wird zurückgesetzt.  
  
### <a name="editing-client-configuration"></a>Bearbeiten der Clientkonfiguration  
 Linke Bereich des Hauptfensters WCF-Testclient Clientkonfigurationsdateien aufgeführt. Doppelklicken Sie auf eines der Elemente, um im rechten Bereich die Inhalte der Datei anzuzeigen.  
  
#### <a name="edit-with-service-configuration-editor"></a>Bearbeiten mit dem Service Configuration Editor  
 Mit der rechten Maustaste **Datei "App.config"** im linken Bereich, und wählen Sie im Kontextmenü den Befehl **mit SvcConfigEditor bearbeiten**. Der Service Configuration Editor wird mit dem Clientkonfigurationsinhalt gestartet. Sie können die Konfiguration bearbeiten und innerhalb des Tools speichern.  
  
 Nach dem Speichern der Datei im Dienstkonfigurations-Editor zeigt die WCF-Testclient eine Warnmeldung aus, um Sie zu informieren, die die Datei extern geändert wurde und Sie werden gefragt, ob Sie sie erneut laden möchten.  
  
 Bei Auswahl des **Ja**, der konfigurationsinhalt auf der Registerkarte "Client.dll.config" widerspiegelt, die Sie im Editor vorgenommenen Änderungen.  
  
 Bei Auswahl des **keine**der konfigurationsinhalt auf der Registerkarte "Client.dll.config" unverändert, und der geänderte Inhalt wird automatisch in der Quelldatei gespeichert.  
  
#### <a name="restore-to-default-configuration"></a>Wiederherstellen der Standardkonfiguration  
 Sollen alle Änderungen Abbrechen und Wiederherstellen der standardmäßigen Clientkonfiguration, mit der rechten Maustaste **Datei "App.config"** im linken Bereich, und wählen Sie im Kontextmenü den Befehl **Standardkonfiguration wiederherstellen**. Der standardkonfigurationswert wird geladen und Inhalt in der Registerkarte "Client.dll.config" wird wiederhergestellt.  
  
#### <a name="validate-changes"></a>Überprüfen von Änderungen  
 Wenn die Änderungen gespeicherte in WCF-Testclient geladen werden, wird die Konfiguration auf Gültigkeit für WCF-Schema überprüft. Sind Fehler vorhanden, wird ein Dialogfeld mit Fehlerdetails angezeigt.  
  
 Während der Proxygenerierung, binärkompilierung oder Dienst aufrufen werden die Menüelemente, bearbeiten (d. h. "Bearbeiten...", "Wiederherzustellen...", usw.) unterstützen, deaktiviert. Aufrufen von Diensten ist auch deaktiviert werden, wenn laden Configuration auf WCF-Testclient aktualisiert.  
  
#### <a name="persist-client-configuration"></a>Beibehalten der Clientkonfiguration  
 Die **Tools**->**Optionen**->**Clientkonfiguration** Registerkarte enthält ein **immer neu generieren Konfiguration beim Starten Dienste** Option, die standardmäßig aktiviert ist. Diese Option gibt an, dass jedes Mal, wenn einen Dienst von WCF-Testclient geladen wird, eine Konfigurationsdatei, die basierend auf den neuesten Dienstvertrag und die "App.config" Dienstdateien erneut generiert.  
  
 Wenn Sie die Clientkonfiguration für den WCF-Dienst bearbeitet haben und immer diese aktualisierte Datei verwenden, um den Dienst zu debuggen, deaktivieren Sie möchten die **Regenerieren** Option. Selbst wenn Sie den Dienst zu aktualisieren und erneut WCF-Testclient öffnen, ist die Client.dll.config-Datei auf diese Weise, die Sie zuvor anstelle einer neu aktualisiert eine auf dem aktualisierten Dienst basierend.  
  
 Die Konfigurationsdatei muss jedoch möglicherweise bearbeitet werden, um sie mit dem neu generierten Proxy abzustimmen. Stimmen der neu generierte Proxy und die Konfigurationsdatei aufgrund eines aktualisierten Diensts nicht überein, treten beim Aufrufen des Diensts entsprechende Fehler auf.  
  
> [!CAUTION]
>  Für den Fall, dass Sie die Clientkonfigurationsdatei geändert haben und später wieder verwenden möchten, finden Sie die Datei im folgenden Verzeichnis:  
>   
>  \Documents and Settings\\[Benutzerkonto] \My Documents\Test Client Projects.  
>   
>  Aktualisierte Anmeldeinformationen, die in der Clientkonfigurationsdatei gespeichert sind, sind durch die Zugriffsteuerungsliste (Access Control List, ACL) dieses Ordners geschützt.  
  
### <a name="adding-removing-and-refreshing-services"></a>Hinzufügen, Entfernen und Aktualisieren von Diensten  
  
#### <a name="add-service"></a>Hinzufügen eines Diensts  
 Klicken Sie auf **Datei**->**Dienst hinzufügen** WCF-Testclient einen Dienst hinzu. Geben Sie anschließend den URI (die Endpunktadresse) des hinzuzufügenden Diensts ein. Bei der Adresse des Diensts kann es sich um eine mex-Adresse oder um eine WSDL-Adresse handeln.  
  
 Sie erhalten auch eine Liste der 10 zuletzt hinzugefügten Dienstendpunkten in der **zuletzt verwendete Dienste** Untermenü. Wenn Sie eine dieser Optionen auswählen, wird der angegebene Dienst WCF-Testclient hinzugefügt.  
  
 Sie können auch mit der rechten Maustaste den Stamm der Dienststruktur **Meine Dienstprojekte**, und wählen Sie **Dienst hinzufügen** um dasselbe Ergebnis zu erzielen.  
  
 Menüelemente, die das Hinzufügen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.  
  
#### <a name="remove-service"></a>Entfernen eines Diensts  
 Mit der rechten Maustaste in des dienststamm des Diensts entfernt werden soll, und wählen Sie **Dienst entfernen** an einen Dienst vom WCF-Testclient zu entfernen.  
  
 Menüelemente, die das Entfernen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.  
  
#### <a name="refresh-service"></a>Aktualisieren eines Diensts  
 Wenn eine Änderung an den Dienst vorgenommen wird während WCF-Testclient ausgeführt wird und Sie sicherstellen möchten, dass die WCF-Testclient-Implementierung für diesen Dienst auf dem neuesten Stand ist, mit der rechten Maustaste des dienststamm des Diensts, und wählen **Dienst aktualisieren**. Der Dienststatus wird nach der Aktualisierung zurückgesetzt.  
  
 Menüelemente, die das Aktualisieren eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>Speicherort der vom Testclient generierten Dateien  
 Standardmäßig generiert die WCF-Testclient Client Clientcode- und Clientkonfigurationsdateien im Ordner "%appdata%\Local\temp\Test Client Projects". Dieser Ordner wird gelöscht, nachdem WCF-Testclient beendet wird. Wenn im WCF-Testclient eine Konfigurationsdatei geändert wird und die **immer neu generieren Konfiguration beim Starten von Diensten** Option deaktiviert ist, wird die geänderte Datei in den Ordner "Cached Config" unter "Eigene Dateien\test Client Projects kopiert Dateien\test Client Projects"mit einer Zuordnung (Metadaten Adresse-zu-Dateiname) XML-Datei als Index.  
  
 Sie können die WCF-Testclient auch starten, in einer Befehlszeile verwenden die `/ProjectPath` Schalter, um einen neuen Pfad zum Speichern der generierten Dateien anzugeben, oder verwenden Sie die `/RestoreProjectPath` Schalter, um den standardmäßigen Speicherort wiederherzustellen. Die Syntax lautet wie folgt:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Mit diesem Befehl wird die WCF-Testclient nicht geöffnet. Nur der Speicherort des Ordners wird geändert. Sie können diesen Befehl ausführen, ob WCF-Testclient oder nicht ausgeführt wird. Der neue Speicherort wird angewendet, wenn WCF-Testclient neu gestartet wird. Informationen zum Speicherort kann in der Registrierung oder in der WcfTestClient.exe.option-Datei im Ordner "%appdata%\Local\temp\Test Client Projects" gespeichert werden.  
  
## <a name="features-supported-by-wcf-test-client"></a>Vom WCF-Testclient unterstützte Funktionen  
 Im folgenden finden eine Liste der vom WCF-Testclient unterstützte Funktionen:  
  
-   Dienstaufruf: Anforderung/Antwort und unidirektionale Nachricht.  
  
-   Bindungen: alle von Svcutil.exe unterstützten Bindungen.  
  
-   Sitzungssteuerung  
  
-   Nachrichtenvertrag  
  
-   XML-Serialisierung  
  
 Im folgenden finden eine Liste der Funktionen von WCF-Testclient nicht unterstützt:  
  
-   Typen: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, Typen, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren, einschließlich des zugehörigen <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attributs, sowie die Typen <xref:System.Xml.Linq.XDocument> und <xref:System.Xml.Linq.XElement> und der ADO.NET-Typ <xref:System.Data.DataTable>.  
  
-   Duplexvertrag  
  
-   Transaktion  
  
-   Sicherheit: [!INCLUDE[infocard](../../../includes/infocard-md.md)], Zertifikat und Benutzername/Kennwort.  
  
-   Bindungen: WSFederationbinding, beliebige Kontextbindungen und HTTPS-Bindung, WebHttpbinding (Unterstützung von JSON-Antwortnachrichten).  
  
## <a name="closing-wcf-test-client"></a>Schließen des WCF-Testclients  
 Sie können WCF-Testclient auf folgende Weise schließen:  
  
-   Auf der **Datei** Menü klicken Sie auf **beenden**. Alternativ klicken Sie im Hauptfenster von WCF-Testclient auf **schließen**. Sowohl dieser Aktionen auch WCF-Dienst-Auto-Host heruntergefahren und der Visual Studio-debugging-Prozess zu beenden, wenn WCF-Testclient von Visual Studio gestartet wurde.  
  
-   Mit der rechten Maustaste die **WCF-Diensthost** Symbol im Infobereich, und klicken Sie dann auf **beenden.** Diese WCF-Dienst-Auto-Host und WCF-Testclient heruntergefahren, und die Visual Studio-debuggingvorgang beendet.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
