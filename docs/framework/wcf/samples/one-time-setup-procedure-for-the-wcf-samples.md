---
title: Einmaliges Setupverfahren für Windows Communication Foundation-Beispiele
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: e3bf4d70217a8231fe4ddc5b9a15afdfe8f0522e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Einmaliges Setupverfahren für Windows Communication Foundation-Beispiele
Die meisten der Windows Communication Foundation (WCF)-Beispiele sind in Internet Information Services (IIS) gehostet, und führen Sie von einem gemeinsamen virtuellen Verzeichnisses. Diesem einmaligen Setupverfahren wird ein Ordner erstellt, auf dem Datenträger; Es fügt auch ein virtuelles Verzeichnis in IIS **ServiceModelSamples**.  
  
 Die **ServiceModelSamples** virtuelles Verzeichnis wird zum Erstellen und Ausführen aller Beispiele verwendet, die einen IIS-gehosteten Dienst zu verwenden. Dies ist das einzige virtuelle Verzeichnis, das zum Ausführen der Beispiele erforderlich ist. Durch die Erstellung eines Beispiels werden alle zuvor bereitgestellten Dienste in diesem virtuellen Verzeichnis ersetzt. Nur das zuletzt erstellte Beispiel wird bereitgestellt und ist dann in diesem virtuellen Verzeichnis verfügbar.  
  
> [!NOTE]
>  Sie müssen alle Befehle unter einem lokalen Administratorkonto ausführen. Wenn Sie mit Windows 7, [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] oder Windows Server 2008 R2 arbeiten, müssen Sie außerdem die Eingabeaufforderung mit erweiterten Berechtigungen ausführen. Zu diesem Zweck mit der rechten Maustaste des Symbol "Eingabeaufforderung", und klicken Sie dann auf **als Administrator ausführen**. Alle Befehle in diesem Thema müssen an einer Eingabeaufforderung ausgeführt werden, die über die richtigen Pfadeinstellungen verfügt.  Dies kann am einfachsten sichergestellt werden, wenn Sie die Visual Studio-Eingabeaufforderung verwenden. Um diese Aufforderung zu öffnen, klicken Sie auf **starten**Option **Programme**, führen Sie einen Bildlauf nach unten bis zum **Visual Studio 2010**Option **Visual Studio-Tools**, mit der rechten Maustaste **Visual Studio-Eingabeaufforderung (2010)**, und klicken Sie dann auf **als Administrator ausführen**. Wenn Sie eine Visual Studio Express Edition installiert haben, ist diese Eingabeaufforderung nicht verfügbar. In diesem Fall müssen Sie dem Systempfad "C:\Windows\Microsoft.Net\Framework\v4.0" hinzufügen.  
  
### <a name="one-time-setup-procedure-for-wcf-samples"></a>Einmaliges Setupverfahren für WCF-Beispiele  
  
1.  Stellen Sie sicher, dass [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] eingerichtet ist. Weitere Informationen über das Einrichten von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], finden Sie unter [Internet-Internetinformationsdiensts](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md).  
  
2.  Stellen Sie sicher, dass [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] installiert ist. Durchsuchen Sie das folgende Verzeichnis nach v4. 0 (oder höher): **\Windows\Microsoft.NET\Framework**  
  
