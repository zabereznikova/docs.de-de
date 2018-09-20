---
title: WCF-Dienstpublishing
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: b62b2616233eb81e64945e997a2efe17973dedd2
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481805"
---
# <a name="wcf-service-publishing"></a>WCF-Dienstpublishing

Windows Communication Foundation (WCF)-Dienst veröffentlichen hilft Ihnen beim Fortschreiten von der frühen Entwicklungsumgebung, die von WCF-Diensthost und WCF-Testclient zum eigentlichen Bereitstellung der Anwendung in einer produktionsumgebung zu Testzwecken bereitgestellt werden. Bevor Sie sich auf einen finalen Bereitstellungsplan festlegen, können Sie Windows Communication Foundation (WCF)-Dienst veröffentlichen verwenden, um sicherzustellen, dass der WCF-Dienst ordnungsgemäß funktioniert und kann veröffentlicht werden. Sie können auch Ihre WCF-Dienstbibliotheken verschiedene Zielspeicherorte für Tests bereitstellen.

## <a name="supported-services-and-target-locations"></a>Unterstützte Dienste und Zielorte

Veröffentlichen von WCF-Dienst unterstützt die WCF-Dienste erstellt, aus dem Satz von WCF-Dienst-Bibliotheksvorlagen und der entsprechenden Elementvorlagen, die zählen unter anderem folgende:

-   WCF-dienstbibliotheksvorlage mit Elementvorlage.

-   Syndication-Dienstbibliothek

