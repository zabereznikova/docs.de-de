---
title: Installieren von .NET Core auf Linux RHEL 8 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 8 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 054494a9b77e1c7803e42c947e067d3eb290f73c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78849795"
---
# <a name="rhel-8-package-manager---install-net-core"></a>RHEL 8-Paket-Manager: Installieren von .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf RHEL 8 installieren.

## <a name="register-your-red-hat-subscription"></a>Registrieren Ihres Red Hat-Abonnements

Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren. Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Installieren des .NET Core SDK

Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installieren der ASP.NET Core-Runtime

Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installieren der .NET Core-Runtime

Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a>Siehe auch

- [Verwenden von .NET Core 3.1 unter Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
