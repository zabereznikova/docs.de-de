---
title: Voraussetzungen für .NET Core unter Linux
description: Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen.
author: jralexander
ms.author: johalex
ms.date: 08/20/2018
ms.openlocfilehash: 4939dfb642c2aef9da593a193f42334f1d57e067
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842267"
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

**NET Core 2.1**

.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

* Red Hat Enterprise Linux 7, 6 – 64-Bit (`x86_64` oder `amd64`)
* CentOS 7 – 64-Bit (`x86_64` oder `amd64`) 
* Oracle Linux 7 – 64-Bit (`x86_64` oder `amd64`) 
* Fedora 28, 27 – 64-Bit (`x86_64` oder `amd64`) 
* Debian 9 (64 Bit, `arm32`), 8.7 oder höher – 64 Bit (`x86_64` oder `amd64`)
* Ubuntu 18.04 (64 Bit, `arm32`), 16.04, 14.04 – 64 Bit (`x86_64` oder `amd64`)
* Linux Mint 18, 17 – 64-Bit (`x86_64` oder `amd64`)
* openSUSE 42.3 oder höhere Versionen – 64-Bit (`x86_64` oder `amd64`)
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 oder höher – 64-Bit (`x86_64` oder `amd64`)
* Alpine Linux 3.7 oder höhere Versionen – 64-Bit (`x86_64` oder `amd64`)

Unter [.NET Core 2.1 Supported OS Versions (Von .NET Core 2.1 unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.1 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

**.NET Core 2.0**

.NET Core 2.0 wird unter den folgenden 64-Bit-Verteilungen und -Versionen (`x86_64` oder`amd64`) von Linux unterstützt:

* Red Hat Enterprise Linux 7, 6
* CentOS 7
* Oracle Linux 7
* Fedora 27
* Debian 9, 8.7 oder höhere Versionen
* Ubuntu 18.04, 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 oder höhere Versionen
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 oder höher

Unter [.NET Core 2.0 Supported OS Versions (Von .NET Core 2.0 unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 28 (.NET Core 1.1), 27
* Debian 8.2 oder höhere Versionen
* Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04
* Linux Mint 17
* openSUSE 42.3 oder höhere Versionen (.NET Core 1.1)

Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

---

## <a name="linux-distribution-dependencies"></a>Abhängigkeiten der Linux-Distributionen

Bei folgenden Paketen handelt es sich um Beispiele. Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.

### <a name="ubuntu"></a>Ubuntu

Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* liblttng-ust0
* libcurl3
* libssl1.0.0
* libkrb5-3
* zlib1g
* libicu52 (für 14.X)
* libicu55 (für 16.X)
* libicu57 (für 17.X)
* libicu60 (für 18.X)

Für Versionen vor .NET Core 2.1 sind außerdem folgende Abhängigkeiten erforderlich:

* libunwind8
* libuuid1

### <a name="centos-and-fedora"></a>CentOS und Fedora

Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* lttng-ust
* libcurl
* openssl-libs
* krb5-libs
* libicu
* zlib

Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL höher als oder gleich 1.1 ist, müssen Sie „compat-openssl10“ installieren.

Für Versionen vor .NET Core 2.1 sind außerdem folgende Abhängigkeiten erforderlich:

* libunwind
* libuuid

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Eigenständige Linux-Anwendungen).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installieren der erforderlichen Abhängigkeiten für .NET Core mit nativen Installationsprogrammen

Native Installationsprogramme für .NET Core sind für unterstützte Linux-Distributionen und -Versionen verfügbar. Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server. Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden. Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.

Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete:

* Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.
* Das eigenständige Verwenden der Pakete, DEB oder RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Das Skripten von Installationen mit dem Installationsskript von .NET Core

Die [Dotnet-Installationsskripts](./tools/dotnet-install-script.md) werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können das Skript unter [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh) herunterladen.

Das Skript installiert standardmäßig die neueste Version von „LTS“, aktuell .NET Core 1.1. Zum Installieren von .NET Core 2.x führen Sie das Skript mit dem folgenden Switch aus:

```console
./dotnet-install.sh -c Current
```

Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet. Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>Installieren von .NET Core auf unterstützten Versionen von Red Hat Enterprise Linux (RHEL)

So installieren Sie .NET Core auf unterstützten RHEL-Versionen:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**.NET Core 2.1**

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Die neuesten Installationsinformationen zu .NET Core 2.1 auf Red Hat Enterprise Linux finden Sie unter [.NET Core 2.1 Getting Started Guide (Erste Schritte mit .NET Core 2.1)](https://access.redhat.com/documentation/en-us/net_core/2.1/html/getting_started_guide/)

**.NET Core 2.0**

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Die neuesten Installationsinformationen zu .NET Core 2.0 auf Red Hat Enterprise Linux finden Sie unter [.NET Core 2.0 Getting Started Guide (Erste Schritte mit .NET Core 2.0)](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/) 

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

|Runtimes/SDKs          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|.NET Core-Runtime 2.0.9  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.9)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.9)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.9)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.9)            |
|.NET Core-Runtime 2.0.8  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.8)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.8)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.8)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.8)            |
|.NET Core-Runtime 2.0.7  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.7)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.7)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.7)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.7)            |
|.NET Core-Runtime 2.0.6  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.6)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|.NET Core-Runtime 2.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.5)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|.NET Core SDK 2.1.202    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.202)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.202)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.202)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.202)            |
|.NET Core SDK 2.1.201    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.201)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.201)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.201)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.201)            |
|.NET Core SDK 2.1.200    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.200)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.200)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.200)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.200)            |
|.NET Core SDK 2.1.105    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.105)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.105)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.105)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.105)            |
|.NET Core SDK 2.1.103    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.103)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|.NET Core SDK 2.0.3      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.3)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |
|.NET Core SDK 2.0.0      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.0)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.0)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.0)          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.0)            |

