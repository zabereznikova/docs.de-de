---
title: "WCF-Testclient (WcfTestClient.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
caps.latest.revision: 45
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 45
---
# WCF-Testclient (WcfTestClient.exe)
Der [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Testclient \(WcfTestClient.exe\) ist ein GUI\-Tool, mit dem Benutzer Testparameter eingeben, die Eingabe an den Dienst senden und die zurückgesendete Antwort des Diensts anzeigen können.  Zusammen mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost ermöglicht er einen problemlosen Diensttest.  
  
 Sie finden den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient \("WcfTestClient.exe"\) am folgenden Speicherort: C:\\Programme\\Microsoft Visual Studio 9.0\\Common7\\IDE\\  
  
## Szenarien für das Verwenden des Testclients  
 In den folgenden Abschnitten werden die am häufigsten auftretenden Szenarien beschrieben, in denen Sie mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient den Entwicklungsvorgang optimieren können.  
  
### In Visual Studio  
  
#### Der WCF\-Diensthost startet den WCF\-Testclient mit einem einzelnen Dienst.  
 Nachdem Sie ein neues [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstprojekt erstellt und zum Starten des Debuggers auf F5 gedrückt haben, beginnt der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost Service mit dem Hosten des Diensts in Ihrem Projekt.  Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient öffnet dann eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte.  Sie können die Parameter testen und den Dienst aufrufen und anschließend den Vorgang wiederholen, um den Dienst kontinuierlich zu testen und zu validieren.  
  
#### Der WCF\-Diensthost startet den WCF\-Testclient mit mehreren Diensten.  
 Mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient können Sie auch ein Dienstprojekt debuggen, das mehrere Dienste enthält.  Wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient geöffnet wird, erstellt er automatisch eine Liste der Dienste in Ihrem Projekt und öffnet sie zum Testen.  
  
### Außerhalb von Visual Studio  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient \(WcfTestClient.exe\) kann auch außerhalb von Visual Studio aufgerufen werden, um einen beliebigen Dienst im Internet zu testen.  Das Tool befindet sich im folgenden Verzeichnis:  
  
 C:\\Programme\\Microsoft Visual Studio&\#160;9.0\\Common7\\IDE\\  
  
 Doppelklicken Sie zum Verwenden des Tools auf den Dateinamen, um das Tool von dessen Verzeichnis aus zu öffnen, oder starten Sie das Tool mithilfe einer Befehlszeile.  
  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient nimmt eine beliebige Anzahl von URIs als Befehlszeilenargumente an.  Bei diesen handelt es sich um die URIs der Dienste, die getestet werden können.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Klicken Sie im geöffneten Fenster des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclients auf **Datei**\-\>**Dienst hinzufügen**, und geben Sie die Endpunktadresse des zu öffnenden Diensts ein.  
  
## WCF\-Testclient\-Benutzeroberfläche  
 Sie können den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient mit einem einzelnen Dienst oder mehreren Diensten verwenden.  
  
### Dienstvorgänge  
 Der linke Bereich im Hauptfenster des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclients enthält alle verfügbaren Dienste sowie die entsprechenden Endpunkte und Vorgänge.  
  
 Durch Doppelklicken auf einen Vorgang wird dessen Inhalt im rechten Bereich auf einer neuen Registerkarte angezeigt, die mit dem Namen des Vorgangs versehen ist.  
  
 Im linken Bereich werden auch die Clientkonfigurationsdateien aufgeführt.  Doppelklicken Sie auf eines der Elemente, um den Inhalt der Datei im rechten Bereich in einem neuen Fenster mit Registerkarten anzuzeigen.  
  
### Eingeben der Testparameter  
 Doppelklicken Sie zur Anzeige der Testparameter auf einen Vorgang, um ihn im rechten Bereich zu öffnen.  Die Parameter werden in der Ansicht **Formatiert** angezeigt, und Sie können beliebige Werte für die Parameter eingeben, um den Dienst zu testen.  
  
 Klicken Sie auf **XML**, um den XML\-Code der Nachricht anzuzeigen.  Klicken Sie auf **Aufrufen**, um sie an den Dienst zu senden.  
  
 Klicken Sie für einen DataSet\-Parameter auf die Schaltfläche **…** neben **Bearbeiten…**, um den Parameter in einem neuen Fenster zu bearbeiten, in dem das DataGrid angezeigt wird.  Beachten Sie die Darstellung der Schaltflächen **DataSet kopieren** und **DataSet einfügen**.  Wenn das Schema des DataSet\-Objekts bei der ersten Bearbeitung unbekannt ist, ist das DataGrid leer.  Sie müssen ein DataSet\-Objekt mit dem gleichen Schema in das aktuelle Objekt im DataGrid einfügen.  \(Beachten Sie, dass Sie das Schema vor dem Einfügevorgang an anderer Stelle kopieren müssen.\) Sie können ein DataSet\-Objekt auch für die zukünftige Verwendung kopieren, indem Sie auf die Schaltfläche **DataSet kopieren** klicken.  
  
 Die Antwort des Dienstes wird unter den Testparametern angezeigt.  
  
> [!NOTE]
>  Ist der erwartete Rückgabewert eine Zeichenfolge, wird das Ergebnis als Zeichenfolge in Anführungszeichen angezeigt, auch wenn die Eingabe selbst nicht in Anführungszeichen angegeben wurde.  
  
 Wenn Sie einen bestimmten Vorgang beim Erstellen des Dienstvertrags als einseitig festgelegt haben, wird keine Dienstantwort angezeigt.  Sobald die Nachricht für die Lieferung in die Warteschlange gestellt wird, wird ein Dialogfeld angezeigt, dass die Nachricht erfolgreich gesendet wurde.  
  
### Sitzungsunterstützung  
 Das Kontrollkästchen **Neuen Proxy starten** auf der Registerkarte eines Dienstvorgangs ermöglicht das Aktivieren\/Deaktivieren der Sitzungsunterstützung.  Dieses Kontrollkästchen ist in der Standardeinstellung deaktiviert.  
  
 Wenn Sie Testparameter für einen bestimmten Vorgang \(oder für einen anderen Vorgang im gleichen Dienstendpunkt\) eingeben und mehrmals auf **Aufrufen** klicken, ohne das Kontrollkästchen zu aktivieren, wird für diese Vorgänge der gleiche Proxy verwendet, und der Dienststatus wird über mehrere Vorgänge hinweg beibehalten.  
  
 Ist das Kontrollkästchen **Neuen Proxy starten** aktiviert, wird bei jedem Klick auf **Aufrufen** ein neuer Proxy gestartet, das vorherige Sitzungsszenario wird beendet, und der Dienststatus wird zurückgesetzt.  
  
### Bearbeiten der Clientkonfiguration  
 Im linken Bereich des Hauptfensters des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclients werden die Clientkonfigurationsdateien aufgeführt.  Doppelklicken Sie auf eines der Elemente, um im rechten Bereich die Inhalte der Datei anzuzeigen.  
  
#### Bearbeiten mit dem Service Configuration Editor  
 Klicken Sie im linken Bereich mit der rechten Maustaste auf **Konfigurationsdatei**, und wählen Sie das Kontextmenü **Mit SvcConfigEditor bearbeiten** aus.  Der Service Configuration Editor wird mit dem Clientkonfigurationsinhalt gestartet.  Sie können die Konfiguration bearbeiten und innerhalb des Tools speichern.  
  
 Nach dem Speichern der Datei im Service Configuration Editor wird vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient eine Warnmeldung mit dem Hinweis angezeigt, dass die Datei extern geändert wurde, und gefragt, ob die Datei neu geladen werden soll.  
  
 Bei Auswahl von **Ja** sind die im Editor vorgenommenen Änderungen im Konfigurationsinhalt auf der Registerkarte "Client.dll.config" enthalten.  
  
 Bei Auswahl von **Nein** bleibt der Konfigurationsinhalt auf der Registerkarte "Client.dll.config" unverändert, und der geänderte Inhalt wird automatisch in der Quelldatei gespeichert.  
  
#### Wiederherstellen der Standardkonfiguration  
 Klicken Sie zum Verwerfen aller Änderungen und zum Wiederherstellen der standardmäßigen Clientkonfiguration im linken Bereich mit der rechten Maustaste auf **Konfigurationsdatei**, und wählen Sie das Kontextmenü **Standardkonfiguration wiederherstellen** aus.  Der Standardkonfigurationswert wird geladen, und der Inhalt der Registerkarte "Client.dll.config" wird wiederhergestellt.  
  
#### Überprüfen von Änderungen  
 Beim Laden gespeicherter Änderungen im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient wird die Konfiguration anhand des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Schemas auf Gültigkeit geprüft.  Sind Fehler vorhanden, wird ein Dialogfeld mit Fehlerdetails angezeigt.  
  
 Menüelemente, die Bearbeitungsfunktionen \(also "Bearbeiten", "Wiederherstellen" usw.\) unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert.  Beim Laden einer aktualisierten Konfiguration im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient ist auch das Aufrufen von Diensten deaktiviert.  
  
#### Beibehalten der Clientkonfiguration  
 Auf der Registerkarte **Clientkonfiguration** \(unter **Tools**\-\>**Optionen**\) befindet sich die standardmäßig aktivierte Option **Konfiguration beim Starten von Diensten immer neu generieren**.  Durch diese Option wird angegeben, dass immer dann, wenn ein Dienst durch den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient geladen wird, eine Konfigurationsdatei erstellt wird, die auf der neuesten Dienstvertrags\- sowie auf der neuesten App.config\-Datei basiert.  
  
 Deaktivieren Sie die Option für dieNeugenerierung, wenn Sie die Clientkonfiguration für Ihren [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst geändert haben und zum Debuggen des Diensts immer diese aktualisierte Datei verwenden möchten.  Dadurch wird anstelle einer neu generierten Datei, die auf dem aktualisierten Dienst basiert, immer die zuvor aktualisierte Client.dll.config\-Datei verwendet. Dies ist auch dann der Fall, wenn der Dienst aktualisiert und der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient erneut geöffnet wurde.  
  
 Die Konfigurationsdatei muss jedoch möglicherweise bearbeitet werden, um sie mit dem neu generierten Proxy abzustimmen.  Stimmen der neu generierte Proxy und die Konfigurationsdatei aufgrund eines aktualisierten Diensts nicht überein, treten beim Aufrufen des Diensts entsprechende Fehler auf.  
  
> [!CAUTION]
>  Für den Fall, dass Sie die Clientkonfigurationsdatei geändert haben und später wieder verwenden möchten, finden Sie die Datei im folgenden Verzeichnis:  
>   
>  \\Dokumente und Einstellungen\\\[Benutzerkonto\]\\Eigene Dateien\\Test Client Projects.  
>   
>  Aktualisierte Anmeldeinformationen, die in der Clientkonfigurationsdatei gespeichert sind, sind durch die Zugriffsteuerungsliste \(Access Control List, ACL\) dieses Ordners geschützt.  
  
### Hinzufügen, Entfernen und Aktualisieren von Diensten  
  
#### Hinzufügen eines Diensts  
 Klicken Sie auf **Datei**\-\>**Dienst hinzufügen**, um dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient einen Dienst hinzuzufügen.  Geben Sie anschließend den URI \(die Endpunktadresse\) des hinzuzufügenden Diensts ein.  Bei der Adresse des Diensts kann es sich um eine mex\-Adresse oder um eine WSDL\-Adresse handeln.  
  
 Im Untermenü **Zuletzt verwendete Dienste** steht eine Liste mit den zehn zuletzt hinzugefügten Dienstendpunkten zur Verfügung.  Wenn Sie eine dieser Optionen auswählen, wird der angegebene Dienst dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient hinzugefügt.  
  
 Das gleiche Ergebnis erzielen Sie, wenn Sie mit der rechten Maustaste auf den Stamm der Dienststruktur **Meine Dienstprojekte** klicken und anschließend die Option **Dienst hinzufügen** auswählen.  
  
 Menüelemente, die das Hinzufügen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert.  Auch das Aufrufen von Diensten ist deaktiviert.  
  
#### Entfernen eines Diensts  
 Klicken Sie mit der rechten Maustaste auf den Dienstknoten des zu entfernenden Diensts, und wählen Sie die Option **Dienst entfernen** aus, um einen Dienst aus dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient zu entfernen.  
  
 Menüelemente, die das Entfernen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert.  Auch das Aufrufen von Diensten ist deaktiviert.  
  
#### Aktualisieren eines Diensts  
 Wenn eine Änderung an einem Dienst vorgenommen wird, während der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient ausgeführt wird, und Sie sicherstellen möchten, dass die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclientimplementierung für diesen Dienst auf dem neuesten Stand ist, klicken Sie mit der rechten Maustaste auf den Dienststamm des Diensts, und wählen Sie die Option **Dienst aktualisieren** aus.  Der Dienststatus wird nach der Aktualisierung zurückgesetzt.  
  
 Menüelemente, die das Aktualisieren eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert.  Auch das Aufrufen von Diensten ist deaktiviert.  
  
## Speicherort der vom Testclient generierten Dateien  
 Standardmäßig werden vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient generierte Clientcode\- und Clientkonfigurationsdateien im Ordner"%appdata%\\Local\\temp\\Test Client Projects" gespeichert.  Dieser Ordner wird nach dem Schließen des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclients gelöscht.  Wird im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient eine Konfigurationsdatei geändert, während die Option **Konfiguration beim Starten von Diensten immer neu generieren** deaktiviert ist, wird die geänderte Datei unter "Eigene Dateien\\Test Client Projects Documents\\Test Client Projects" mit einer als Index fungierenden Zuordnungs\-XML\-Datei \(Metadatenadresse zu Dateiname\) in den Ordner "Cached Config" kopiert.  
  
 Alternativ kann der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient auch von einer Befehlszeile aus gestartet werden. Verwenden Sie in diesem Fall den `/ProjectPath`\-Schalter, um einen neuen Pfad zum Speichern der generierten Dateien anzugeben, oder verwenden Sie den `/RestoreProjectPath`\-Schalter, um den standardmäßigen Speicherort wiederherzustellen.  Die Syntax lautet wie folgt:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Dieser Befehl öffnet den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient.  Nur der Speicherort des Ordners wird geändert.  Dieser Befehl kann unabhängig davon ausgeführt werden, ob der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient ausgeführt wird.  Der neue Speicherort wird übernommen, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient neu gestartet wird.  Die Informationen zum Speicherort können in der Registrierung oder in der WcfTestClient.exe.option\-Datei \(im Ordner "%appdata%\\Local\\temp\\Test Client Projects"\) gespeichert werden.  
  
## Vom WCF\-Testclient unterstützte Funktionen  
 Die folgende Liste enthält die vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient unterstützten Features:  
  
-   Dienstaufruf: Anforderung\/Antwort und unidirektionale Nachricht.  
  
-   Bindungen: alle von Svcutil.exe unterstützten Bindungen.  
  
-   Sitzungssteuerung  
  
-   Nachrichtenvertrag  
  
-   XML\-Serialisierung  
  
 Die folgende Liste enthält Features, die der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient nicht unterstützt:  
  
-   Typen: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, Typen, die die <xref:System.Xml.Serialization.IXmlSerializable>\-Schnittstelle implementieren, einschließlich des zugehörigen <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>\-Attributs, sowie die Typen <xref:System.Xml.Linq.XDocument> und <xref:System.Xml.Linq.XElement> und der ADO.NET\-Typ <xref:System.Data.DataTable>.  
  
-   Duplexvertrag  
  
-   Transaktion  
  
-   Sicherheit: [!INCLUDE[infocard](../../../includes/infocard-md.md)], Zertifikat und Benutzername\/Kennwort.  
  
-   Bindungen: WSFederationbinding, beliebige Kontextbindungen und HTTPS\-Bindung, WebHttpbinding \(Unterstützung von JSON\-Antwortnachrichten\).  
  
## Schließen des WCF\-Testclients  
 Sie können den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient auf einem der folgenden Wege schließen:  
  
-   Klicken Sie im Menü **Datei** auf **Beenden**.  Klicken Sie anderenfalls im Hauptfenster des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclients auf **Schließen**.  Bei beiden Vorgängen wird auch der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst\-Auto\-Host geschlossen und der [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\-Debuggingvorgang beendet, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient durch [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] gestartet wurde.  
  
-   Klicken Sie mit der rechten Maustaste auf das Symbol **WCF\-Diensthost** im Benachrichtigungsbereich, und wählen Sie dann **Beenden**. Dadurch werden der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst\-Auto\-Host und der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient geschlossen und der [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\-Debuggenvorgang wird beendet.  
  
## Siehe auch  
 [WCF\-Diensthost \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)