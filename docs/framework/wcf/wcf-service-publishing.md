---
title: WCF-Dienstpublishing
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 258c7e65b69648477e58880f35b100a9378dc9c0
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806460"
---
# <a name="wcf-service-publishing"></a>WCF-Dienstpublishing
Windows Communication Foundation (WCF)-Dienst veröffentlichen hilft Ihnen beim Fortschreiten von der frühen Entwicklungsumgebung, die von WCF-Diensthost oder WCF-Testclient zur eigentlichen Bereitstellung der Anwendung in einer produktionsumgebung zu Testzwecken bereitgestellt. Bevor Sie auf einen finalen Bereitstellungsplan festlegen, können Sie Windows Communication Foundation (WCF)-Dienst veröffentlichen verwenden, um sicherzustellen, dass der WCF-Dienst ordnungsgemäß funktioniert und für die Veröffentlichung bereit ist. Sie könne auch die WCF-Dienst-Bibliotheken für verschiedene Zielspeicherorte für Tests bereitstellen.  
  
## <a name="supported-services-and-target-locations"></a>Unterstützte Dienste und Zielorte  
 Veröffentlichen von WCF-Dienst unterstützt das Veröffentlichen von WCF-Dienste erstellt, aus dem Satz von Bibliotheksvorlagen für WCF-Dienst und der entsprechenden Elementvorlagen, zählen folgende:  
  
-   Vorlage für WCF-Dienstbibliothek mit Elementvorlage.  
  
-   Syndication-Dienstbibliothek  
  
 Sie können diese Dienstvorlagen durch Auswahl **Datei** -> **neues Projekt** -> **Visual Basic** oder **Visual C#-**  ->  **WCF**. Für die anderen WCF-Vorlagen an diesem Speicherort (einschließlich WCF-Workflowdienstanwendung und WCF-Dienstanwendung) können Veröffentlichung unter Verwendung von [One-Click-Veröffentlichung für Webanwendungen](https://msdn.microsoft.com/library/dd465337\(v=vs.110\).aspx).  
  
 Der Dienst kann an den folgenden Zielorten veröffentlicht werden:  
  
-   Lokale IIS  
  
-   Dateisystem  
  
-   FTP-Site  
  
## <a name="using-wcf-service-publishing"></a>Verwenden des WCF-Dienstpublishings  
 Führen Sie zum Bereitstellen einer Dienstimplementierung die folgenden Schritte aus:  
  
1.  Öffnen Sie Visual Studio mit erweiterten Berechtigungen (mit der rechten Maustaste in der ausführbare das und verwenden Sie "Als Administrator ausführen", um ihn zu starten).  Wenn Sie mit IIS 7.0 oder höher, stellen Sie sicher, dass Sie die Komponente "IIS-Metabasis und IIS 6-Konfigurationskompatibilität" mit installiert ist "" Windows-Funktionen ein- oder ausschalten "in der Systemsteuerung.  
  
2.  Öffnen Sie ein Dienstprojekt, wählen Sie **erstellen**->**veröffentlichen \<Projektname >** über das Hauptmenü oder mit der rechten Maustaste des Projekts im **Projektmappen-Explorer**, und klicken Sie auf **veröffentlichen**.  
  
3.  Die **veröffentlichen** Fenster wird angezeigt. Klicken Sie auf der **...** . um den Zielort anzugeben, an dem der Dienst bereitgestellt werden soll. Sie können auswählen, um die Anwendung auf lokale IIS, Dateisystem oder FTP-Site bereitzustellen. Wenn die Anwendung für IIS lokal bereitstellen, können Sie Ihre Website auswählen und erstellen Sie Ihre Webanwendung, indem Sie auf die **neue Webanwendung erstellen** Symbol auf der oberen rechten Ecke.  
  
