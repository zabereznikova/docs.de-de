---
title: Voraussetzungen für .NET Core unter Linux
description: Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen.
author: jralexander
ms.author: johalex
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 9d986ed56bbc6f803988fde4b5500cd5d5364050
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a>Voraussetzungen für .NET Core unter Linux

Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux. Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:

* [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> Das .NET Core SDK-Paket ist für Produktionsserver und -Umgebungen nicht erforderlich. Für in Produktionsumgebungen bereitgestellte Apps ist nur das .NET Core-Runtime-Paket erforderlich. Die .NET Core-Runtime wird als Teil einer eigenständigen Bereitstellung mit Apps bereitgestellt, sie muss für frameworkabhängige, bereitgestellte Apps jedoch separat bereitgestellt werden. Weitere Informationen zu den frameworkabhängigen und eigenständigen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](./deploying/index.md). Außerdem finden Sie bestimmte Richtlinien unter [Self-contained Linux applications (Eigenständige Linux-Anwendungen)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

## <a name="supported-linux-versions"></a>Unterstützte Linux-Versionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x behandelt Linux als ein einzelnes Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.

.NET Core 2.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 27, 26
* Debian 9, 8.7 oder höhere Versionen
* Ubuntu 17.10, 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 oder höhere Versionen
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 oder höher

Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 26
* Debian 8.2 oder höhere Versionen
* Ubuntu 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 oder höhere Versionen (.NET Core 1.1)

Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

---

## <a name="linux-distribution-dependencies"></a>Abhängigkeiten der Linux-Distributionen

Bei folgenden Paketen handelt es sich um Beispiele. Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.

### <a name="ubuntu"></a>Ubuntu

Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* libunwind8
* liblttng-ust0
* libcurl3
* libssl1.0.0
* libuuid1
* libkrb5-3
* zlib1g
* libicu52 (für 14.X)
* libicu55 (für 16.X)
* libicu57 (für 17.X)

### <a name="centos"></a>CentOS

Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* libunwind
* lttng-ust
* libcurl
* openssl-libs
* libuuid
* krb5-libs
* libicu
* zlib

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Eigenständige Linux-Anwendungen).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installieren der erforderlichen Abhängigkeiten für .NET Core mit nativen Installationsprogrammen

Native Installationsprogramme für .NET Core sind für unterstützte Linux-Distributionen und -Versionen verfügbar. Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server. Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden. Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.

Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete:

* Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.
* Das eigenständige Verwenden der Pakete, DEB oder RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Das Skripten von Installationen mit dem Installationsskript von .NET Core

Die [Dotnet-Installationsskripts](./tools/dotnet-install-script.md) werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können das Skript unter [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh) herunterladen.

Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet. Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>Installieren von .NET Core auf unterstützten Versionen von Red Hat Enterprise Linux (RHEL)

So installieren Sie .NET Core auf unterstützten RHEL-Versionen:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Führen Sie die Anweisungen unter [.NET Core 2.x SDK and Runtime Installer instructions (Installationsanweisungen für .NET Core 2.x SDK und -Runtime)](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current) für unterstützte RHEL-Versionen aus, um sicherzustellen, dass Sie über die aktuellen Installationsinformationen verfügen.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2.  Die neuesten Installationsinformationen zu .NET Core 1.1 auf Red Hat Enterprise Linux finden Sie unter [.NET Core 1.1 Getting Started Guide (Erste Schritte mit .NET Core 1.1)](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)
     
**.NET Core 1.0**

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2.  Die neuesten Installationsinformationen zu .NET Core 1.0 auf Red Hat Enterprise Linux finden Sie unter [.NET Core 1.0 Getting Started Guide (Erste Schritte mit .NET Core 1.0)](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)

Weitere Informationen zur Registrierung des Kanalzugriffs von Red Hat .NET finden Sie im Abschnitt „Red Hat“ in [Kapitel 1 des Leitfadens für erste Schritte mit .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/).

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a>Installieren von .NET Core auf unterstützten Verteilungen bzw. Versionen von Ubuntu und Linux Mint (64-Bit)

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 2.x auf unterstützten Verteilungen bzw. Versionen von Ubuntu und Linux Mint (64-Bit):

**.NET Core 2.0**

|Runtimes/SDKs          |Ubuntu 17.10  |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|--------------|----------------------------|----------------------------|
|.NET Core-Runtime 2.0.6  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|.NET Core-Runtime 2.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|.NET Core SDK 2.1.103    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|.NET Core SDK 2.0.3      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |

**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 Preview 1 oder höher installieren](https://www.visualstudio.com/vs/preview), um .NET Core 2.1 mit Visual Studio verwenden zu können.

|Runtimes/SDKs                  |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|---------------------------------|----------------|----------------------------|----------------------------|
|.NET Core-Runtime 2.1.0-preview2 |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|.NET Core-Runtime 2.1.0-preview1 |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|.NET Core SDK 2.1.300-preview2   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)
|.NET Core SDK 2.1.300-preview1   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Verteilungen bzw. Versionen von Ubuntu und Linux Mint (64-Bit):

