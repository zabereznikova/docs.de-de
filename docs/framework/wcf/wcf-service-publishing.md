---
title: WCF-Dienstpublishing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e3d86153d4192e04e55fb9e99ef588b45511560
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-service-publishing"></a>WCF-Dienstpublishing
Das [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienstpublishing unterstützt Sie auf Ihrem Weg von der frühen Entwicklungsumgebung, die vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost und dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient gebildet wird, zur eigentlichen Bereitstellung der Anwendung in einer Produktionsumgebung zu Testzwecken. Bevor Sie sich auf einen finalen Bereitstellungsplan festlegen, können Sie mithilfe des [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienstpublishings sicherstellen, dass der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst ordnungsgemäß funktioniert und für die Veröffentlichung bereit ist. Auch können Sie Ihre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheken zu Testzwecken an einer Reihe von Orten bereitstellen.  
  
## <a name="supported-services-and-target-locations"></a>Unterstützte Dienste und Zielorte  
 Das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstpublishing ermöglicht das Veröffentlichen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensten, die auf der Grundlage der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksvorlagen erstellt wurden, sowie der entsprechenden Elementvorlagen. Hierzu zählen unter anderem Folgende:  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksvorlage mit Elementvorlage  
  
-   Syndication-Dienstbibliothek  
  
 Sie können diese Dienstvorlagen durch Auswahl **Datei** -> **neues Projekt** -> **Visual Basic** oder **Visual C#-**  ->  **WCF**. Für die anderen WCF-Vorlagen an diesem Speicherort (einschließlich WCF-Workflowdienstanwendung und WCF-Dienstanwendung) können Veröffentlichung unter Verwendung von [One-Click-Veröffentlichung für Webanwendungen](https://msdn.microsoft.com/en-us/library/dd465337\(v=vs.110\).aspx).  
  
 Der Dienst kann an den folgenden Zielorten veröffentlicht werden:  
  
-   Lokale IIS  
  
-   Dateisystem  
  
-   FTP-Site  
  
## <a name="using-wcf-service-publishing"></a>Verwenden des WCF-Dienstpublishings  
 Führen Sie zum Bereitstellen einer Dienstimplementierung die folgenden Schritte aus:  
  
1.  Öffnen Sie Visual Studio mit erweiterten Berechtigungen (mit der rechten Maustaste in der ausführbare das und verwenden Sie "Als Administrator ausführen", um ihn zu starten).  Wenn Sie mit IIS 7.0 oder höher, stellen Sie sicher, dass Sie die Komponente "IIS-Metabasis und IIS 6-Konfigurationskompatibilität" mit installiert ist "" Windows-Funktionen ein- oder ausschalten "in der Systemsteuerung.  
  
2.  Öffnen Sie ein Dienstprojekt, wählen Sie **erstellen**->**veröffentlichen \<Projektname >** über das Hauptmenü oder mit der rechten Maustaste des Projekts im **Projektmappen-Explorer**, und klicken Sie auf **veröffentlichen**.  
  
3.  Die **veröffentlichen** Fenster wird angezeigt. Klicken Sie auf der **...** . um den Zielort anzugeben, an dem der Dienst bereitgestellt werden soll. Sie können auswählen, um die Anwendung auf lokale IIS, Dateisystem oder FTP-Site bereitzustellen. Wenn die Anwendung für IIS lokal bereitstellen, können Sie Ihre Website auswählen und erstellen Sie Ihre Webanwendung, indem Sie auf die **neue Webanwendung erstellen** Symbol auf der oberen rechten Ecke.  
  
4.  Nachdem Sie auf **veröffentlichen** im Hauptfenster von Visual Studio stellt die Anwendung am angegebenen Zielort bereit, und die Dateien "Web.config", SVC-Datei und Assembly in das Zielverzeichnis kopiert. sein. Der Name der SVC werden die "Datei lautet ProjectName.ServiceName.svc". Nachdem der Dienst erfolgreich veröffentlicht wurde, finden Sie in der Visual Studio-Ausgabefenster einen Hotlink, die "Verbinden mit http://localhost/WebApplicationFolderName zu HYPERLINK"http://localhost/WebApplicationFolderName"" ähnelt. Sie können STRG gedrückt halten und auf den Link klicken, um in Visual Studio eine Browserseite zu öffnen, in der die Dienstverzeichnisstruktur angezeigt wird.  
  
     Wenn die Website nicht geöffnet werden kann, liegt dies möglicherweise daran, dass der Verzeichnisbrowser in IIS nicht aktiviert ist. Befolgen Sie die Tipps im Abschnitt "Mögliche Vorgehensweise", um ihn zu aktivieren. Sie können auch direkt eingeben"HYPERLINK"http://localhost/WebApplicationFolderName"http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc" um die Dienstseite anzuzeigen.  
  
 Sie können **veröffentlichen** angeben, wenn die Assembly, die Konfiguration und die SVC-Datei für alle Dienste, die definiert, die im Projekt an den Zielspeicherort kopiert werden soll, und überschreiben vorhandene Dateien am Ziel.  
  
 Wenn Sie die Anwendung lokal für IIS bereitgestellt haben, treten möglicherweise Fehler in Bezug auf das IIS-Setup auf. Stellen Sie sicher, dass IIS ordnungsgemäß installiert ist. Sie können Geben Sie "HYPERLINK"http://localhost"http://localhost" in Ihrem Browser und überprüfen Sie, ob die IIS-Standardseite angezeigt wird.  In einigen Fällen können die Probleme auch durch eine fehlerhafte Registrierung von ASP.NET oder [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in IIS verursacht werden. Öffnen die Visual Studio-Eingabeaufforderung können und führen den Befehl "aspnet_regiis.exe - Ir", um ASP.NET-Registrierungsprobleme zu beheben oder Befehl "ServiceModelReg.exe – ia" zum Beheben von WCF-Registrierungsprobleme ausführen.  
  
## <a name="files-generated-for-publishing"></a>Generierte Dateien für die Veröffentlichung  
 Damit eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek im Internet gehostet werden kann, müssen die folgenden Dateien durch das Tool erstellt werden: Assemblydateien, Web.config-Datei und SVC-Datei. Alle Dateien werden an den Zielort kopiert. Anschließend wird der Dienst veröffentlicht.  
  
### <a name="assembly-files"></a>Assemblydateien  
 Wenn Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst mithilfe dieses Tools veröffentlichen, wird automatisch zunächst der Dienst erstellt; die Assemblydateien werden erst nach der Erstellung im Dienstprojekt generiert.  
  
### <a name="svc-file"></a>SVC-Datei  
 Durch den Veröffentlichungsvorgang wird für jeden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst eine SVC-Datei generiert. Aus Gründen der Versionsgültigkeit spielt es dabei keine Rolle, ob die Datei bereits vorhanden ist. Zwei unterschiedliche Arten von SVC-Dateien stehen zur Verfügung: eine für die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek und die Syndication-Dienstbibliothek und eine weitere für die Dienstbibliotheken für den sequenziellen Workflow und den Zustandsautomatworkflow. Die generierte \*SVC-Datei wird in den Stammordner am Zielort kopiert.  
  
### <a name="webconfig-file"></a>Web.config-Datei  
 Bei jeder Veröffentlichung eines Dienstprojekts an einem bestimmten Zielort wird eine Web.config-Datei erstellt.  
  
 Die generierte Web.config-Datei enthält Webabschnitte für das Webhosting sowie den Inhalt von App.config für die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek mit folgenden Änderungen:  
  
-   Die Basisadresse wird ausgeschlossen.  
  
-   Einstellungen im `<diagnostics>`-Element werden übersprungen, um die Ablaufverfolgungseinstellungen der Zielplattform beizubehalten.  
  
## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Veröffentlichen von WCF-Diensten mit Nicht-HTTP-Bindungen in IIS  
 Wenn Sie IIS 7.0 oder höher verwenden, können Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste mit Nicht-HTTP-Bindungen in IIS veröffentlichen. Hierfür müssen einige vorbereitende Konfigurationsschritte ausgeführt werden. Weitere Informationen finden Sie unter den Themen zur [Hosten in Windows Process Activation Service](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
## <a name="security"></a>Sicherheit  
 Für eine lokale Veröffentlichung in IIS sind Administratorberechtigungen erforderlich, da IIS unter einem Administratorkonto ausgeführt werden muss. Wird das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstpublishing von einem Benutzer ohne Administratorberechtigungen geöffnet, sind die IIS nicht als Zielort verfügbar. Die Publishing Dateisystem oder FTP-Site ist ohne Administratorberechtigungen möglich.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