4.  Nachdem Sie auf **veröffentlichen** im Hauptfenster von Visual Studio stellt die Anwendung am angegebenen Zielort bereit, und die Dateien "Web.config", SVC-Datei und Assembly in das Zielverzeichnis kopiert. sein. Der Name der SVC werden die "Datei lautet ProjectName.ServiceName.svc". Nachdem der Dienst erfolgreich veröffentlicht wurde, können Sie einen Hotlink suchen, im Ausgabefenster von Visual Studio-Fenster, das "Herstellen einer Verbindung zu HYPERLINK" ähnelthttp://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName ...". Sie können STRG gedrückt halten und auf den Link klicken, um in Visual Studio eine Browserseite zu öffnen, in der die Dienstverzeichnisstruktur angezeigt wird.  
  
     Wenn die Website nicht geöffnet werden kann, liegt dies möglicherweise daran, dass der Verzeichnisbrowser in IIS nicht aktiviert ist. Befolgen Sie die Tipps im Abschnitt "Mögliche Vorgehensweise", um ihn zu aktivieren. Sie können auch direkt eingeben"HYPERLINK"http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc", um die Dienstseite anzuzeigen.  
  
 Sie können **veröffentlichen** angeben, wenn die Assembly, die Konfiguration und die SVC-Datei für alle Dienste, die definiert, die im Projekt an den Zielspeicherort kopiert werden soll, und überschreiben vorhandene Dateien am Ziel.  
  
 Wenn Sie die Anwendung lokal für IIS bereitgestellt haben, treten möglicherweise Fehler in Bezug auf das IIS-Setup auf. Stellen Sie sicher, dass IIS ordnungsgemäß installiert ist. Sie können "HYPERLINK" eingebenhttp://localhost" http://localhost" in Ihrem Browser und überprüfen, ob die IIS-Standardseite wird angezeigt.  In einigen Fällen können die Probleme auch durch ASP.NET oder WCF eine fehlerhafte Registrierung in IIS verursacht werden. Öffnen die Visual Studio-Eingabeaufforderung können und führen den Befehl "aspnet_regiis.exe - Ir", um ASP.NET-Registrierungsprobleme zu beheben oder Befehl "ServiceModelReg.exe – ia" zum Beheben von WCF-Registrierungsprobleme ausführen.  
  
## <a name="files-generated-for-publishing"></a>Generierte Dateien für die Veröffentlichung  
 Bevor eine WCF-Dienstbibliothek Web gehostet werden kann, werden die folgenden Dateien vom Tool generiert: Assemblydateien, Web.config-Datei und SVC-Datei. Alle Dateien werden an den Zielort kopiert. Anschließend wird der Dienst veröffentlicht.  
  
### <a name="assembly-files"></a>Assemblydateien  
 Wenn Sie einen WCF-Dienst veröffentlichen mit diesem Tool wird der Dienst automatisch zuerst erstellt und die Assemblydateien werden erst nach der Erstellung im Dienstprojekt generiert.  
  
### <a name="svc-file"></a>SVC-Datei  
 Der Vorgang der Veröffentlichung generiert eine SVC-Datei für jeden WCF-Dienst, ob die Datei oder nicht, um sicherzustellen, dass Version vorhanden ist. Es gibt zwei verschiedene Arten von svc-Dateien: eine für WCF-Dienstbibliothek und Syndication-Dienstbibliothek und eine andere für sequenziellen Workflow und Service für Zustandsautomatworkflowbibliothek. Die generierte \*SVC-Datei wird in den Stammordner am Zielort kopiert.  
  
### <a name="webconfig-file"></a>Web.config-Datei  
 Bei jeder Veröffentlichung eines Dienstprojekts an einem bestimmten Zielort wird eine Web.config-Datei erstellt.  
  
 Die generierte Datei "Web.config" enthält, die nützlich für das Webhosting sowie den Inhalt von "App.config" für den WCF-Dienstbibliothek die folgenden Änderungen sind:  
  
-   Die Basisadresse wird ausgeschlossen.  
  
-   Einstellungen im `<diagnostics>`-Element werden übersprungen, um die Ablaufverfolgungseinstellungen der Zielplattform beizubehalten.  
  
## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Veröffentlichen von WCF-Diensten mit Nicht-HTTP-Bindungen in IIS  
 Wenn Sie IIS 7.0 oder höher können Sie WCF-Diensten mit nicht-HTTP-Bindungen in IIS veröffentlichen. Hierfür müssen einige vorbereitende Konfigurationsschritte ausgeführt werden. Weitere Informationen finden Sie unter den Themen zur [Hosten in Windows Process Activation Service](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
## <a name="security"></a>Sicherheit  
 Für eine lokale Veröffentlichung in IIS sind Administratorberechtigungen erforderlich, da IIS unter einem Administratorkonto ausgeführt werden muss. Wenn ein Benutzer ohne Administratorberechtigungen geöffnet, WCF-Dienst veröffentlichen wird, ist IIS nicht als Zielort verfügbar. Die Publishing Dateisystem oder FTP-Site ist ohne Administratorberechtigungen möglich.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
