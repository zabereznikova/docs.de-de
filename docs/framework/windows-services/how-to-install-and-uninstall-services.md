---
title: 'Gewusst wie: Installieren und Deinstallieren von Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
manager: douge
ms.openlocfilehash: 9d8e84280b5821f8d8df36694198bd85fb8470d4
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46698393"
---
# <a name="how-to-install-and-uninstall-services"></a>Gewusst wie: Installieren und Deinstallieren von Diensten
Wenn Sie einen Windows-Dienst mit dem.NET Framework entwickeln, können Sie die Dienstanwendung schnell installieren, indem Sie ein Befehlszeilen-Dienstprogramm InstallUtil.exe aufrufen. Wenn Sie ein Entwickler sind, der einen Windows-Dienst freigeben möchte, die Benutzer installieren und deinstallieren können, sollten Sie InstallShield verwenden. Informationen hierzu finden Sie unter [Windows Installer-Bereitstellung](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht. In diesem Fall finden Sie heraus, welches Programm oder Software-Paket den Dienst installiert hat. Wählen Sie dann in der Systemsteuerung **Software** aus, um das Programm zu deinstallieren. Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.  
  
 Um die Schritte in diesem Artikel zu verwenden, müssen Sie zuerst einen Serviceinstaller auf dem Windows-Dienst hinzufügen. Informationen hierzu finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Windows-Dienstprojekte können nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausgeführt werden. Der Grund besteht darin, dass die Dienste des Projekts installiert werden müssen, bevor das Projekt ausgeführt werden kann.  
  
> [!TIP]
>  Sie können den **Server-Explorer** starten und überprüfen, ob der Dienst installiert oder deinstalliert wurde. Weitere Informationen finden Sie unter „Vorgehensweise: Zugreifen auf und Initialisieren von Server-Explorer/Datenbank-Explorer“.  
  
### <a name="to-install-your-service-manually"></a>So installieren Sie einen Dienst manuell  
  
1.  Wählen Sie im Windows-Menü **Start** oder auf dem **Startbildschirm** die Optionen **Visual Studio**, **Visual Studio-Tools** und **Developer-Eingabeaufforderung** aus.  
  
     Eine Visual Studio-Eingabeaufforderung wird angezeigt.  
  
2.  Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.  
  
3.  Führen Sie die Datei "InstallUtil.exe" von der Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter.  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Wenn Sie die Visual Studio-Eingabeaufforderung verwenden, sollten InstallUtil.exe sich auf dem Systempfad befinden. Wenn dies nicht der Fall, können Sie den Pfad hinzufügen oder den vollständig qualifizierten Pfad verwenden, um es aufzurufen. Dieses Tool wird mit dem.NET Framework installiert und lautet `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`. Z. B. für die 32-Bit-Version von.NET Framework 4 oder 4.5. *, wenn Ihr Windows-Installationsverzeichnis C:\Windows, der Pfad ist `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`lautet. Für die 64-Bit-Version von.NET Framework 4 oder 4.5.\* lautet der Standardpfad `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### <a name="to-uninstall-your-service-manually"></a>So deinstallieren Sie einen Dienst manuell  
  
1.  Wählen Sie im Windows-Menü **Start** oder auf dem **Startbildschirm** die Optionen **Visual Studio**, **Visual Studio-Tools** und **Developer-Eingabeaufforderung** aus.  
  
     Eine Visual Studio-Eingabeaufforderung wird angezeigt.  
  
2.  Führen Sie die Datei "InstallUtil.exe" von der Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter.  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  In einigen Fällen könnte der Dienst noch in der Registrierung vorhanden sein, nachdem die ausführbaren Datei für einen Dienst gelöscht wurde. Verwenden Sie in diesem Fall den Befehl [sc delete](https://technet.microsoft.com/library/cc742045.aspx), um den Eintrag für den Dienst aus der Registrierung zu entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Installutil.exe (Installer-Tool)](../../../docs/framework/tools/installutil-exe-installer-tool.md)