**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 oder höher installieren](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), um .NET Core 2.1 mit Visual Studio verwenden zu können.

|Runtimes/SDKs          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|.NET Core-Runtime 2.1.2          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.2)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.2)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.2)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.2)            |
|.NET Core SDK 2.1.400     |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.400)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.400)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.400)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.400)            |
|.NET Core SDK 2.1.302     |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.302)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.302)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.302)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.302)            |
|.NET Core-Runtime 2.1.1          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.1)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.1)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.1)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.1)            |
|.NET Core SDK 2.1.301     |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.301)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.301)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.301)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.301)            |
|.NET Core-Runtime 2.1.0          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0)            |
|.NET Core SDK 2.1.300     |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300)|[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300)            |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300)            |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Verteilungen bzw. Versionen von Ubuntu und Linux Mint (64-Bit):

| Runtimes/SDKs         |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|.NET Core-Runtime 1.1.9  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.1.8  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.1.7  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.1.6  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.1.5  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.1.4  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.10 |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.9  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.8  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.7  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core-Runtime 1.0.4  |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.10     |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.9      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.8      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.7      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.5      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.4      |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-ubuntu-16.04-x64-binaries)            |[Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-ubuntu-14.04-x64-binaries)            |
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
|.NET Core-Runtime 2.0.9  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.9)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.9)   |
|.NET Core-Runtime 2.0.8  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.8)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.8)   |
|.NET Core-Runtime 2.0.7  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.7)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.7)   |
|.NET Core-Runtime 2.0.6  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|.NET Core-Runtime 2.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|.NET Core-Runtime 2.0.3  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.3)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.3)   |
|.NET Core-Runtime 2.0.0  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.0)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.0)   |
|.NET Core SDK 2.1.202    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.202)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.202)   |
|.NET Core SDK 2.1.201    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.201)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.201)   |
|.NET Core SDK 2.1.200    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.200)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.200)   |
|.NET Core SDK 2.1.105    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|.NET Core SDK 2.1.105    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|.NET Core SDK 2.1.104    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.104)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.104)   |
|.NET Core SDK 2.1.103    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|.NET Core SDK 2.1.102    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.102)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.102)   |
|.NET Core SDK 2.1.101    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.101)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.101)   |
|.NET Core SDK 2.0.3      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |
|.NET Core SDK 2.0.0      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.0)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.0)   |

**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 oder höher installieren](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), um .NET Core 2.1 mit Visual Studio verwenden zu können.

|Runtimes/SDKs                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|.NET Core-Runtime 2.1.2          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.2)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.2)   |
|.NET Core SDK 2.1.400        |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.400)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.400)        |
|.NET Core SDK 2.1.302        |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.302)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.302)        |
|.NET Core-Runtime 2.1.1          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.1)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.1)   |
|.NET Core SDK 2.1.301        |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.301)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.301)        |
|.NET Core-Runtime 2.1.0          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0)   |
|.NET Core SDK 2.1.300        |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300)   |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300)        |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x für Debian 9 oder Debian 8:

