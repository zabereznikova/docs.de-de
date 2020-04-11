---
title: Einmaliges Setupverfahren für Windows Communication Foundation-Beispiele
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 954ec04d2ef1ca7667b4f75a8a6652010b5dbd33
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121620"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Einmaliges Setupverfahren für Windows Communication Foundation-Beispiele

Die meisten Windows Communication Foundation (WCF)-Beispiele werden in Internet Informationsdiensten (Internet Information Services, IIS) gehostet und aus einem gemeinsamen virtuellen Verzeichnis ausgeführt. Diese einmalige Einrichtungsprozedur erstellt einen Ordner auf dem Datenträger. Außerdem wird IIS ein virtuelles Verzeichnis mit dem Namen **ServiceModelSamples**hinzugefügt.

Das virtuelle **ServiceModelSamples-Verzeichnis** wird zum Erstellen und Ausführen aller Beispiele verwendet, die einen iIS-gehosteten Dienst verwenden. Dies ist das einzige virtuelle Verzeichnis, das zum Ausführen der Beispiele erforderlich ist. Durch die Erstellung eines Beispiels werden alle zuvor bereitgestellten Dienste in diesem virtuellen Verzeichnis ersetzt. Nur das zuletzt erstellte Beispiel wird bereitgestellt und ist dann in diesem virtuellen Verzeichnis verfügbar.

> [!NOTE]
> Sie müssen alle Befehle unter einem lokalen Administratorkonto ausführen. Wenn Sie Windows 7, Windows Vista oder Windows Server 2008 R2 verwenden, müssen Sie auch die Eingabeaufforderung mit erhöhten Berechtigungen ausführen. Klicken Sie dazu mit der rechten Maustaste auf das Eingabeaufforderungssymbol, und klicken Sie dann auf **Als Administrator ausführen**. Alle Befehle in diesem Thema müssen an einer Eingabeaufforderung ausgeführt werden, die über die richtigen Pfadeinstellungen verfügt.  Dies kann am einfachsten sichergestellt werden, wenn Sie die Visual Studio-Eingabeaufforderung verwenden. Um diese Eingabeaufforderung zu öffnen, klicken Sie auf **Starten**, wählen Sie **Alle Programme**aus , scrollen Sie nach unten zu Visual **Studio 2010**, wählen Sie Visual Studio Tools **aus**, klicken Sie mit der rechten Maustaste auf **Visual Studio-Eingabeaufforderung (2010)**, und klicken Sie dann auf **Ausführen als Administrator**. Wenn Sie eine Visual Studio Express Edition installiert haben, ist diese Eingabeaufforderung nicht verfügbar. In diesem Fall müssen Sie dem Systempfad "C:\Windows\Microsoft.Net\Framework\v4.0" hinzufügen.

### <a name="one-time-setup-procedure-for-wcf-samples"></a>Einmaliges Setupverfahren für WCF-Beispiele

1. Stellen Sie sicher, dass ASP.NET eingerichtet ist. Weitere Informationen zum Einrichten von ASP.NET finden Sie unter [Internetinformationsdienst-Hostinganweisungen](internet-information-service-hosting-instructions.md).

2. Stellen Sie sicher, dass .NET Framework 4 installiert ist. Durchsuchen Sie das folgende Verzeichnis nach v4.0 (oder **höher):**

3. Stellen Sie sicher, dass Visual Studio 2012 oder höher installiert ist oder Ihr Betriebssystem Windows Server 2008 SP2 oder höher ist.

4. Führen Sie die folgenden Befehle aus: Weitere Informationen dazu, warum diese Befehle ausgeführt werden müssen, finden Sie unter [IIS Hosted Service Fails](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752252(v=vs.90)).

    > [!WARNING]
    > Wenn IIS neu installiert wird, müssen die folgenden Befehle noch einmal ausgeführt werden.

    ```console
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r
    ```

    > [!WARNING]
    > Durch Ausführen `aspnet_regiis –i –enable` des Befehls wird der Standard-App-Pool mit .NET Framework 4 ausgeführt, was zu Inkompatibilitätsproblemen für andere Anwendungen auf demselben Computer führen kann.

5. Befolgen Sie die [Firewall-Anweisungen zum](firewall-instructions.md) Aktivieren der Ports, die von den Beispielen verwendet werden.

6. Suchen Sie nach dem \<folgenden Standardverzeichnis: InstallDrive>: WF_WCF_Samples . . .**. . . . . . . . . . . . . . . . . . . . . . . . . . . . .** Wenn die Beispiele bereits installiert wurden, ist dies das Standardverzeichnis.

