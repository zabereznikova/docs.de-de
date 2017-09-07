---
title: "Voraussetzungen für .NET Core unter Linux"
description: "Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS
author: johalex
ms.author: johalex
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: c30888895275ce18628ea341fee2d5a77080b8f6
ms.openlocfilehash: ff2b85372208e76c6c3becb551c41cdfb275d272
ms.contentlocale: de-de
ms.lasthandoff: 08/28/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Voraussetzungen für .NET Core unter Linux

Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux. Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:

* [Befehlszeile](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Unterstützte Linux-Versionen

.NET Core 2.x wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

 * Red Hat Enterprise Linux 7 x64
 * CentOS 7 x64
 * Oracle Linux 7 x64
 * Fedora 25, 26 x64
 * Debian 9, 8.7+ x64 
 * Ubuntu 17.04, 16.04, 14.04  x64
 * Linux Mint 18, 17 x64
 * openSUSE 42.2+ x64
 * SUSE Enterprise Linux (SLES) 12 SP2+ x64

.NET Core 1.x wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

* Red Hat Enterprise Linux / CentOS / Oracle Linux 7 x64
* Fedora 24 x64
* Debian 8.2+ x64
* Ubuntu / Linux Mint 14.04, 16.04, 16.10*, 17 x64
* openSUSE 42.1 (1.1) x64
> [!NOTE]
> Ubuntu/Linux 16.10 wird von der neuesten Patchversion von .NET Core 1.1 unterstützt.

Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.
## <a name="linux-distribution-dependencies"></a>Abhängigkeiten der Linux-Verteilungen
### <a name="ubuntu"></a>Ubuntu
Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* libunwind8
* libunwind8-dev
* gettext
* libicu-dev
* liblttng-ust-dev
* libcurl4-openssl-dev
* libssl-dev
* uuid-dev
* unzip

### <a name="centos"></a>CentOS
Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:
* deltarpm
* epel-release
* unzip
* libunwind
* gettext
* libcurl-devel
* openssl-devel
* zlib
* libicu-devel

## <a name="installing-net-core-prerequisites-with-the-native-installers"></a>Installieren der erforderlichen Komponenten für .NET Core mit nativen Installationsprogrammen

Native Installationsprogramme für .NET Core sind für unterstützte Linux-Verteilungen und -Versionen verfügbar. Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server. Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden. Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.

Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete: 
* Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.
* Das eigenständige Verwenden der Pakete, DEB oder RPM. 

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Das Skripten von Installationen mit dem Installationsskript von .NET Core 

Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können die Skripts aus dem [CLI-GitHub-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain) herunterladen. 

Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet. Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.

> [!IMPORTANT]
> Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a>Installieren von .NET Core auf Red Hat Enterprise Linux 7 (RHEL)

Installieren von .NET Core auf RHEL 7:

1. Aktivieren Sie den Red Hat .NET-Kanal, der in Ihrem Abonnement für RHEL 7 verfügbar ist.
    * Verwenden Sie Folgendes für den Red Hat Enterprise 7-Server:
         ```bash
        subscription-manager repos --enable=rhel-7-server-dotnet-rpms
        ```
    * Verwenden Sie Folgendes für die Red Hat Enterprise 7-Arbeitsstation:
         ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
        ```
    * Verwenden Sie Folgendes für den Red Hat Enterprise 7-HPC-Berechnungsknoten:
         ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. Installieren Sie das SCL-Tool.
    ```bash
    yum install scl-utils
    ```
3. Installieren Sie .NET Core.
# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Installieren des .NET Core 2.0 SDKs und der Runtime:
```bash
yum install rh-dotnet20
```
Aktivieren des .NET Core 2.0 SDKs und der Runtime für Ihre Umgebung:
```bash
scl enable rh-dotnet20 bash
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

Installieren des .NET Core 1.1 SDKs und der Runtime:
```bash
yum install rh-dotnetcore11
```
Aktivieren der .NET Core 1.1 SDKs und der Runtime für Ihre Umgebung:
```bash
scl enable rh-dotnetcore11 bash
```

**.NET Core 1.0**

Installieren des .NET Core 1.0 SDKs und der Runtime:
```bash
yum install rh-dotnetcore10
```
Aktivieren des .NET Core 1.0 SDKs und der Runtime für Ihre Umgebung:
```bash
scl enable rh-dotnetcore10 bash
```
---
4. Führen Sie den Befehl `dotnet --help` aus, um zu überprüfen, dass die Installation erfolgreich war.

     ```bash
     dotnet --help
     ```
> [!NOTE]
> Weitere Informationen zur Registrierung des Kanalzugriffs von Red Hat .NET finden Sie im Abschnitt „Red Hat“ in [Kapitel 1 des Leitfadens für erste Schritte mit .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/).


## <a name="install-net-core-for-ubuntu-1404-1604-1610--linux-mint-17-18-64-bit"></a>Installieren von .NET Core für Ubuntu 14.04, 16.04, 16.10 und Linux Mint 17, 18 (64 Bit)

> [!Warning]
> Bevor Sie beginnen, entfernen Sie alle früheren Versionen von .NET Core von Ihrem System.

### <a name="add-the-dotnet-apt-get-feed"></a>Hinzufügen des dotnet-Feeds „apt-get“

1. Richten Sie die gewünschte Version des Hostpaketfeeds ein.

   **Ubuntu 14.04 / Linux Mint 17**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.04 / Linux Mint 18**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.10**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
2. Installieren Sie .NET Core.
# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Installieren Sie .NET Core 2.0 unter Ubuntu oder Linux Mint, nachdem Sie den Hostpaketfeed eingerichtet haben:
```bash
sudo apt-get install dotnet-sdk-2.0.0
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Installieren Sie .NET Core 1.x unter Ubuntu oder Linux Mint, nachdem Sie den Hostpaketfeed eingerichtet haben:
```bash
sudo apt-get install dotnet-dev-1.0.4
```
---
3. Führen Sie den Befehl `dotnet --help` aus, um zu überprüfen, dass die Installation erfolgreich war.

 ```bash
     dotnet --help
 ```
## <a name="install-net-core-for-debian-8-or-9-64-bit"></a>Installieren von .NET Core für Debian 8 oder 9 (64 Bit).

> [!Warning]
> Bevor Sie beginnen, entfernen Sie alle früheren Versionen von .NET Core von Ihrem System.

Installieren von .NET Core für Debian 8 oder 9 (64 Bit):
1. Beschaffen Sie die erforderlichen Komponenten. 
    ```bash
    sudo apt-get install curl libunwind8 gettext
    ```
2. Laden Sie die .NET Core SDK Binärdateien (Tarball) herunter.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)   

```bash
     curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)   

