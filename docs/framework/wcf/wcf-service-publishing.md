---
title: "WCF-Dienstpublishing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# WCF-Dienstpublishing
Das [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienstpublishing unterstützt Sie auf Ihrem Weg von der frühen Entwicklungsumgebung, die vom [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost und dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Testclient gebildet wird, zur eigentlichen Bereitstellung der Anwendung in einer Produktionsumgebung zu Testzwecken.  Bevor Sie sich auf einen finalen Bereitstellungsplan festlegen, können Sie mithilfe des [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienstpublishings sicherstellen, dass der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst ordnungsgemäß funktioniert und für die Veröffentlichung bereit ist.  Auch können Sie Ihre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheken zu Testzwecken an einer Reihe von Orten bereitstellen.  
  
## Unterstützte Dienste und Zielorte  
 Das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstpublishing ermöglicht das Veröffentlichen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensten, die auf der Grundlage der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheksvorlagen erstellt wurden, sowie der entsprechenden Elementvorlagen. Hierzu zählen unter anderem Folgende:  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheksvorlage mit Elementvorlage  
  
-   Dienstbibliotheksvorlage für sequenziellen Workflow mit Elementvorlage  
  
-   Dienstbibliotheksvorlage für Zustandsautomatworkflow mit Elementvorlage  
  
-   Syndication\-Dienstbibliothek  
  
 Diese Dienstvorlagen befinden sich unter **Datei** \-\> **Neues Projekt** \-\> **Visual Basic** oder **Visual C\#** \-\> **WCF**.  
  
 Der Dienst kann an den folgenden Zielorten veröffentlicht werden:  
  
-   Lokale IIS  
  
-   Dateisystem  
  
-   FTP\-Site  
  
-   Remotesite  
  
## Verwenden des WCF\-Dienstpublishings  
 Führen Sie zum Bereitstellen einer Dienstimplementierung die folgenden Schritte aus:  
  
1.  Öffnen Sie Visual Studio mit erweiterten Berechtigungen \(klicken Sie mit der rechten Maustaste auf die ausführbare Datei, und starten Sie sie mit "Als Administrator ausführen"\).  Wenn Sie IIS 7.0 oder höher verwenden, vergewissern Sie sich, dass Sie die Komponente "IIS 6\-Metabasis und IIS 6\-Konfigurationskompatibilität" über "Windows\-Funktionen ein\- oder ausschalten" in der Systemsteuerung installiert haben.  
  
2.  Öffnen Sie ein Dienstprojekt, wählen Sie im Hauptmenü **Erstellen**\-\>**\<Projektname\> veröffentlichen** aus, oder klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf das Projekt, und klicken Sie anschließend auf **Veröffentlichen**.  
  
3.  Das Fenster **Veröffentlichen** wird angezeigt.  Klicken Sie auf die Schaltfläche **...**,  um den Zielort anzugeben, an dem der Dienst bereitgestellt werden soll.  Sie können entscheiden, ob die Anwendung für die lokalen IIS, für das Dateisystem, für eine FTP\-Site oder für eine Remotesite bereitgestellt werden soll.  Wenn Sie die Anwendung für IIS lokal bereitstellen, können Sie Ihre Website auswählen und die Webanwendung darunter erstellen. Klicken Sie dazu in der oberen rechten Ecke auf das Symbol **Neue Webanwendung erstellen**.  
  
4.  Wenn Sie im Hauptfenster auf **Veröffentlichen** klicken, wird die Anwendung von Visual Studio am angegebenen Zielort bereitgestellt, und die Web.config\-Datei, die SVC\-Datei und die Assemblydateien werden in das Zielverzeichnis kopiert.  .  Der Name der SVC\-Datei lautet "ProjectName.ServiceName.svc".  Nach der erfolgreichen Veröffentlichung des Diensts finden Sie im Visual Studio\-Ausgabefenster einen Hotlink ähnlich dem folgenden Beispiel: "Verbinden mit http:\/\/localhost\/WebApplicationFolderName".  Sie können STRG gedrückt halten und auf den Link klicken, um in Visual Studio eine Browserseite zu öffnen, in der die Dienstverzeichnisstruktur angezeigt wird.  
  
     Wenn die Website nicht geöffnet werden kann, liegt dies möglicherweise daran, dass der Verzeichnisbrowser in IIS nicht aktiviert ist.  Befolgen Sie die Tipps im Abschnitt "Mögliche Vorgehensweise", um ihn zu aktivieren.  Alternativ können Sie auch direkt "http:\/\/localhost\/WebApplicationFolderName\/ProjectName.ServiceName.svc" eingeben, um die Dienstseite anzuzeigen.  
  
 Mithilfe von **Veröffentlichen** können Sie angeben, ob Sie die Assembly\- und Konfigurationsdateien und die SVC\-Datei für alle im Projekt definierten Dienste an den Zielort kopieren und alle vorhandenen Dateien am Zielort überschreiben möchten.  
  
 Wenn Sie die Anwendung lokal für IIS bereitgestellt haben, treten möglicherweise Fehler in Bezug auf das IIS\-Setup auf.  Stellen Sie sicher, dass IIS ordnungsgemäß installiert ist.  Sie können im Browser "http:\/\/localhost" eingeben und überprüfen, ob die IIS\-Standardseite aufgerufen wird.  In einigen Fällen können die Probleme auch durch eine fehlerhafte Registrierung von ASP.NET oder [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in IIS verursacht werden.  Öffnen Sie die Visual Studio\-Eingabeaufforderung, und führen Sie den Befehl "aspnet\_regiis.exe \-ir" aus, um ASP.NET\-Registrierungsprobleme zu beheben, oder führen Sie den Befehl "ServiceModelReg.exe –ia" aus, um WCF\-Registrierungsprobleme zu beheben.  
  
## Generierte Dateien für die Veröffentlichung  
 Damit eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliothek im Internet gehostet werden kann, müssen die folgenden Dateien durch das Tool erstellt werden: Assemblydateien, Web.config\-Datei und SVC\-Datei.  Alle Dateien werden an den Zielort kopiert.  Anschließend wird der Dienst veröffentlicht.  
  
### Assemblydateien  
 Wenn Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst mithilfe dieses Tools veröffentlichen, wird automatisch zunächst der Dienst erstellt; die Assemblydateien werden erst nach der Erstellung im Dienstprojekt generiert.  
  
### SVC\-Datei  
 Durch den Veröffentlichungsvorgang wird für jeden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst eine SVC\-Datei generiert. Aus Gründen der Versionsgültigkeit spielt es dabei keine Rolle, ob die Datei bereits vorhanden ist.  Zwei unterschiedliche Arten von SVC\-Dateien stehen zur Verfügung: eine für die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliothek und die Syndication\-Dienstbibliothek und eine weitere für die Dienstbibliotheken für den sequenziellen Workflow und den Zustandsautomatworkflow.  Die generierte SVC\-Datei wird in den Stammordner am Zielort kopiert.  
  
### Web.config\-Datei  
 Bei jeder Veröffentlichung eines Dienstprojekts an einem bestimmten Zielort wird eine Web.config\-Datei erstellt.  
  
 Die generierte Web.config\-Datei enthält Webabschnitte für das Webhosting sowie den Inhalt von App.config für die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliothek mit folgenden Änderungen:  
  
-   Die Basisadresse wird ausgeschlossen.  
  
-   Einstellungen im `<diagnostics>`\-Element werden übersprungen, um die Ablaufverfolgungseinstellungen der Zielplattform beizubehalten.  
  
## Veröffentlichen von WCF\-Diensten mit Nicht\-HTTP\-Bindungen in IIS  
 Wenn Sie IIS 7.0 oder höher verwenden, können Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienste mit Nicht\-HTTP\-Bindungen in IIS veröffentlichen.  Hierfür müssen einige vorbereitende Konfigurationsschritte ausgeführt werden.  Weitere Informationen finden Sie in den Themen unter [Hosten in WAS \(Windows Process Activation Service\)](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
## Sicherheit  
 Für eine lokale Veröffentlichung in IIS sind Administratorberechtigungen erforderlich, da IIS unter einem Administratorkonto ausgeführt werden muss.  Wird das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstpublishing von einem Benutzer ohne Administratorberechtigungen geöffnet, sind die IIS nicht als Zielort verfügbar.  Die Veröffentlichung für Dateisystem, FTP\-Site und Remotesite ist ohne Administratorberechtigungen möglich.  
  
## Siehe auch  
 [WCF Visual Studio\-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)   
 [WCF\-Diensthost \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)   
 [WCF\-Testclient \(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)