7. Wenn die Beispiele nicht installiert sind, installieren Sie sie aus [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

8. Nach der Installation der Beispiele \<gehen Sie zu : InstallDrive>**WF_WCF_Samples:\\ **

9. Führen Sie die **Batchdatei Setupvroot.bat** aus. Es werden folgende Schritte ausgeführt:

    - In IIS wird ein virtuelles Verzeichnis mit dem Namen ServiceModelSamples erstellt.

    - Es werden die neuen Datenträgerverzeichnisse %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples und %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin erstellt.

    Wenn Sie diese Verzeichnisse lieber manuell einrichten möchten, lesen Sie die Anweisungen zum [Virtual Directory-Setup](virtual-directory-setup-instructions.md). Um alle in diesem Schritt vorgenommenen Änderungen rückgängig zu machen, führen Sie cleanupvroot.bat aus, sobald die Beispiele nicht mehr benötigt werden.

    > [!NOTE]
    > Diese Prozedur muss nur einmal auf einem Computer ausgeführt werden, es sei denn, cleanupvroot.bat wird ausgeführt.

10. Sie müssen dem Konto, unter dem Sie die Beispiele erstellen, und dem Netzwerkdienstbenutzer die Berechtigung zum Ändern von %SystemDrive%\inetpub\wwwroot zuweisen. Beim Erstellen wird bei einigen im Internet gehosteten Beispielen möglicherweise versucht, die kompilierten Binärdateien an den oben genannten Speicherort zu kopieren. Wenn Sie nicht die entsprechenden Berechtigungen festgelegt haben, können die Beispiele nicht erstellt werden. Alternativ können Sie die Berechtigungen so belassen, wie sie sind, und die SDK-Eingabeaufforderung oder Visual Studio-Eingabeaufforderung (2012) als Administrator ausführen oder die Beispiele in Visual Studio 2012 erstellen, die auch als Administrator ausgeführt werden.

    > [!NOTE]
    > Wenn dieser Schritt nicht ausgeführt wird, lässt sich keines der von IIS gehosteten Beispiele erstellen. Legen Sie die Berechtigungen unbedingt richtig fest, oder führen Sie die SDK-Eingabeaufforderung und Visual Studio-Eingabeaufforderung (2012) als Administrator aus.

11. Erstellen Sie das Verzeichnis C:\logs auf dem Computer. Möglicherweise wird es bei einigen Beispielen vorausgesetzt. Stellen Sie sicher, dass das entsprechende Konto Schreibzugriff auf diesen Ordner hat. Für Windows 7, Windows Vista und Windows Server 2008 R2 lautet dieses Konto **Network Service**. Für Windows Server 2008 ist das Konto NT Authority-Netzwerkdienst. Für Windows XP und Windows Server 2003 ist das Konto ASPNET.

12. Führen Sie die Datei "Setupcerttool.bat" aus. Diese Datei befindet \<sich im Ordner InstallPath> WF_WCF_Samples.  Mit diesem Skript werden folgende Aufgaben ausgeführt:

    - Erstellen des Tools FindPrivateKey

    - Erstellen eines Verzeichnisses mit dem Namen %ProgramFiles%\ServiceModelSampleTools

    - Kopieren Sie das neue Tool FindPrivateKey in dieses Verzeichnis.

    Dieses Tool ist für Beispiele erforderlich, die Zertifikate verwenden und in IIS gehostet werden.

    > [!NOTE]
    > Entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den vorhergehenden Setupschritten gewährten Berechtigungen, indem Sie die Batchdatei Cleanupvroot.bat nach Abschluss der Beispiele ausführen.

13. Für selbst gehostete Beispiele (nicht in IIS gehostet) ist auf dem Computer die Berechtigung zum Registrieren von HTTP-Adressen für die Überwachung erforderlich. Die Berechtigung für eine HTTP-Namespacereservierung wird von dem Benutzerkonto übernommen, das zum Ausführen des Beispiels verwendet wird. Standardmäßig verfügen Administratorkonten über die Berechtigung zum Registrieren von HTTP-Adressen. Nicht-Administratorkonten muss die Berechtigung für die von den Beispielen verwendeten HTTP-Namespaces gewährt werden. Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](../feature-details/configuring-http-and-https.md).

14. Für einige Beispiele ist Message Queuing erforderlich. Installationsanweisungen finden Sie unter [Installieren von Message Queuing (MSMQ).](installing-message-queuing-msmq.md)

    > [!NOTE]
    > Stellen Sie sicher, dass der MSMQ-Dienst gestartet wurde, bevor Sie Beispiele ausführen, für die Message Queuing erforderlich ist.

15. Einige Beispiele erfordern Zertifikate. S. [Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)](iis-server-certificate-installation-instructions.md).
