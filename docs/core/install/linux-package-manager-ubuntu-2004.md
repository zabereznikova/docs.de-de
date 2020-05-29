---
title: '.NET Core: Installieren von .NET Core auf Ubuntu 20.04 mit einem Paket-Manager'
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf Ubuntu 20.04 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 05/13/2020
ms.openlocfilehash: 4d7d7ee9117314ef360097fee929f24943c7a7f2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83618870"
---
# <a name="ubuntu-2004-package-manager---install-net-core"></a>Ubuntu 20.04-Paket-Manager: Installieren von .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf Ubuntu 20.04 installieren.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a>Hinzufügen des Microsoft-Repositoryschlüssels und -Feeds

Vor der Installation von .NET müssen Sie folgende Schritte ausführen:

- Fügen Sie der Liste der vertrauenswürdigen Schlüssel den Microsoft-Paketsignaturschlüssel hinzu.
- Fügen Sie das Repository dem Paket-Manager hinzu.
- Installieren Sie erforderliche Abhängigkeiten.

Dies muss nur einmal pro Computer ausgeführt werden.

Öffnen Sie ein Terminal, und führen Sie die folgenden Befehle aus.

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a>Installieren des .NET Core SDK

Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann das .NET Core SDK. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-sdk-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).

## <a name="install-the-aspnet-core-runtime"></a>Installieren der ASP.NET Core-Runtime

Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die ASP.NET Core-Runtime. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket aspnetcore-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).

## <a name="install-the-net-core-runtime"></a>Installieren der .NET Core-Runtime

Aktualisieren Sie die zur Installation verfügbaren Produkte, und installieren Sie dann die .NET Core-Runtime. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> Wenn Sie eine ähnliche Fehlermeldung wie **Das Paket dotnet-runtime-3.1 wurde nicht gefunden** erhalten, lesen Sie den Abschnitt [Problembehandlung des Paket-Managers](#troubleshoot-the-package-manager).

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Problembehandlung des Paket-Managers

Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.

### <a name="unable-to-locate"></a>Auffinden nicht möglich

Führen Sie die folgenden Befehle aus, wenn Sie eine ähnliche Fehlermeldung wie **Das Paket {das .NET Core-Paket} wurde nicht gefunden** erhalten.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

Wenn dies nicht funktioniert, können Sie eine manuelle Installation mit den folgenden Befehlen ausführen.

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/20.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a>Fehler beim Abrufen

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
