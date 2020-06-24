---
title: WCF-Dienstpublishing
description: Mithilfe der WCF-Dienst Veröffentlichung können Sie Ihre Anwendung zu Testzwecken in einer Produktionsumgebung bereitstellen.
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 99798b75e1dc01c8db361f4d8d1f162c7f7617b1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245673"
---
# <a name="wcf-service-publishing"></a>WCF-Dienstpublishing

Windows Communication Foundation (WCF)-Dienst Publishing unterstützt Sie bei der Fortsetzung von der frühen Entwicklungsumgebung, die vom WCF-Dienst Host und vom WCF-Test Client bereitgestellt wird, um die Anwendung in einer Produktionsumgebung zu Testzwecken bereitzustellen. Bevor Sie einen endgültigen Bereitstellungs Plan ausführen, können Sie mithilfe der Windows Communication Foundation (WCF)-Dienst Veröffentlichung überprüfen, ob der WCF-Dienst ordnungsgemäß funktioniert und bereit für die Veröffentlichung ist. Sie können Ihre WCF-Dienst Bibliotheken auch für verschiedene Zielspeicher Orte für Tests bereitstellen.

## <a name="supported-services-and-target-locations"></a>Unterstützte Dienste und Zielorte

Die WCF-Dienst Veröffentlichung unterstützt das Veröffentlichen von WCF-Diensten, die aus dem Satz von WCF-Dienst Bibliotheks Vorlagen erstellt wurden, und die entsprechenden Element Vorlagen, darunter die folgenden:

- Vorlage für WCF-Dienst Bibliotheken mit Element Vorlage.

- Syndication-Dienstbibliothek

