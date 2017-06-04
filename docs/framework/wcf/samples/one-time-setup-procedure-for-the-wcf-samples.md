---
title: "Einmaliges Setupverfahren f&#252;r Windows Communication Foundation-Beispiele | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
caps.latest.revision: 83
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 83
---
# Einmaliges Setupverfahren f&#252;r Windows Communication Foundation-Beispiele
Die meisten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Beispiele werden in Internetinformationsdienste \(IIS\) gehostet und von einem gemeinsamen virtuellen Verzeichnis ausgeführt.In diesem einmaligen Setupverfahren wird ein Ordner auf dem Datenträger erstellt. Außerdem wird in IIS das virtuelle Verzeichnis **ServiceModelSamples** hinzugefügt.  
  
 Das virtuelle Verzeichnis **ServiceModelSamples** wird zum Erstellen und Ausführen aller Beispiele verwendet, in denen ein von IIS gehosteter Dienst verwendet wird.Dies ist das einzige virtuelle Verzeichnis, das zum Ausführen der Beispiele erforderlich ist.Durch die Erstellung eines Beispiels werden alle zuvor bereitgestellten Dienste in diesem virtuellen Verzeichnis ersetzt. Nur das zuletzt erstellte Beispiel wird bereitgestellt und ist dann in diesem virtuellen Verzeichnis verfügbar.  
  
> [!NOTE]
>  Sie müssen alle Befehle unter einem lokalen Administratorkonto ausführen.Wenn Sie mit Windows 7, [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] oder Windows Server 2008 R2 arbeiten, müssen Sie außerdem die Eingabeaufforderung mit erweiterten Berechtigungen ausführen.Klicken Sie hierzu mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung, und klicken Sie dann auf **Als Administrator ausführen**.Alle Befehle in diesem Thema müssen an einer Eingabeaufforderung ausgeführt werden, die über die richtigen Pfadeinstellungen verfügt.Dies kann am einfachsten sichergestellt werden, wenn Sie die Visual Studio\-Eingabeaufforderung verwenden.Klicken Sie zum Öffnen dieser Eingabeaufforderung auf **Start** und auf **Alle Programme**. Führen Sie einen Bildlauf nach unten bis **Visual Studio 2010** aus, wählen Sie **Visual Studio Tools** aus, und klicken Sie mit der rechten Maustaste auf **Visual Studio\-Eingabeaufforderung \(2010\)**. Klicken Sie dann auf **Als Administrator ausführen**.Wenn Sie eine Visual Studio Express Edition installiert haben, ist diese Eingabeaufforderung nicht verfügbar. In diesem Fall müssen Sie dem Systempfad "C:\\Windows\\Microsoft.Net\\Framework\\v4.0" hinzufügen.  
  
### Einmaliges Setupverfahren für WCF\-Beispiele  
  
1.  Stellen Sie sicher, dass [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] eingerichtet ist.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Einrichten von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] erhalten Sie unter [Hostinganweisungen des Internetinformationsdiensts](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md).  
  
2.  Stellen Sie sicher, dass [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] installiert ist.Durchsuchen Sie das folgende Verzeichnis nach v4.0 \(oder höher\): **\\Windows\\Microsoft.NET\\Framework**  
  
