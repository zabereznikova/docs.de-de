---
title: '.NET Core: Installieren von .NET Core auf Fedora 32 mit einem Paket-Manager'
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die .NET Core-Runtime auf Fedora 32 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624951"
---
# <a name="fedora-32-package-manager---install-net-core"></a>Fedora 32-Paket-Manager: Installieren von .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

In diesem Artikel wird beschrieben, wie Sie .NET Core mit einem Paket-Manager auf Fedora 32 installieren.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

Ab Fedora 32 ist .NET Core 3.1 in den Standardpaketrepositorys in Fedora verfügbar.

## <a name="install-the-net-core-sdk"></a>Installieren des .NET Core SDK

Installieren Sie das .NET Core-SDK. Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installieren der ASP.NET Core-Runtime

Installieren Sie die ASP.NET Core-Runtime. Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installieren der .NET Core-Runtime

Installieren Sie die .NET Core-Runtime. Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

Installieren Sie das [.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) oder die [.NET Core-Runtime](runtime.md?pivots=os-linux#download-and-manually-install) manuell, um andere Versionen von .NET Core zu installieren.