Sie finden diese Dienst Vorlagen, indem Sie auf **Datei**  >  **Neues Projekt** > [**Visual Basic** oder **Visual c#**] **> WCF**klicken. Für andere WCF-Vorlagen an diesem Speicherort (einschließlich der WCF-Workflow Dienst Anwendung und der WCF-Dienst Anwendung) können Sie mithilfe der [One-Click-Veröffentlichung für Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))veröffentlichen.

Der Dienst kann an den folgenden Zielorten veröffentlicht werden:

- Lokale IIS

- Dateisystem:

- FTP-Site

## <a name="using-wcf-service-publishing"></a>Verwenden des WCF-Dienstpublishings

Führen Sie zum Bereitstellen einer Dienstimplementierung die folgenden Schritte aus:

1. Öffnen Sie Visual Studio mit erhöhten Rechten (Klicken Sie mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **als Administrator ausführen** aus).  Wenn Sie IIS 7,0 oder höher verwenden, stellen Sie sicher, dass Sie die Komponente "IIS-Metabasis und IIS6-Konfigurations Kompatibilität" mithilfe der Option "Windows-Funktionen ein-oder ausschalten" in der Systemsteuerung installiert haben.

2. Öffnen Sie ein Dienstprojekt, wählen Sie im Hauptmenü **Build**  >  ** \<Project Name> veröffentlichen** aus, oder klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **veröffentlichen**.

3. Das Fenster **veröffentlichen** wird angezeigt. Klicken Sie auf **...**. um den Zielort anzugeben, an dem der Dienst bereitgestellt werden soll. Sie können auswählen, dass die Anwendung auf der lokalen IIS-, Datei System-oder FTP-Site bereitgestellt werden soll. Wenn Sie die Anwendung für lokale IIS bereitstellen, können Sie Ihre Website auswählen und unter Ihr Ihre Webanwendung erstellen, indem Sie in der oberen rechten Ecke auf das Symbol **neue Webanwendung erstellen** klicken.

4. Nachdem Sie im Hauptfenster auf **veröffentlichen** klicken, stellt Visual Studio die Anwendung am angegebenen Zielort bereit und kopiert die Web.config-, SVC-und Assemblydateien in das Zielverzeichnis. . Der Name der SVC-Datei lautet "ProjectName. ServiceName. svc". Nachdem der Dienst erfolgreich veröffentlicht wurde, finden Sie einen Hotlink im Ausgabefenster von Visual Studio, der in etwa wie folgt aussieht: "Verbinden mit `http://localhost/WebApplicationFolderName...` ". Sie können STRG gedrückt halten und auf den Link klicken, um in Visual Studio eine Browserseite zu öffnen, in der die Dienstverzeichnisstruktur angezeigt wird.

     Wenn die Website nicht geöffnet werden kann, liegt dies möglicherweise daran, dass der Verzeichnisbrowser in IIS nicht aktiviert ist. Befolgen Sie die Tipps im Abschnitt "Dinge, die Sie ausprobieren können", um es zu aktivieren. Alternativ können Sie direkt eingeben, `http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc` um die Dienst Seite anzuzeigen.

Mit **veröffentlichen** können Sie angeben, ob Sie die Assembly, die Konfiguration und die SVC-Datei für alle im Projekt definierten Dienste an den Ziel Speicherort kopieren und vorhandene Dateien am Ziel überschreiben möchten.

Wenn Sie die Anwendung lokal für IIS bereitgestellt haben, treten möglicherweise Fehler in Bezug auf das IIS-Setup auf. Stellen Sie sicher, dass IIS ordnungsgemäß installiert ist. Sie können `http://localhost` in der Adressleiste Ihres Browsers eingeben und überprüfen, ob die IIS-Standardseite angezeigt wird. In einigen Fällen können die Probleme auch durch eine nicht ordnungsgemäße Registrierung von ASP.net oder WCF in IIS verursacht werden. Sie können den Developer-Eingabeaufforderung für Visual Studio öffnen und den Befehl ausführen, `aspnet_regiis.exe -ir` um Probleme mit der ASP.net-Registrierung zu beheben `ServiceModelReg.exe –ia`

## <a name="files-generated-for-publishing"></a>Generierte Dateien für die Veröffentlichung
 Bevor eine WCF-Dienst Bibliothek im Internet gehostet werden kann, werden die folgenden Dateien vom Tool generiert: Assemblydateien, Web.config Datei und SVC-Datei. Alle Dateien werden an den Zielort kopiert. Anschließend wird der Dienst veröffentlicht.

### <a name="assembly-files"></a>Assemblydateien
 Wenn Sie einen WCF-Dienst mit diesem Tool veröffentlichen, wird der Dienst zuerst automatisch erstellt, und die Assemblydateien werden nach dem Erstellen im Dienstprojekt generiert.

### <a name="svc-file"></a>SVC-Datei
 Der Veröffentlichungs Vorgang generiert eine *. svc-Datei für jeden WCF-Dienst, unabhängig davon, ob die Datei vorhanden ist oder nicht, um die Gültigkeit der Version sicherzustellen. Es gibt zwei verschiedene Arten von SVC-Dateien: eine für die WCF-Dienst Bibliothek und die Syndizierungs-Dienst Bibliothek und eine weitere für die sequenzielle und Zustands Automat-Workflow Dienst Bibliothek. Die generierte \* svc-Datei wird in den Stamm Ordner am Zielort kopiert.

### <a name="webconfig-file"></a>Web.config-Datei
 Bei jeder Veröffentlichung eines Dienstprojekts an einem bestimmten Zielort wird eine Web.config-Datei erstellt.

 Die generierte Web.config Datei enthält Webabschnitte, die für das Webhosting nützlich sind, sowie den Inhalt von App.config für die WCF-Dienst Bibliothek mit den folgenden Änderungen:

- Die Basisadresse wird ausgeschlossen.

- Einstellungen im `<diagnostics>`-Element werden übersprungen, um die Ablaufverfolgungseinstellungen der Zielplattform beizubehalten.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Veröffentlichen von WCF-Diensten mit Nicht-HTTP-Bindungen in IIS
 Wenn Sie IIS 7.0 oder höher verwenden, können Sie WCF-Dienste mit nicht-HTTP-Bindungen in IIS veröffentlichen. Hierfür müssen einige vorbereitende Konfigurationsschritte ausgeführt werden. Weitere Informationen finden Sie in den Themen unter [Hosting in Windows Process Activation Service](./feature-details/hosting-in-windows-process-activation-service.md).

## <a name="security"></a>Sicherheit
 Für eine lokale Veröffentlichung in IIS sind Administratorberechtigungen erforderlich, da IIS unter einem Administratorkonto ausgeführt werden muss. Wenn ein Benutzer ohne Administrator Berechtigung die WCF-Dienst Veröffentlichung öffnet, ist IIS nicht als Ziel Speicherort verfügbar. Das Veröffentlichen im Datei System oder in einer FTP-Site funktioniert ohne Administratorrechte.

## <a name="see-also"></a>Siehe auch

- [WCF Visual Studio-Vorlagen](wcf-vs-templates.md)
- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