* .NET Core-Runtime 1.1.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.2 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-debian-x64-binaries)
* .NET Core-Runtime 1.1.0 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.0-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.10 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-debian-x64-binaries)
* .NET Core-Runtime 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-debian-x64-binaries)
* .NET Core SDK 1.1.10 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-debian-x64-binaries)
* .NET Core SDK 1.1.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-debian-x64-binaries)
* .NET Core SDK 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)
* .NET Core SDK 1.1.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-debian-x64-binaries)
* .NET Core SDK 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-debian-x64-binaries)
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
|.NET Core-Runtime 2.0.9  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.9)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.9)           |
|.NET Core-Runtime 2.0.8  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.8)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.8)           |
|.NET Core-Runtime 2.0.7  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.7)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.7)           |
|.NET Core-Runtime 2.0.6  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|.NET Core-Runtime 2.0.5  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|.NET Core-Runtime 2.0.3  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.3)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.3)           |
|.NET Core-Runtime 2.0.0  |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.0)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.0)           |
|.NET Core SDK 2.1.200    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.200)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.200)           |
|.NET Core SDK 2.1.105    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.105)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.105)           |
|.NET Core SDK 2.1.103    |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|.NET Core SDK 2.0.3      |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 oder höher installieren](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), um .NET Core 2.1 mit Visual Studio verwenden zu können.

|Runtimes/SDKs                  |Fedora 28          |Fedora 27             |
|---------------------------------|-------------------|----------------------|
|.NET Core-Runtime 2.1.2          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.2)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.2)           |
|.NET Core SDK 2.1.400          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.400)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.400)           |
|.NET Core SDK 2.1.302          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.302)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.302)           |
|.NET Core-Runtime 2.1.1          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.1)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.1)           |
|.NET Core SDK 2.1.301          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.301)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.301)           |
|.NET Core-Runtime 2.1.0          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.0)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0)           |
|.NET Core SDK 2.1.300          |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.300)       |[Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Versionen von Fedora (64-Bit):

**Fedora 24**

* .NET Core-Runtime 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.2 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-fedora-24-x64-binaries)
* .NET Core-Runtime 1.1.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5linux-fedora-24-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

**Fedora 23**

* .NET Core-Runtime 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-fedora-23-x64-binaries)
* .NET Core-Runtime 1.1.2 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-fedora-23-x64-binaries)
* .NET Core-Runtime 1.1.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-fedora-23-x64-binaries)
* .NET Core-Runtime 1.0.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)
* .NET Core-Runtime 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4linux-fedora-23-x64-binaries)
* .NET Core SDK 1.1.2 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.2linux-fedora-23-x64-binaries)
* .NET Core SDK 1.1.2 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.2linux-fedora-23-x64-binaries)
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

* .NET Core-Runtime 2.0.9 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.9)
* .NET Core-Runtime 2.0.8 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.8)
* .NET Core-Runtime 2.0.7 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.7)
* .NET Core-Runtime 2.0.6 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* .NET Core-Runtime 2.0.5 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)
* .NET Core-Runtime 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.3)
* .NET Core-Runtime 2.0.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.0)
* .NET Core SDK 2.1.202 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.202)
* .NET Core SDK 2.1.201 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.201)
* .NET Core SDK 2.1.200 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.200)
* .NET Core SDK 2.1.105 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.105)
* .NET Core SDK 2.1.104 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.104)
* .NET Core SDK 2.1.103 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)
* .NET Core SDK 2.1.102 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.102)
* .NET Core SDK 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)
* .NET Core SDK 2.0.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 oder höher installieren](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), um .NET Core 2.1 mit Visual Studio verwenden zu können.

* .NET Core-Runtime 2.1.2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.2)
* .NET Core SDK 2.1.400 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.400)
* .NET Core SDK 2.1.302 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.302)
* .NET Core-Runtime 2.1.1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.1)
* .NET Core SDK 2.1.301 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.301)
* .NET Core-Runtime 2.1.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0)
* .NET Core SDK 2.1.300 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Verteilungen bzw. Versionen von CentOS und Oracle Linux (64-Bit):

* .NET Core-Runtime 1.1.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.2 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-centos-x64-binaries)
* .NET Core-Runtime 1.1.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.12 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.12-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.11 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.11-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.10 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-centos-x64-binaries)
* .NET Core-Runtime 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-centos-x64-binaries)
* .NET Core SDK 1.1.10 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-centos-x64-binaries)
* .NET Core SDK 1.1.9 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-centos-x64-binaries)
* .NET Core SDK 1.1.8 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)
* .NET Core SDK 1.1.5 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-centos-x64-binaries)
* .NET Core SDK 1.1.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-centos-x64-binaries)
* .NET Core SDK 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>Installieren von .NET Core auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit)

So installieren Sie .NET Core 2.x auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit):

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 2.x auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit):

**.NET Core 2.0**

**SUSE Linux Enterprise Server**

