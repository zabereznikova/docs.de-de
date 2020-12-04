---
title: Bereitstellen von .net-apps auf Raspberry Pi
description: Erfahren Sie, wie Sie .net-apps auf Raspberry Pi bereitstellen.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592109"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a>Bereitstellen von .net-apps auf Raspberry Pi

Die Bereitstellung von .net-apps auf Raspberry Pi ist identisch mit der einer beliebigen anderen Plattform. Ihre APP kann als *eigenständiger* oder *Framework-abhängiger* Bereitstellungs Modus ausgeführt werden. Jede Strategie bietet Vorteile. Weitere Informationen finden Sie unter [Übersicht über die .NET-Anwendungs Veröffentlichung](../core/deploying/index.md).

## <a name="deploying-a-framework-dependent-app"></a>Bereitstellen einer Framework-abhängigen App

Führen Sie die folgenden Schritte aus, um Ihre APP als Framework-abhängige App bereitzustellen:

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. Installieren Sie .net auf dem Raspberry Pi mithilfe der [dotnet-install-Skripts](../core/tools/dotnet-install-script.md). Führen Sie die folgenden Schritte von einer bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder SSH) aus:
    1. Führen Sie den folgenden Befehl aus, um .net zu installieren:

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > So wird die aktuelle Version installiert. Wenn Sie eine bestimmte Version benötigen, fügen Sie am `--version <VERSION>` Ende hinzu, wobei `<VERSION>` die jeweilige Buildversion ist.

    1. Fügen Sie zum Vereinfachen der Pfad Auflösung eine `DOTNET_ROOT` Umgebungsvariable hinzu, und fügen Sie das *. dotnet* -Verzeichnis `$PATH` mit den folgenden Befehlen hinzu:

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. Überprüfen Sie die .net-Installation mit dem folgenden Befehl:

        ```dotnetcli
        dotnet --version
        ```

        Vergewissern Sie sich, dass die angezeigte Version der installierten Version entspricht.

1. Veröffentlichen Sie die APP wie folgt auf dem Entwicklungs Computer, abhängig von der Entwicklungsumgebung.
    - Wenn Sie **Visual Studio** verwenden, stellen Sie [die app in einem lokalen Ordner](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019)bereit. Wählen Sie vor dem Veröffentlichen in der Zusammenfassung Veröffentlichungs Profil die Option **Bearbeiten** aus, und wählen Sie die Registerkarte **Einstellungen** Stellen Sie sicher, dass der **Bereitstellungs Modus** auf *Framework-abhängig* festgelegt ist und die **Ziel Laufzeit** *portabel* ist.
    - Wenn Sie die **.net-CLI** verwenden, verwenden Sie den [dotnet Publish](../core/tools/dotnet-publish.md) -Befehl. Es sind keine zusätzlichen Argumente erforderlich.

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. Führen Sie die APP über eine bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder SSH) aus. Legen Sie hierzu den Bereitstellungs Ordner als Aktuelles Verzeichnis fest, und führen Sie den folgenden Befehl aus (wobei *HelloWorld.dll* für den Einstiegspunkt der APP steht):

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a>Bereitstellen einer eigenständigen App

Führen Sie die folgenden Schritte aus, um Ihre APP als eigenständige App bereitzustellen:

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. Veröffentlichen Sie die APP wie folgt auf dem Entwicklungs Computer, abhängig von der Entwicklungsumgebung.
    - Wenn Sie **Visual Studio** verwenden, stellen Sie [die app in einem lokalen Ordner](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019)bereit. Wählen Sie vor dem Veröffentlichen in der Zusammenfassung Veröffentlichungs Profil die Option **Bearbeiten** aus, und wählen Sie die Registerkarte **Einstellungen** Stellen Sie sicher, dass der **Bereitstellungs Modus** auf *eigen* ständig festgelegt ist und die **Ziel Laufzeit** auf *Linux-ARM* festgelegt ist.
    - Wenn Sie die **.net-CLI** verwenden, verwenden Sie den [dotnet Publish](../core/tools/dotnet-publish.md) -Befehl mit dem- `-r linux-arm` Argument:

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. Führen Sie die APP über eine bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder SSH) aus. Legen Sie zu diesem Zweck das aktuelle Verzeichnis auf den Bereitstellungs Speicherort fest, und führen Sie die folgenden Schritte aus:
    1. Erteilen Sie der ausführbaren Datei die *Ausführungs* Berechtigung (wobei `HelloWorld` der Name der ausführbaren Datei ist).

        ```bash
        chmod +x HelloWorld
        ```

    1. Führt die ausführbare Datei aus.

        ```bash
        ./HelloWorld
        ```
