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
ms.openlocfilehash: 38fc0172b5f97561d69fe495237e95597d7b9727
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003135"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Vorgehensweise: Installieren und Deinstallieren von Windows-Diensten

Wenn Sie einen Windows-Dienst mit dem .NET Framework entwickeln, können Sie die Dienst-App mithilfe des Befehlszeilen Programms " [*installutil. exe*](../tools/installutil-exe-installer-tool.md) " oder mit [PowerShell](/powershell/scripting/overview)schnell installieren. Entwickler, die einen Windows-Dienst veröffentlichen möchten, den Benutzer installieren und deinstallieren können, sollten InstallShield verwenden. Weitere Informationen finden Sie unter [Erstellen eines Installationspakets (Windows-Client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

> [!WARNING]
> Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht. In diesem Fall finden Sie heraus, welches Programm oder Software-Paket den Dienst installiert hat. Wählen Sie dann in den Einstellungen **Apps** aus, um das Programm zu deinstallieren. Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.

Sie müssen zunächst ein Dienstinstallationsprogramm zu Ihrem Windows-Dienst hinzufügen, um die in diesem Artikel aufgeführten Schritte ausführen zu können. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).

Sie können Windows-Dienstprojekte nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausführen. Bevor Sie das Projekt ausführen können, müssen Sie den Dienst im Projekt installieren.

> [!TIP]
> Sie können den **Server-Explorer** verwenden, um zu überprüfen, ob Sie Ihren Dienst installiert oder deinstalliert haben. Weitere Informationen finden Sie unter [How to use Server Explorer in Visual Studio (Verwenden des Server-Explorers in Visual Studio)](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).

### <a name="install-your-service-manually-using-installutilexe-utility"></a>Manuelles Installieren des Dienstanbieter mithilfe von "installutil. exe"

1. Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.

     Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.

2. Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.

3. Führen Sie die *InstallUtil.exe* über die Eingabeaufforderung mit der ausführbaren Datei Ihres Projekts als Parameter aus:

    ```console
    installutil <yourproject>.exe
    ```

     Wenn Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, sollte *InstallUtil.exe* sich im Systempfad befinden. Andernfalls können Sie die Datei in den Pfad einfügen oder den vollqualifizierten Pfad zum Aufrufen verwenden. Dieses Tool wird mit dem .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<Frameworkversion>\>* installiert.

     Zum Beispiel:
     - Für die 32-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt, wenn Ihr Windows-Installationsverzeichnis *C:\Windows* ist: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Für die 64-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt: *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a>Manuelles Deinstallieren des dienstanzdienstanbieter

1. Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.

     Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.

2. Führen Sie die Datei *InstallUtil.exe* über die Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter:

    ```console
    installutil /u <yourproject>.exe
    ```

3. Nachdem die ausführbare Datei für ein Dienst gelöscht wurde, kann der Dienst weiterhin in der Registrierung vorhanden sein. Verwenden Sie in diesem Fall den Befehl [sc delete](/windows-server/administration/windows-commands/sc-delete), um den Eintrag für den Dienst aus der Registrierung zu entfernen.

### <a name="install-your-service-manually-using-powershell"></a>Manuelles Installieren Ihres Dienstanbieter mithilfe von PowerShell

1. Wählen Sie im **Startmenü** das **Windows PowerShell** -Verzeichnis aus, und wählen Sie dann **Windows PowerShell**aus.

2. Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.

3. Führen Sie das [**New-Service-** ](/powershell/module/microsoft.powershell.management/new-service) Cmdlet mit der-Ausgabe Ihres Projekts und einen Dienstnamen als Parameter aus:

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a>Manuelles Deinstallieren Ihres Dienes mithilfe von PowerShell

1. Wählen Sie im **Startmenü** das **Windows PowerShell** -Verzeichnis aus, und wählen Sie dann **Windows PowerShell**aus.

2. Führen Sie das Cmdlet " [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) " mit dem Namen Ihres Dienstanbieter als Parameter aus:

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. Nachdem die ausführbare Datei für ein Dienst gelöscht wurde, kann der Dienst weiterhin in der Registrierung vorhanden sein. Verwenden Sie in diesem Fall den Befehl [sc delete](/windows-server/administration/windows-commands/sc-delete), um den Eintrag für den Dienst aus der Registrierung zu entfernen.

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](../windows-services/introduction-to-windows-service-applications.md)
- [Vorgehensweise: Erstellen von Windows-Diensten](../windows-services/how-to-create-windows-services.md)
- [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Installer-Tool)](../tools/installutil-exe-installer-tool.md)
