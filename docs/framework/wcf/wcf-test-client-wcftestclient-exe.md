---
title: WCF-Testclient (WcfTestClient.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
caps.latest.revision: "45"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc189ab1c68edfc41267e493a6ca6bccf9fe519a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF-Testclient (WcfTestClient.exe)
Der [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Benutzer Testparameter eingeben, die Eingabe an den Dienst senden und die zurückgesendete Antwort des Diensts anzeigen können. Zusammen mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost ermöglicht er einen problemlosen Diensttest.  
  
 Sie finden den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient ("WcfTestClient.exe") am folgenden Speicherort: C:\Programme\Microsoft Visual Studio 9.0\Common7\IDE\  
  
## <a name="scenarios-for-using-test-client"></a>Szenarien für das Verwenden des Testclients  
 In den folgenden Abschnitten werden die am häufigsten auftretenden Szenarien beschrieben, in denen Sie mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient den Entwicklungsvorgang optimieren können.  
  
### <a name="inside-visual-studio"></a>In Visual Studio  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>Der WCF-Diensthost startet den WCF-Testclient mit einem einzelnen Dienst.  
 Nachdem Sie ein neues [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstprojekt erstellt und zum Starten des Debuggers auf F5 gedrückt haben, beginnt der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost Service mit dem Hosten des Diensts in Ihrem Projekt. Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient öffnet dann eine Liste der in der Konfigurationsdatei definierten Dienstendpunkte. Sie können die Parameter testen und den Dienst aufrufen und anschließend den Vorgang wiederholen, um den Dienst kontinuierlich zu testen und zu validieren.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>Der WCF-Diensthost startet den WCF-Testclient mit mehreren Diensten.  
 Mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient können Sie auch ein Dienstprojekt debuggen, das mehrere Dienste enthält. Wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient geöffnet wird, erstellt er automatisch eine Liste der Dienste in Ihrem Projekt und öffnet sie zum Testen.  
  
### <a name="outside-visual-studio"></a>Außerhalb von Visual Studio  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) kann auch außerhalb von Visual Studio aufgerufen werden, um einen beliebigen Dienst im Internet zu testen. Das Tool befindet sich im folgenden Verzeichnis:  
  
 C:\Programme\Microsoft Visual Studio&#160;9.0\Common7\IDE\  
  
 Doppelklicken Sie zum Verwenden des Tools auf den Dateinamen, um das Tool von dessen Verzeichnis aus zu öffnen, oder starten Sie das Tool mithilfe einer Befehlszeile.  
  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient nimmt eine beliebige Anzahl von URIs als Befehlszeilenargumente an.  Bei diesen handelt es sich um die URIs der Dienste, die getestet werden können.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Nach der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Testclient-Fenster geöffnet ist, klicken Sie auf **Datei**->**Dienst hinzufügen**, und geben Sie die Endpunktadresse des Diensts, die Sie öffnen möchten.  
  
## <a name="wcf-test-client-user-interface"></a>WCF-Testclient-Benutzeroberfläche  
 Sie können den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient mit einem einzelnen Dienst oder mehreren Diensten verwenden.  
  
### <a name="service-operations"></a>Dienstvorgänge  
 Der linke Bereich im Hauptfenster des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclients enthält alle verfügbaren Dienste sowie die entsprechenden Endpunkte und Vorgänge.  
  
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
 Im linken Bereich des Hauptfensters des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclients werden die Clientkonfigurationsdateien aufgeführt. Doppelklicken Sie auf eines der Elemente, um im rechten Bereich die Inhalte der Datei anzuzeigen.  
  
#### <a name="edit-with-service-configuration-editor"></a>Bearbeiten mit dem Service Configuration Editor  
 Mit der rechten Maustaste **Datei "App.config"** im linken Bereich, und wählen Sie im Kontextmenü den Befehl **mit SvcConfigEditor bearbeiten**. Der Service Configuration Editor wird mit dem Clientkonfigurationsinhalt gestartet. Sie können die Konfiguration bearbeiten und innerhalb des Tools speichern.  
  
 Nach dem Speichern der Datei im Service Configuration Editor wird vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient eine Warnmeldung mit dem Hinweis angezeigt, dass die Datei extern geändert wurde, und gefragt, ob die Datei neu geladen werden soll.  
  
 Bei Auswahl des **Ja**, der konfigurationsinhalt auf der Registerkarte "Client.dll.config" widerspiegelt, die Sie im Editor vorgenommenen Änderungen.  
  
 Bei Auswahl des **keine**der konfigurationsinhalt auf der Registerkarte "Client.dll.config" unverändert, und der geänderte Inhalt wird automatisch in der Quelldatei gespeichert.  
  
#### <a name="restore-to-default-configuration"></a>Wiederherstellen der Standardkonfiguration  
 Sollen alle Änderungen Abbrechen und Wiederherstellen der standardmäßigen Clientkonfiguration, mit der rechten Maustaste **Datei "App.config"** im linken Bereich, und wählen Sie im Kontextmenü den Befehl **Standardkonfiguration wiederherstellen**. Der standardkonfigurationswert wird geladen und Inhalt in der Registerkarte "Client.dll.config" wird wiederhergestellt.  
  
#### <a name="validate-changes"></a>Überprüfen von Änderungen  
 Beim Laden gespeicherter Änderungen im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient wird die Konfiguration anhand des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Schemas auf Gültigkeit geprüft. Sind Fehler vorhanden, wird ein Dialogfeld mit Fehlerdetails angezeigt.  
  
 Während der Proxygenerierung, binärkompilierung oder Dienst aufrufen werden die Menüelemente, bearbeiten (d. h. "Bearbeiten...", "Wiederherzustellen...", usw.) unterstützen, deaktiviert. Beim Laden einer aktualisierten Konfiguration im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient ist auch das Aufrufen von Diensten deaktiviert.  
  
#### <a name="persist-client-configuration"></a>Beibehalten der Clientkonfiguration  
 Die **Tools**->**Optionen**->**Clientkonfiguration** Registerkarte enthält ein **immer neu generieren Konfiguration beim Starten Dienste** Option, die standardmäßig aktiviert ist. Durch diese Option wird angegeben, dass immer dann, wenn ein Dienst durch den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient geladen wird, eine Konfigurationsdatei erstellt wird, die auf der neuesten Dienstvertrags- sowie auf der neuesten App.config-Datei basiert.  
  
 Wenn Sie für die Clientkonfiguration bearbeitet haben Ihre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst und für die immer diese aktualisierte Datei verwenden, um den Dienst debuggen möchten, deaktivieren Sie die **neu generieren** Option. Dadurch wird anstelle einer neu generierten Datei, die auf dem aktualisierten Dienst basiert, immer die zuvor aktualisierte Client.dll.config-Datei verwendet. Dies ist auch dann der Fall, wenn der Dienst aktualisiert und der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient erneut geöffnet wurde.  
  
 Die Konfigurationsdatei muss jedoch möglicherweise bearbeitet werden, um sie mit dem neu generierten Proxy abzustimmen. Stimmen der neu generierte Proxy und die Konfigurationsdatei aufgrund eines aktualisierten Diensts nicht überein, treten beim Aufrufen des Diensts entsprechende Fehler auf.  
  
> [!CAUTION]
>  Für den Fall, dass Sie die Clientkonfigurationsdatei geändert haben und später wieder verwenden möchten, finden Sie die Datei im folgenden Verzeichnis:  
>   
>  \Documents and Settings\\[Benutzerkonto] \My Documents\Test Client Projects.  
>   
>  Aktualisierte Anmeldeinformationen, die in der Clientkonfigurationsdatei gespeichert sind, sind durch die Zugriffsteuerungsliste (Access Control List, ACL) dieses Ordners geschützt.  
  
### <a name="adding-removing-and-refreshing-services"></a>Hinzufügen, Entfernen und Aktualisieren von Diensten  
  
#### <a name="add-service"></a>Hinzufügen eines Diensts  
 Klicken Sie auf **Datei**->**Dienst hinzufügen** zum Hinzufügen eines Diensts zu [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Testclient. Geben Sie anschließend den URI (die Endpunktadresse) des hinzuzufügenden Diensts ein. Bei der Adresse des Diensts kann es sich um eine mex-Adresse oder um eine WSDL-Adresse handeln.  
  
 Sie erhalten auch eine Liste der 10 zuletzt hinzugefügten Dienstendpunkten in der **zuletzt verwendete Dienste** Untermenü. Wenn Sie eine dieser Optionen auswählen, wird der angegebene Dienst dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient hinzugefügt.  
  
 Sie können auch mit der rechten Maustaste den Stamm der Dienststruktur **Meine Dienstprojekte**, und wählen Sie **Dienst hinzufügen** um dasselbe Ergebnis zu erzielen.  
  
 Menüelemente, die das Hinzufügen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.  
  
#### <a name="remove-service"></a>Entfernen eines Diensts  
 Mit der rechten Maustaste in des dienststamm des Diensts entfernt werden soll, und wählen Sie **Dienst entfernen** So entfernen Sie einen Dienst aus [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Testclient.  
  
 Menüelemente, die das Entfernen eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.  
  
#### <a name="refresh-service"></a>Aktualisieren eines Diensts  
 Wenn eine Änderung, an den Dienst beim vorgenommen wird [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Testclient ausgeführt wird und Sie möchten, um sicherzustellen, dass die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] testclientimplementierung für diesen Dienst auf dem neuesten Stand ist, mit der rechten Maustaste in des dienststamm des Diensts, und wählen **aktualisieren Dienst**. Der Dienststatus wird nach der Aktualisierung zurückgesetzt.  
  
 Menüelemente, die das Aktualisieren eines Diensts unterstützen, sind während der Proxygenerierung, Binärkompilierung sowie während Dienstaufrufen deaktiviert. Auch das Aufrufen von Diensten ist deaktiviert.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>Speicherort der vom Testclient generierten Dateien  
 Standardmäßig [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Testclient generierte Clientcode- und Clientkonfigurationsdateien im Ordner "%appdata%\Local\temp\Test Client Projects". Dieser Ordner wird nach dem Schließen des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclients gelöscht. Wenn in eine Konfigurationsdatei geändert wird [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Testclient und **immer neu generieren Konfiguration beim Starten von Diensten** Option deaktiviert ist, wird die geänderte Datei in den Ordner "Cached Config" unter "Eigene Dateien\test kopiert Client Projects Documents\Test Client Projects"mit einer Zuordnung (Metadaten Adresse-zu-Dateiname) XML-Datei als Index.  
  
 Alternativ kann der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient auch von einer Befehlszeile aus gestartet werden. Verwenden Sie in diesem Fall den `/ProjectPath`-Schalter, um einen neuen Pfad zum Speichern der generierten Dateien anzugeben, oder verwenden Sie den `/RestoreProjectPath`-Schalter, um den standardmäßigen Speicherort wiederherzustellen. Die Syntax lautet wie folgt:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Dieser Befehl öffnet den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient. Nur der Speicherort des Ordners wird geändert. Dieser Befehl kann unabhängig davon ausgeführt werden, ob der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient ausgeführt wird. Der neue Speicherort wird übernommen, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient neu gestartet wird. Informationen zum Speicherort kann in der Registrierung oder in der WcfTestClient.exe.option-Datei im Ordner "%appdata%\Local\temp\Test Client Projects" gespeichert werden.  
  
## <a name="features-supported-by-wcf-test-client"></a>Vom WCF-Testclient unterstützte Funktionen  
 Die folgende Liste enthält die vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient unterstützten Features:  
  
-   Dienstaufruf: Anforderung/Antwort und unidirektionale Nachricht.  
  
-   Bindungen: alle von Svcutil.exe unterstützten Bindungen.  
  
-   Sitzungssteuerung  
  
-   Nachrichtenvertrag  
  
-   XML-Serialisierung  
  
 Die folgende Liste enthält Features, die der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient nicht unterstützt:  
  
-   Typen: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, Typen, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren, einschließlich des zugehörigen <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attributs, sowie die Typen <xref:System.Xml.Linq.XDocument> und <xref:System.Xml.Linq.XElement> und der ADO.NET-Typ <xref:System.Data.DataTable>.  
  
-   Duplexvertrag  
  
-   Transaktion  
  
-   Sicherheit: [!INCLUDE[infocard](../../../includes/infocard-md.md)], Zertifikat und Benutzername/Kennwort.  
  
-   Bindungen: WSFederationbinding, beliebige Kontextbindungen und HTTPS-Bindung, WebHttpbinding (Unterstützung von JSON-Antwortnachrichten).  
  
## <a name="closing-wcf-test-client"></a>Schließen des WCF-Testclients  
 Sie können den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient auf einem der folgenden Wege schließen:  
  
-   Auf der **Datei** Menü klicken Sie auf **beenden**. Alternativ können Sie in der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Testclient im Hauptfenster, klicken Sie auf **schließen**. Bei beiden Vorgängen wird auch der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host geschlossen und der [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Debuggingvorgang beendet, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient durch [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] gestartet wurde.  
  
-   Mit der rechten Maustaste die **WCF-Diensthost** Symbol im Infobereich, und klicken Sie dann auf **beenden.** Dadurch werden der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host und der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient geschlossen und der [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Debuggenvorgang wird beendet.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
