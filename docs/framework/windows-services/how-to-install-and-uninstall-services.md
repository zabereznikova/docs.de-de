---
title: 'Vorgehensweise: Installieren und Deinstallieren von Windows-Diensten'
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 43b5ad2f346406897e8bcbcce5660a6c9524f9af
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826259"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Vorgehensweise: Installieren und Deinstallieren von Windows-Diensten
Wenn Sie einen Windows-Dienst mit dem .NET Framework entwickeln, können Sie Ihre Dienstanwendung schnell installieren, indem Sie das Befehlszeilendienstprogramm [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) verwenden. Entwickler, die einen Windows-Dienst veröffentlichen möchten, den Benutzer installieren und deinstallieren können, sollten InstallShield verwenden. Weitere Informationen finden Sie unter [Erstellen eines Installationspakets (Windows-Client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).
  
> [!WARNING]
>  Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht. In diesem Fall finden Sie heraus, welches Programm oder Software-Paket den Dienst installiert hat. Wählen Sie dann in den Einstellungen **Apps** aus, um das Programm zu deinstallieren. Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.  
  
 Sie müssen zunächst ein Dienstinstallationsprogramm zu Ihrem Windows-Dienst hinzufügen, um die in diesem Artikel aufgeführten Schritte ausführen zu können. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Sie können Windows-Dienstprojekte nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausführen. Bevor Sie das Projekt ausführen können, müssen Sie den Dienst im Projekt installieren.  
  
> [!TIP]
>  Sie können den **Server-Explorer** verwenden, um zu überprüfen, ob Sie Ihren Dienst installiert oder deinstalliert haben. Weitere Informationen finden Sie unter [How to use Server Explorer in Visual Studio (Verwenden des Server-Explorers in Visual Studio)](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).
  
### <a name="install-your-service-manually"></a>Manuelles Installieren des Diensts  
  
1.  Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.
  
     Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt. 
  
2.  Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.  
  
3.  Führen Sie die *InstallUtil.exe* über die Eingabeaufforderung mit der ausführbaren Datei Ihres Projekts als Parameter aus:  
  
    ```console
    installutil <yourproject>.exe  
    ```  

     Wenn Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, sollte *InstallUtil.exe* sich im Systempfad befinden. Andernfalls können Sie die Datei in den Pfad einfügen oder den vollqualifizierten Pfad zum Aufrufen verwenden. Dieses Tool wird mit dem .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<Frameworkversion>* installiert.
     
     Beispiel:
     - Für die 32-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt, wenn Ihr Windows-Installationsverzeichnis *C:\Windows* ist: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Für die 64-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt: *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.
  
### <a name="uninstall-your-service-manually"></a>Manuelles Deinstallieren des Diensts  
  
1. Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.
  
     Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.  
  
2.  Führen Sie die Datei *InstallUtil.exe* über die Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter:  
  
    ```console  
    installutil /u <yourproject>.exe  
    ```  
  
3. Nachdem die ausführbare Datei für ein Dienst gelöscht wurde, kann der Dienst weiterhin in der Registrierung vorhanden sein. Verwenden Sie in diesem Fall den Befehl [sc delete](/windows-server/administration/windows-commands/sc-delete), um den Eintrag für den Dienst aus der Registrierung zu entfernen.  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in Windows-Dienstanwendungen](../windows-services/introduction-to-windows-service-applications.md)
- [Vorgehensweise: Erstellen von Windows-Diensten](../windows-services/how-to-create-windows-services.md)
- [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Installer-Tool)](../tools/installutil-exe-installer-tool.md)