| Runtimes/SDKs         |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|.NET Core-Runtime 1.1.7  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.1.6  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.10 |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.9  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.8      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.7      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.4      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.1      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a>Installieren von .NET Core auf unterstützten Versionen von Debian (64-Bit)

So installieren Sie .NET Core auf unterstützten Versionen von Debian (64-Bit):

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 2.x auf unterstützten Versionen von Debian (64-Bit):

**.NET Core 2.0**

|Runtimes/SDKs          |Debian 9       |Debian 8       |
|-------------------------|---------------|---------------|
|.NET Core-Runtime 2.0.6  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|.NET Core-Runtime 2.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|.NET Core SDK 2.1.103    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|.NET Core SDK 2.0.3      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |

**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 Preview 1 oder höher installieren](https://www.visualstudio.com/vs/preview), um .NET Core 2.1 mit Visual Studio verwenden zu können.

|Runtimes/SDKs                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|.NET Core-Runtime 2.1.0-preview2 |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|.NET Core-Runtime 2.1.0-preview1 |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|.NET Core SDK 2.1.300-preview2   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|.NET Core SDK 2.1.300-preview1   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x für Debian 9 oder Debian 8:

* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.10 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)
* .NET Core SDK 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)
* .NET Core SDK 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a>Installieren von .NET Core auf unterstützten Versionen von Fedora (64-Bit)

So installieren Sie .NET Core auf unterstützten Versionen von Fedora:

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 2.x auf unterstützten Versionen von Fedora (64-Bit):

**.NET Core 2.0**

|Runtimes/SDKs          |Fedora 26 oder höher |Fedora 25 oder früher |
|-------------------------|-------------------|----------------------|
|.NET Core-Runtime 2.0.6  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|.NET Core-Runtime 2.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|.NET Core SDK 2.1.103    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|.NET Core SDK 2.0.3      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 Preview 1 oder höher installieren](https://www.visualstudio.com/vs/preview), um .NET Core 2.1 mit Visual Studio verwenden zu können.

|Runtimes/SDKs                  |Fedora 26 oder höher |Fedora 25 oder früher |
|---------------------------------|-------------------|----------------------|
|.NET Core-Runtime 2.1.0-preview2 |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview2)           |
|.NET Core-Runtime 2.1.0-preview1 |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview1)           |
|.NET Core SDK 2.1.300-preview2   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview2)           |
|.NET Core SDK 2.1.300-preview1   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview1)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Versionen von Fedora (64-Bit):

**Fedora 24**

* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

**Fedora 23**

* .NET Core-Runtime 1.0.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a>Installieren von .NET Core auf unterstützten Verteilungen bzw. Versionen von CentOS und Oracle Linux (64-Bit)

So installieren Sie .NET Core auf unterstützten Verteilungen bzw. Versionen von CentOS und Oracle Linux (64-Bit):

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 2.x auf unterstützten Verteilungen bzw. Versionen von CentOS und Oracle Linux (64-Bit):

**.NET Core 2.0**

* .NET Core-Runtime 2.0.6 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* .NET Core-Runtime 2.0.5 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)
* .NET Core SDK 2.1.103 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)
* .NET Core SDK 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 Preview 1 oder höher installieren](https://www.visualstudio.com/vs/preview/), um .NET Core 2.1 mit Visual Studio verwenden zu können.

* .NET Core-Runtime 2.1.0-preview2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)
* .NET Core-Runtime 2.1.0-preview1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-preview2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-preview1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Verteilungen bzw. Versionen von CentOS und Oracle Linux (64-Bit):

* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.10 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)
* .NET Core SDK 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)
* .NET Core SDK 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>Installieren von .NET Core auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit)

So installieren Sie .NET Core 2.x auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit):

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 2.x auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit):

**.NET Core 2.0**

* .NET Core-Runtime 2.0.6 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)
* .NET Core-Runtime 2.0.5 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)
* .NET Core SDK 2.1.103 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)
* .NET Core SDK 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 Preview 1 oder höher installieren](https://www.visualstudio.com/vs/preview), um .NET Core 2.1 mit Visual Studio verwenden zu können.

* .NET Core-Runtime 2.1.0-preview2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)
* .NET Core-Runtime 2.1.0-preview1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-preview2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-preview1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit):

**SUSE Linux Enterprise Server 13.2**

* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)

**openSUSE 24**

* .NET Core SDK 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)

---

> [!IMPORTANT]
> Weitere Informationen zu Problemen mit der Installation von .NET Core auf einer unterstützten Verteilung bzw. Version von Linux finden Sie in den folgenden Artikeln zu Ihrer installierte Verteilung bzw. Version:
> * [.NET Core 2.1 known issues (.NET Core 2.1 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [.NET Core 2.0 known issues (.NET Core 2.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [.NET Core 1.1 known issues (.NET Core 1.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [.NET Core 1.0 known issues (.NET Core 1.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0)