* .NET Core-Runtime 2.0.9 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.9)
* .NET Core-Runtime 2.0.8 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.8)
* .NET Core-Runtime 2.0.7 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.7)
* .NET Core-Runtime 2.0.6 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.6)
* .NET Core-Runtime 2.0.5 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.5)
* .NET Core-Runtime 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.3)
* .NET Core-Runtime 2.0.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.0)
* .NET Core SDK 2.1.202 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.202)
* .NET Core SDK 2.1.201 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.201)
* .NET Core SDK 2.1.200 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.200)
* .NET Core SDK 2.1.105 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.105)
* .NET Core SDK 2.1.104 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.104)
* .NET Core SDK 2.1.103 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.103)
* .NET Core SDK 2.1.102 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.102)
* .NET Core SDK 2.1.101 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.101)
* .NET Core SDK 2.1.100 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.100)
* .NET Core SDK 2.1.4 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.4)
* .NET Core SDK 2.1.2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.2)
* .NET Core SDK 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.3)
* .NET Core SDK 2.0.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.0)

**openSUSE**

* .NET Core-Runtime 2.0.9 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.9)
* .NET Core-Runtime 2.0.8 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.8)
* .NET Core-Runtime 2.0.7 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.7)
* .NET Core-Runtime 2.0.6 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)
* .NET Core-Runtime 2.0.5 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)
* .NET Core-Runtime 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.3)
* .NET Core-Runtime 2.0.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.0)
* .NET Core SDK 2.1.202 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.202)
* .NET Core SDK 2.1.201 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.201)
* .NET Core SDK 2.1.200 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.200)
* .NET Core SDK 2.1.105 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.105)
* .NET Core SDK 2.1.103 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)
* .NET Core SDK 2.1.102 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.102)
* .NET Core SDK 2.1.101 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.101)
* .NET Core SDK 2.1.100 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.100)
* .NET Core SDK 2.1.4 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.4)
* .NET Core SDK 2.1.2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.2)
* .NET Core SDK 2.0.3 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)
* .NET Core SDK 2.0.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Sie müssen [Visual Studio 2017 15.7 oder höher installieren](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), um .NET Core 2.1 mit Visual Studio verwenden zu können.

**SUSE Linux Enterprise Server**

* .NET Core-Runtime 2.1.2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.2)
* .NET Core SDK 2.1.400 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.400)
* .NET Core SDK 2.1.302 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.302)
* .NET Core-Runtime 2.1.1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.1)
* .NET Core SDK 2.1.301 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.301)
* .NET Core-Runtime 2.1.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0)
* .NET Core SDK 2.1.300 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300)

**openSUSE**

* .NET Core-Runtime 2.1.2 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.2)
* .NET Core SDK 2.1.400 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.400)
* .NET Core SDK 2.1.302 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.302)
* .NET Core-Runtime 2.1.1 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.1)
* .NET Core SDK 2.1.301 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.301)
* .NET Core-Runtime 2.1.0 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0)
* .NET Core SDK 2.1.300 [Link zur Installation](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Installieren Sie .NET Core 1.x auf unterstützten Verteilungen bzw. Versionen von SUSE Linux Enterprise Server und OpenSUSE (64-Bit):

**SUSE Linux Enterprise Server 13.2**

* .NET Core-Runtime 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)
* .NET Core-Runtime 1.1.6 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)
* .NET Core SDK 1.1.7 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)
* .NET Core SDK 1.0.4 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-13.2-x64-binaries)
* .NET Core SDK 1.0.1 [Link zur Installation](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-13.2-x64-binaries)

---

## <a name="install-net-core-for-supported-alpine-linux-versions-64-bit"></a>Installieren von .NET Core auf unterstützten Versionen von Alpine Linux (64-Bit)

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

Laden Sie .NET Core 2.1 herunter, und führen Sie die Installationsanweisungen für unterstützte Alpine Linux-Versionen (64-Bit) unter den folgenden Links aus:

* .NET Core-Runtime 2.1.2 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.2-linux-x64-alpine-binaries)
* .NET Core SDK 2.1.400 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.400-linux-x64-alpine-binaries)
* .NET Core SDK 2.1.302 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.302-linux-x64-alpine-binaries)
* .NET Core-Runtime 2.1.1 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.1-linux-x64-alpine-binaries)
* .NET Core SDK 2.1.301 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.301-linux-x64-alpine-binaries)
* .NET Core-Runtime 2.1.0 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.0-linux-x64-alpine-binaries)
* .NET Core SDK 2.1.300 [Link zum Download](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.300-linux-x64-alpine-binaries)

> [!IMPORTANT]
> Weitere Informationen zu Problemen mit der Installation von .NET Core auf einer unterstützten Verteilung bzw. Version von Linux finden Sie in den folgenden Artikeln zu Ihrer installierte Verteilung bzw. Version:
> * [.NET Core 2.1 known issues (.NET Core 2.1 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [.NET Core 2.0 known issues (.NET Core 2.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [.NET Core 1.1 known issues (.NET Core 1.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [.NET Core 1.0 known issues (.NET Core 1.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0)
