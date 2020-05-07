---
title: Installieren von .NET Core auf CentOS Linux 8 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die .NET Core-Runtime auf CentOS 8 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728504"
---
# <a name="centos-8-package-manager---install-net-core"></a>CentOS 8-Paket-Manager: Installieren von .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

In diesem Artikel wird beschrieben, wie Sie .NET Core mit einem Paket-Manager auf CentOS 8 installieren.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a>Installieren des .NET Core SDK

Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installieren der ASP.NET Core-Runtime

Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installieren der .NET Core-Runtime

Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
