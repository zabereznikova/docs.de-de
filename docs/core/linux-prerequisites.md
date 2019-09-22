---
title: Voraussetzungen für .NET Core unter Linux
description: Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 31c53b2cc0fe576e56685f4a5561258136fd2541
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71116591"
---
# <a name="prerequisites-for-net-core-on-linux"></a>Voraussetzungen für .NET Core unter Linux

Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux. Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:

* [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> Das .NET Core SDK-Paket ist für Produktionsserver und -Umgebungen nicht erforderlich. Für in Produktionsumgebungen bereitgestellte Apps ist nur das .NET Core-Runtime-Paket erforderlich. Die .NET Core-Runtime wird als Teil einer eigenständigen Bereitstellung mit Apps bereitgestellt, sie muss für frameworkabhängige, bereitgestellte Apps jedoch separat bereitgestellt werden. Weitere Informationen zu den frameworkabhängigen und eigenständigen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](./deploying/index.md). Außerdem finden Sie bestimmte Richtlinien unter [Self-contained Linux applications (Eigenständige Linux-Anwendungen)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

## <a name="supported-linux-versions"></a>Unterstützte Linux-Versionen

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x behandelt Linux als ein einzelnes Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen. 

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 2.2-Downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2) oder [.NET Core 2.1-Downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).

.NET Core 2.x wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

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

Unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) und [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.1 und .NET Core 2.2 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 1.1-Downloads](https://dotnet.microsoft.com/download/dotnet-core/1.1) oder [.NET Core 1.0-Downloads](https://dotnet.microsoft.com/download/dotnet-core/1.0).

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

# <a name="net-core-30-preview-1tabnetcore30"></a>[.NET Core 3.0 Vorschauversion 1](#tab/netcore30)

.NET Core 3.0 Vorschauversion 1 behandelt Linux als ein einziges Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen. 

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 3.0-Downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).

.NET Core 3.0 Vorschauversion 1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt. 

OS                            | Version               | Architekturen  
------------------------------|-----------------------|----------------
Red Hat Enterprise Linux      | 6                     | x64
Red Hat Enterprise Linux<br>CentOS<br>Oracle Linux  | 7                     | x64
Fedora                        | 28                    | x64
Debian                        | 9                     | x64, ARM32\*, ARM64\*
Ubuntu                        | 16.04+, 18.04+        | x64, ARM32\*, ARM64\*
Linux Mint                    | 18                    | x64
openSUSE                      | 42.3+                 | x64
SUSE Enterprise Linux (SLES)  | 12 SP2+               | x64
Alpine Linux                  | 3.8+                  | x64, ARM64

\* ARM32 und ARM64 unterstützen das Starten mit Debian 9 und Ubuntu 16.04. Frühere Versionen dieser Distributionen werden auf ARM-Chips nicht unterstützt.

Unter [.NET Core 3.0 Supported OS Versions (Von .NET Core 3.0 unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 3.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).

---

## <a name="linux-distribution-dependencies"></a>Abhängigkeiten der Linux-Distributionen

Bei folgenden Paketen handelt es sich um Beispiele. Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.

### <a name="ubuntu"></a>Ubuntu

Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* liblttng-ust0
* libcurl3 (für 14.x und 16.x)
* libcurl4 (für 18.x)
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

Die [Dotnet-Installationsskripts](./tools/dotnet-install-script.md) werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.

Das Skript installiert standardmäßig die neueste Version von „LTS“, aktuell .NET Core 1.1. Zum Installieren von .NET Core 2.1 führen Sie das Skript mit dem folgenden Switch aus:

```bash
./dotnet-install.sh -c Current
```

Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet. Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.

## <a name="troubleshoot"></a>Problembehandlung

Weitere Informationen zu Problemen mit der Installation von .NET Core auf einer unterstützten Verteilung bzw. Version von Linux finden Sie in den folgenden Artikeln zu Ihrer installierte Verteilung bzw. Version:

* [.NET Core 3.0 known issues (.NET Core 1.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [.NET Core 2.2 known issues (.NET Core 1.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [.NET Core 2.1 known issues (.NET Core 2.1 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [.NET Core 1.1 known issues (.NET Core 1.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [.NET Core 1.0 known issues (.NET Core 1.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0)