Sie können diese Dienstvorlagen auswählen **Datei** > **neues Projekt** > [**Visual Basic** oder **Visual C#-**] > **WCF**. Für die anderen WCF-Vorlagen an diesem Speicherort (einschließlich WCF Workflow Service Application "und" WCF-Dienstanwendung), können Sie veröffentlichen, mit [One-Click-Veröffentlichung für Webanwendungen](https://msdn.microsoft.com/library/dd465337\(v=vs.110\).aspx).

Der Dienst kann an den folgenden Zielorten veröffentlicht werden:

-   Lokale IIS

-   Dateisystem

-   FTP-Site

## <a name="using-wcf-service-publishing"></a>Verwenden des WCF-Dienstpublishings

Führen Sie zum Bereitstellen einer Dienstimplementierung die folgenden Schritte aus:

1.  Öffnen Sie Visual Studio mit erweiterten Berechtigungen (mit der rechten Maustaste in der ausführbare Datei, und wählen Sie **als Administrator ausführen** um ihn zu öffnen).  Wenn Sie mit IIS 7.0 oder höher,, dass sicher haben Sie die "IIS-Metabasis und IIS 6-Konfigurationskompatibilität"-Komponente, die mithilfe von "Turn Windows Features ein- oder ausschalten" in der Systemsteuerung installiert.

2.  Öffnen Sie ein Dienstprojekt, wählen Sie **erstellen** > **veröffentlichen \<Projektname >** im Hauptmenü oder mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer**, und klicken Sie auf **veröffentlichen**.

3.  Die **veröffentlichen** Fenster wird angezeigt. Klicken Sie auf die **...** . um den Zielort anzugeben, an dem der Dienst bereitgestellt werden soll. Sie können auswählen, um die Anwendung auf lokale IIS, Dateisystem oder FTP-Site bereitzustellen. Wenn die Anwendung für IIS lokal bereitstellen, können Sie wählen Sie Ihre Website und Ihre Webanwendung darunter erstellen, indem Sie auf die **neue Webanwendung erstellen** Symbol in der oberen rechten Ecke.

4.  Nachdem Sie auf **veröffentlichen** in im Hauptfenster von Visual Studio die Anwendung an den angegebenen Zielort bereitgestellt und die Datei "Web.config", SVC-Datei und Assembly-Dateien in das Zielverzeichnis kopiert. sein. Der Name der SVC werden "ProjectName.ServiceName.svc". Nachdem der Dienst erfolgreich veröffentlicht wurde, können Sie einen Hotlink suchen, im Ausgabefenster von Visual Studio-Fenster, das "Herstellen einer Verbindung zu HYPERLINK" ähnelt "http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName ...". Sie können STRG gedrückt halten und auf den Link klicken, um in Visual Studio eine Browserseite zu öffnen, in der die Dienstverzeichnisstruktur angezeigt wird.

     Wenn die Website nicht geöffnet werden kann, liegt dies möglicherweise daran, dass der Verzeichnisbrowser in IIS nicht aktiviert ist. Befolgen Sie die Tipps im Abschnitt "Mögliche Vorgehensweise", um ihn zu aktivieren. Sie können auch direkt eingeben"HYPERLINK"http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc" an die Dienstseite anzuzeigen.

Sie können **veröffentlichen** angeben, wenn die Assembly, Konfiguration und SVC-Datei für alle Dienste, die definiert, die im Projekt an den Zielspeicherort kopiert werden soll, und überschreiben vorhandene Dateien am Ziel.

Wenn Sie die Anwendung lokal für IIS bereitgestellt haben, treten möglicherweise Fehler in Bezug auf das IIS-Setup auf. Stellen Sie sicher, dass IIS ordnungsgemäß installiert ist. Sie können eingeben, `http://localhost` in Adressleiste Ihres Browsers ein und überprüfen, ob die IIS-Standardseite anzeigt. In einigen Fällen können die Probleme auch durch eine fehlerhafte Registrierung von ASP.NET oder WCF in IIS verursacht werden. Sie können Developer-Eingabeaufforderung für Visual Studio öffnen, und führen Sie den Befehl `aspnet_regiis.exe -ir` um ASP.NET-Registrierungsprobleme zu beheben, oder führen Sie Befehl `ServiceModelReg.exe –ia` , WCF-Registrierungsprobleme zu beheben.

## <a name="files-generated-for-publishing"></a>Generierte Dateien für die Veröffentlichung
 Bevor eine WCF-Dienstbibliothek Internet gehostet werden kann, werden die folgenden Dateien vom Tool generierten: Assemblydateien, Web.config-Datei und SVC-Datei. Alle Dateien werden an den Zielort kopiert. Anschließend wird der Dienst veröffentlicht.

### <a name="assembly-files"></a>Assemblydateien
 Wenn Sie einen WCF-Dienst veröffentlichen über dieses Tool wird der Dienst automatisch zuerst erstellt und die Assemblydateien werden nach der Erstellung im Dienstprojekt generiert.

### <a name="svc-file"></a>SVC-Datei
 Der Vorgang der Veröffentlichung generiert eine *.svc-Datei für jeden WCF-Dienst, ob die Datei oder nicht, versionsgültigkeit vorhanden ist. Es gibt zwei verschiedene Arten von svc-Dateien: eines für WCF-Dienstbibliothek und Syndication-Dienstbibliothek und eine andere für den sequenziellen Workflow und State Machine Workflow Service Library. Die generierte \*SVC-Datei wird in den Stammordner am Zielort kopiert.

### <a name="webconfig-file"></a>Web.config-Datei
 Bei jeder Veröffentlichung eines Dienstprojekts an einem bestimmten Zielort wird eine Web.config-Datei erstellt.

 Die generierte Datei "Web.config" enthält, die nützlich für das Webhosting sowie den Inhalt der Datei "App.config" für den WCF-Dienstbibliothek mit den folgenden Änderungen sind:

-   Die Basisadresse wird ausgeschlossen.

-   Einstellungen im `<diagnostics>`-Element werden übersprungen, um die Ablaufverfolgungseinstellungen der Zielplattform beizubehalten.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Veröffentlichen von WCF-Diensten mit Nicht-HTTP-Bindungen in IIS
 Wenn Sie IIS 7.0 oder höher können Sie WCF-Dienste mit nicht-HTTP-Bindungen in IIS veröffentlichen. Hierfür müssen einige vorbereitende Konfigurationsschritte ausgeführt werden. Weitere Informationen finden Sie unter den Themen unter [Hosten in Windows Process Activation Service](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).

## <a name="security"></a>Sicherheit
 Für eine lokale Veröffentlichung in IIS sind Administratorberechtigungen erforderlich, da IIS unter einem Administratorkonto ausgeführt werden muss. Wenn ein Benutzer ohne Administratorberechtigungen geöffnet, WCF-Dienst veröffentlichen wird, ist IIS nicht als Zielort verfügbar. Veröffentlichen in das Dateisystem oder FTP-Site ist ohne Administratorberechtigungen möglich.

## <a name="see-also"></a>Siehe auch

- [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)
- [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)