---
title: Installieren von .NET Core auf Linux RHEL 7 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 7 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 4f85ed3da8a434fcd5b6ee88491daf623c3c8b31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76980183"
---
# <a name="rhel-7-package-manager---install-net-core"></a>RHEL 7-Paket-Manager: Installieren von .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf RHEL 7 installieren.

## <a name="register-your-red-hat-subscription"></a>Registrieren Ihres Red Hat-Abonnements

Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren. Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Installieren des .NET Core SDK

Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren. Führen Sie in Ihrem Terminal die folgenden Befehle aus, um den dotnet-Kanal RHEL 7 zu aktivieren und zu installieren.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a>Installieren der ASP.NET Core-Runtime

Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a>Installieren der .NET Core-Runtime

Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a>Weitere Informationen

- [Verwenden von .NET Core 3.1 unter Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