3.  Wenn [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] nicht installiert ist und das Betriebssystem nicht Windows Server 2008 SP2 oder höher ist, installieren Sie den [Hotfix 251798](http://go.microsoft.com/fwlink/?LinkId=184693).  
  
4.  Führen Sie die folgenden Befehle durch.Weitere Informationen dazu, warum diese Befehle ausgeführt werden müssen, finden Sie unter [IIS Hosted Service Fails](http://msdn.microsoft.com/de-de/ee5499fc-1b10-4cda-a9b1-13dba70f05f8).  
  
    > [!WARNING]
    >  Wenn IIS neu installiert wird, müssen die folgenden Befehle noch einmal ausgeführt werden.  
  
    ```  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r  
    ```  
  
    > [!WARNING]
    >  Wenn der Befehl `aspnet_regiis –i –enable` ausgeführt wird, wird der Standardanwendungspool mit [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] ausgeführt. Dadurch kann es zu Inkompatibilitätsproblemen bei anderen Anwendungen auf demselben Computer kommen.  
  
5.  Folgen Sie den [Firewall\-Anweisungen](../../../../docs/framework/wcf/samples/firewall-instructions.md) zum Aktivieren der in den Beispielen verwendeten Anschlüsse.  
  
6.  Suchen Sie nach dem folgenden Standardverzeichnis: \<Installationslaufwerk\>:**\\WF\_WCF\_Samples**.Wenn die Beispiele bereits installiert wurden, ist dies das Standardverzeichnis.  
  
7.  Wenn die Beispiele nicht installiert sind, installieren Sie sie von der Beispiel\-Downloadseite für [Visual C\#](http://go.microsoft.com/fwlink/?LinkId=190939) bzw. [Visual Basic](http://go.microsoft.com/fwlink/?LinkID=193373).  
  
8.  Wechseln Sie nach dem Installieren der Beispiele zu folgendem Verzeichnis: \<Installationslaufwerk\>:**\\WF\_WCF\_Samples\\WCF\\Setup\\**  
  
9. Führen Sie die Batchdatei **Setupvroot.bat** aus.Die folgenden Schritte werden ausgeführt:  
  
    -   In IIS wird ein virtuelles Verzeichnis mit dem Namen ServiceModelSamples erstellt.  
  
    -   Es werden die neuen Datenträgerverzeichnisse %SystemDrive%\\Inetpub\\wwwroot\\ServiceModelSamples und %SystemDrive%\\Inetpub\\wwwroot\\ServiceModelSamples\\bin erstellt.  
  
     Wenn Sie diese Verzeichnisse manuell einrichten möchten, finden Sie Informationen unter [Anleitung zum Einrichten eines virtuellen Verzeichnisses](../../../../docs/framework/wcf/samples/virtual-directory-setup-instructions.md).Um alle in diesem Schritt vorgenommenen Änderungen rückgängig zu machen, führen Sie cleanupvroot.bat aus, sobald die Beispiele nicht mehr benötigt werden.  
  
    > [!NOTE]
    >  Diese Prozedur muss nur einmal auf einem Computer ausgeführt werden, es sei denn, cleanupvroot.bat wird ausgeführt.  
  
10. Sie müssen dem Konto, unter dem Sie die Beispiele erstellen, und dem Netzwerkdienstbenutzer die Berechtigung zum Ändern von %SystemDrive%\\inetpub\\wwwroot zuweisen.Beim Erstellen wird bei einigen im Internet gehosteten Beispielen möglicherweise versucht, die kompilierten Binärdateien an den oben genannten Speicherort zu kopieren. Wenn Sie nicht die entsprechenden Berechtigungen festgelegt haben, können die Beispiele nicht erstellt werden.Sie können die Berechtigungen aber auch unverändert lassen und die SDK\-Eingabeaufforderung oder die Visual Studio\-Eingabeaufforderung \(2012\) als Administrator ausführen, oder Sie können die Beispiele als Administrator in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] erstellen.  
  
    > [!NOTE]
    >  Wenn dieser Schritt nicht ausgeführt wird, lässt sich keines der von IIS gehosteten Beispiele erstellen.Legen Sie die Berechtigungen unbedingt richtig fest, oder führen Sie die SDK\-Eingabeaufforderung und Visual Studio\-Eingabeaufforderung \(2012\) als Administrator aus.  
  
11. Erstellen Sie das Verzeichnis C:\\logs auf dem Computer. Möglicherweise wird es bei einigen Beispielen vorausgesetzt.Stellen Sie sicher, dass das entsprechende Konto Schreibzugriff auf diesen Ordner hat.Unter Windows 7, [!INCLUDE[wv](../../../../includes/wv-md.md)] und Windows Server 2008 R2 ist dies das Konto **Netzwerkdienst**.Unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)] ist es das Konto NT\-Autorität\\Netzwerkdienst.Unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lautet das Konto ASPNET.  
  
12. Führen Sie die Datei Setupcerttool.bat aus.Diese Datei befindet sich im Ordner \<Installationspfad\>\\WF\_WCF\_Samples\\WCF\\Setup\\.Mit diesem Skript werden folgende Aufgaben ausgeführt:  
  
    -   Erstellen des Tools FindPrivateKey  
  
    -   Erstellen eines Verzeichnisses mit dem Namen %ProgramFiles%\\ServiceModelSampleTools  
  
    -   Kopieren Sie das neue Tool FindPrivateKey in dieses Verzeichnis.  
  
     Dieses Tool ist für Beispiele erforderlich, die Zertifikate verwenden und in IIS gehostet werden.  
  
    > [!NOTE]
    >  Entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den vorhergehenden Setupschritten gewährten Berechtigungen, indem Sie die Batchdatei Cleanupvroot.bat nach Abschluss der Beispiele ausführen.  
  
13. Für selbst gehostete Beispiele \(nicht in IIS gehostet\) ist auf dem Computer die Berechtigung zum Registrieren von HTTP\-Adressen für die Überwachung erforderlich.Die Berechtigung für eine HTTP\-Namespacereservierung wird von dem Benutzerkonto übernommen, das zum Ausführen des Beispiels verwendet wird.Standardmäßig verfügen Administratorkonten über die Berechtigung zum Registrieren von HTTP\-Adressen.Nicht\-Administratorkonten muss die Berechtigung für von den Beispielen verwendete HTTP\-Namespaces gewährt werden.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] dazu, wie Namespacereservierungen konfiguriert werden, finden Sie unter [Konfigurieren von HTTP und HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).  
  
14. Für einige Beispiele ist Message Queuing erforderlich.Installationsanweisungen finden Sie unter [Installieren von Message Queuing \(MSMQ\)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md).  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass der MSMQ\-Dienst gestartet wurde, bevor Sie Beispiele ausführen, für die Message Queuing erforderlich ist.  
  
15. Einige Beispiele erfordern Zertifikate.Siehe [Installationsanleitung für IIS\-Serverzertifikate \(Internetinformationsdienste\)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
## Siehe auch