```bash
     curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
```
---
3. Extrahieren Sie die .NET Core SDK Binärdateien.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Fügen Sie dotnet zu Ihrem Pfad hinzu.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Führen Sie den Befehl `dotnet --help` aus, um zu überprüfen, dass die Installation erfolgreich war.

     ```bash
     dotnet --help
     ```

## <a name="install-net-core-for-fedora-24-25-or-26-64-bit"></a>Installieren von .NET Core für Fedora 24, 25 oder 26 (64 Bit)

> [!Warning]
> Bevor Sie beginnen, entfernen Sie alle früheren Versionen von .NET Core von Ihrem System.

Installieren von .NET Core für Fedora 26, 25 (.NET Core 2.x) oder 24 (.NET Core 1.x): 
1. Beschaffen Sie die erforderlichen Komponenten. 
    ```bash
    sudo dnf install libunwind libicu
    ```
2. Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 or 25**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
```

---
3. Extrahieren Sie die .NET Core SDK Binärdateien.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Fügen Sie dotnet zu Ihrem Pfad hinzu.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Führen Sie den Befehl `dotnet --help` aus, um zu überprüfen, dass die Installation erfolgreich war.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Installieren von .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit)

> [!Warning]
> Bevor Sie beginnen, entfernen Sie alle früheren Versionen von .NET Core von Ihrem System.

Installieren von .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit):

1. Beschaffen Sie die erforderlichen Komponenten.
    ```bash
    sudo dnf install libunwind libicu
    ```
2. Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
```

---
3. Extrahieren Sie die .NET Core SDK Binärdateien.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Fügen Sie dotnet zu Ihrem Pfad hinzu.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Führen Sie den Befehl `dotnet --help` aus, um zu überprüfen, dass die Installation erfolgreich war.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit-net-core-2x-and-opensuse-64-bit"></a>Installieren von .NET Core für SUSE Linux Enterprise Server (64-Bit) (.NET Core 2.x) und openSUSE (64 Bit)

> [!Warning]
> Bevor Sie beginnen, entfernen Sie alle früheren Versionen von .NET Core von Ihrem System.

Installieren von .NET Core für SUSE Linux Enterprise Server (SLES) 12 SP2 (64 Bit) und openSUSE 42.2 auf NET Core 2.x oder openSUSE 42.1 (64 Bit) auf .NET Core 1.x:

1. Beschaffen Sie die erforderlichen Komponenten.
    ```bash
    sudo zypper install libunwind libicu
    ```
2. Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**SLES 12 SP2, openSUSE 42.2**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**openSUSE 42.1**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
```

---
3. Extrahieren Sie die .NET Core SDK Binärdateien.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Fügen Sie dotnet zu Ihrem Pfad hinzu.
    ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Führen Sie den Befehl `dotnet --help` aus, um zu überprüfen, dass die Installation erfolgreich war.

     ```bash
     dotnet --help
     ```

> [!IMPORTANT]
> Weitere Informationen zu Problemen mit der Installation von .NET Core 2.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie im Thema [2.0 Known issues (2.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) für Ihre installierte Verteilung oder Version.
> [!IMPORTANT]
> Weitere Informationen zu Problemen mit der Installation von .NET Core 1.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie in den Themen [1.0.0 Known issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) für Ihre installierte Verteilung oder Version.
