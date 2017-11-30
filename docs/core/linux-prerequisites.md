---
title: "Voraussetzungen für .NET Core unter Linux"
description: "Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 04fdf26e150e6d489c0641588563f69f24835615
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-linux"></a>Voraussetzungen für .NET Core unter Linux

Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux. Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:

* [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Unterstützte Linux-Versionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.0 behandelt Linux als ein einziges Betriebssystem. Es gibt einen einzelnen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Distributionen.

.NET Core 2.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:

 * Red Hat Enterprise Linux 7
 * CentOS 7
 * Oracle Linux 7
 * Fedora 25, Fedora 26
 * Debian 8.7 oder höhere Versionen 
 * Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04
 * Linux Mint 18, Linux Mint 17
 * openSUSE 42.2 oder höhere Versionen
 * SUSE Enterprise Linux (SLES) 12 SP2 oder höhere Versionen

Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 24
* Debian 8.2 oder höhere Versionen
* Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*
 * Ubuntu 16.10 wird vom neuesten Patchrelease von .NET Core 1.1 unterstützt.
* Linux Mint 17
* openSUSE 42.1 oder höhere Versionen (.NET Core 1.1)

Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

---

## <a name="linux-distribution-dependencies"></a>Abhängigkeiten der Linux-Distributionen

Die folgenden Beispiele werden vorgesehen. Die exakte Version und den Namen können Ihrer Linux-Distribution Wahl leicht variieren.

### <a name="ubuntu"></a>Ubuntu

Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* libunwind8
* Liblttng ust0
* libcurl3
* libssl1.0.0
* libuuid1
* libkrb5
* zlib1g
* libicu52 (für 14.X)
* libicu55 (für 16.X)
* libicu57 (für 17.X)

### <a name="centos"></a>CentOS

Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

* libunwind
* Lttng ust
* libcurl
* OpenSSL-Bibliotheken
* libuuid3LIB
* KRB5-Bibliotheken
* libicu
* zlib

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Eigenständige Linux-Anwendungen).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installieren der erforderlichen Abhängigkeiten für .NET Core mit nativen Installationsprogrammen

Native Installationsprogramme für .NET Core sind für unterstützte Linux-Distributionen und -Versionen verfügbar. Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server. Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden. Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.

Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete:

* Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.
* Das eigenständige Verwenden der Pakete, DEB oder RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Das Skripten von Installationen mit dem Installationsskript von .NET Core

Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können das Skript herunterladen: https://dot.net/v1/dotnet-install.sh

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
4. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

     ```bash
     dotnet --version
     ```

Weitere Informationen zur Registrierung des Kanalzugriffs von Red Hat .NET finden Sie im Abschnitt „Red Hat“ in [Kapitel 1 des Leitfadens für erste Schritte mit .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/).

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a>Installieren von .NET Core für Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 und Linux Mint 17, Linux Mint 18 (64 Bit)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registrieren Sie den Microsoft-Produktschlüssel als vertrauenswürdig.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. Richten Sie die gewünschte Version des Hostpaketfeeds ein.

   **Ubuntu 17.04**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 16.04 / Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 14.04 / Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. Installieren Sie .NET Core.

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Richten Sie die gewünschte Version des Hostpaketfeeds ein.

   **Ubuntu 16.10**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  **Ubuntu 16.04 / Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   **Ubuntu 14.04 / Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. Installieren Sie .NET Core 1.x auf Ubuntu oder Linux Mint:

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a>Installieren von .NET Core für Debian 8 oder Debian 9 (64 Bit)

So installieren Sie .NET Core für Debian 8 oder Debian 9 (64 Bit):

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Installieren Sie Systemkomponenten.

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. Registrieren Sie den vertrauenswürdigen Microsoft-Produktschlüssel.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. Registrieren Sie den Microsoft-Produktfeed.

   **Debian 9 (Stretch)**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   **Debian 8 (Jessie)**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. Installieren Sie das .NET Core-SDK.

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Beschaffen Sie die erforderlichen Komponenten.

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. Laden Sie die .NET Core SDK Binärdateien (Tarball) herunter.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. Extrahieren Sie die .NET Core SDK Binärdateien.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a>Installieren von .NET Core für Fedora 24, Fedora 25 oder Fedora 26 (64 Bit)

So installieren Sie .NET Core 2.x unter Fedora 26 oder Fedora 25, oder .NET Core 1.x unter Fedora 24

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 oder Fedora 25**

2. Registrieren Sie den Microsoft-Signaturschlüssel.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Fügen Sie den Dotnet-Produktfeed hinzu.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Installieren Sie das .NET Core-SDK.

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

2. Beschaffen Sie die erforderlichen Komponenten.

   ```bash
   sudo dnf install libunwind libicu
   ```

3. Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. Extrahieren Sie die .NET Core SDK Binärdateien.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Installieren von .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit)

So installieren Sie .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registrieren Sie den Microsoft-Signaturschlüssel.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Fügen Sie den Microsoft-Produktfeed hinzu.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Installieren Sie das .NET Core-SDK.

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. Fügen Sie dotnet Ihrem Pfad hinzu.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Beschaffen Sie die erforderlichen Komponenten.

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. Extrahieren Sie die .NET Core SDK Binärdateien.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a>Installieren von .NET Core für SUSE Linux Enterprise Server (64 Bit)

So installieren Sie .NET Core 2.x für SUSE Linux Enterprise Server (SLES) 12 SP2 (64 Bit)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

2. Fügen Sie den Dotnet-Produktfeed hinzu.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. Installieren Sie das .NET Core-SDK.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a>Installieren von .NET Core für openSUSE (64 Bit)

So installieren Sie .NET Core 2.x für openSUSE oder .NET Core 1.x für openSUSE (64 Bit)

1. Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.

> [!NOTE]
> Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registrieren Sie den Microsoft-Signaturschlüssel.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Fügen Sie den Dotnet-Produktfeed hinzu.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. Installieren Sie das .NET Core-SDK.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Beschaffen Sie die erforderlichen Komponenten.

   ```bash
   sudo zypper install libunwind libicu
   ```

3. Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. Extrahieren Sie die .NET Core SDK Binärdateien.
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Fügen Sie dotnet zu Ihrem Pfad hinzu.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> Weitere Informationen zu Problemen mit der Installation von .NET Core 2.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie im Thema [2.0 Known issues (2.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) für Ihre installierte Verteilung oder Version. 
>
> Weitere Informationen zu Problemen mit der Installation von .NET Core 1.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie in den Themen [1.0.0 Known issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) für Ihre installierte Verteilung oder Version.