3.  Wenn [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] nicht installiert ist, und das Betriebssystem ist nicht Windows Server 2008 SP2 oder höher installieren [Hotfix 251798](http://go.microsoft.com/fwlink/?LinkId=184693).  
  
4.  Führen Sie die folgenden Befehle durch. Weitere Informationen dazu, warum diese Befehle ausgeführt werden müssen, finden Sie unter [IIS-Hostdienst](http://msdn.microsoft.com/library/ee5499fc-1b10-4cda-a9b1-13dba70f05f8).  
  
    > [!WARNING]
    >  Wenn IIS neu installiert wird, müssen die folgenden Befehle noch einmal ausgeführt werden.  
  
    ```  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r  
    ```  
  
    > [!WARNING]
    >  Ausführen des Befehls `aspnet_regiis –i –enable` führt dazu, dass der Standardanwendungspool ausführen mit [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], dadurch kann es zu Inkompatibilitätsproblemen bei anderen Anwendungen auf demselben Computer.  
  
5.  Führen Sie die [Firewall-Anweisungen](../../../../docs/framework/wcf/samples/firewall-instructions.md) zum Aktivieren von den Beispielen verwendeten Ports.  
  
6.  Überprüfen Sie die folgenden Standardverzeichnis: \<Installationslaufwerk >:**\WF_WCF_Samples**. Wenn die Beispiele bereits installiert wurden, ist dies das Standardverzeichnis.  
  
7.  Wenn die Beispiele sind nicht installiert sind, installieren Sie sie von den Downloadpfad Beispiele für [Visual C#-](http://go.microsoft.com/fwlink/?LinkId=190939) oder [Visual Basic](http://go.microsoft.com/fwlink/?LinkID=193373).  
  
8.  Nach dem Installieren der Beispiele, wechseln Sie zu: \<Installationslaufwerk >:**\WF_WCF_Samples\WCF\Setup\\**  
  
9. Führen Sie die **Setupvroot.bat** Batchdatei. Die folgenden Schritte werden ausgeführt:  
  
    -   In IIS wird ein virtuelles Verzeichnis mit dem Namen ServiceModelSamples erstellt.  
  
    -   Es werden die neuen Datenträgerverzeichnisse %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples und %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin erstellt.  
  
     Wenn Sie diese Verzeichnisse manuell einrichten möchten, finden Sie unter der [virtuellen Verzeichnis Setupanweisungen](../../../../docs/framework/wcf/samples/virtual-directory-setup-instructions.md). Um alle in diesem Schritt vorgenommenen Änderungen rückgängig zu machen, führen Sie cleanupvroot.bat aus, sobald die Beispiele nicht mehr benötigt werden.  
  
    > [!NOTE]
    >  Diese Prozedur muss nur einmal auf einem Computer ausgeführt werden, es sei denn, cleanupvroot.bat wird ausgeführt.  
  
10. Sie müssen dem Konto, unter dem Sie die Beispiele erstellen, und dem Netzwerkdienstbenutzer die Berechtigung zum Ändern von %SystemDrive%\inetpub\wwwroot zuweisen. Beim Erstellen wird bei einigen im Internet gehosteten Beispielen möglicherweise versucht, die kompilierten Binärdateien an den oben genannten Speicherort zu kopieren. Wenn Sie nicht die entsprechenden Berechtigungen festgelegt haben, können die Beispiele nicht erstellt werden. Sie können die Berechtigungen aber auch unverändert lassen und die SDK-Eingabeaufforderung oder die Visual Studio-Eingabeaufforderung (2012) als Administrator ausführen, oder Sie können die Beispiele als Administrator in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] erstellen.  
  
    > [!NOTE]
    >  Wenn dieser Schritt nicht ausgeführt wird, lässt sich keines der von IIS gehosteten Beispiele erstellen. Legen Sie die Berechtigungen unbedingt richtig fest, oder führen Sie die SDK-Eingabeaufforderung und Visual Studio-Eingabeaufforderung (2012) als Administrator aus.  
  
11. Erstellen Sie das Verzeichnis C:\logs auf dem Computer. Möglicherweise wird es bei einigen Beispielen vorausgesetzt. Stellen Sie sicher, dass das entsprechende Konto Schreibzugriff auf diesen Ordner hat. Für Windows 7 [!INCLUDE[wv](../../../../includes/wv-md.md)], und Windows Server 2008 R2, dieses Konto ist **Netzwerkdienst**. Unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)] ist es das Konto NT-Autorität\Netzwerkdienst. Unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lautet das Konto ASPNET.  
  
12. Führen Sie die Datei "Setupcerttool.bat" aus. Diese Datei befindet sich der \<Datei "Setup.xml" > \WF_WCF_Samples\WCF\Setup\-Ordner.  Mit diesem Skript werden folgende Aufgaben ausgeführt:  
  
    -   Erstellen des Tools FindPrivateKey  
  
    -   Erstellen eines Verzeichnisses mit dem Namen %ProgramFiles%\ServiceModelSampleTools  
  
    -   Kopieren Sie das neue Tool FindPrivateKey in dieses Verzeichnis.  
  
     Dieses Tool ist für Beispiele erforderlich, die Zertifikate verwenden und in IIS gehostet werden.  
  
    > [!NOTE]
    >  Entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den vorhergehenden Setupschritten gewährten Berechtigungen, indem Sie die Batchdatei Cleanupvroot.bat nach Abschluss der Beispiele ausführen.  
  
13. Für selbst gehostete Beispiele (nicht in IIS gehostet) ist auf dem Computer die Berechtigung zum Registrieren von HTTP-Adressen für die Überwachung erforderlich. Die Berechtigung für eine HTTP-Namespacereservierung wird von dem Benutzerkonto übernommen, das zum Ausführen des Beispiels verwendet wird. Standardmäßig verfügen Administratorkonten über die Berechtigung zum Registrieren von HTTP-Adressen. Nicht-Administratorkonten muss die Berechtigung für die von den Beispielen verwendeten HTTP-Namespaces gewährt werden. Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).  
  
14. Für einige Beispiele ist Message Queuing erforderlich. Finden Sie unter [Installieren von Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md) installationsanweisungen.  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass der MSMQ-Dienst gestartet wurde, bevor Sie Beispiele ausführen, für die Message Queuing erforderlich ist.  
  
15. Einige Beispiele erfordern Zertifikate. Finden Sie unter [Internetinformation Services (IIS)-Server-Zertifikat-Installationsanweisungen](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
## <a name="see-also"></a>Siehe auch
