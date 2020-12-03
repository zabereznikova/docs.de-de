---
ms.openlocfilehash: 83808f2f3a05333ed5d9e3809cbc2fd6e230d02c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031764"
---

[.Net Core ist im Snap Store verfügbar.](https://snapcraft.io/dotnet-sdk)

Ein Snap ist ein Bündel aus einer Anwendung und ihren Abhängigkeiten, das ohne Änderungen in vielen verschiedenen Linux-Distributionen funktioniert. Snaps sind über den Snap Store abrufbar und installierbar. Weitere Informationen zu Snap finden Sie unter [Erste Schritte mit Snap](https://snapcraft.io/docs/getting-started).

Nur unterstützte Versionen von .NET Core sind über Snap verfügbar.

### <a name="install-the-sdk"></a>Installieren des SDKs

Snap-Pakete für das .NET SDK werden alle unter demselben Bezeichner veröffentlicht: `dotnet-sdk`. Eine bestimmte Version des SDK kann durch Angabe des Kanals installiert werden. Das SDK enthält die entsprechende Runtime. In der folgenden Tabelle sind die Kanäle aufgeführt:

| .NET-Version | Snap-Paket             |
|--------------|--------------------------|
| 5.0          | `5.0` oder `latest/stable` |
| 3.1 (LTS)    | `3.1` oder `lts/stable`    |
| 2.1 (LTS)    | `2.1`                    |

Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für das .NET SDK zu installieren. Geben Sie mit dem Parameter `--channel` an, welche Version installiert werden soll. Bei Weglassen dieses Parameters wird `latest/stable` verwendet. In diesem Beispiel ist `5.0` angegeben:

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`. Sie können für `{alias}` einen beliebigen Namen auswählen. Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-sdk.dotnet dotnet50`. Beim Verwenden des Befehls `dotnet50` rufen Sie diese spezifische Version von .NET auf. Diese ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.

### <a name="install-the-runtime"></a>Installieren der Runtime

Snap-Pakete für die .NET Core-Runtime werden mit jeweils eigenem Paketbezeichner veröffentlicht. In der folgenden Tabelle sind die Paketbezeichner aufgeführt:

| .NET-Version      | Snap-Paket        |
|-------------------|---------------------|
| 5.0               | `dotnet-runtime-50` |
| 3.1 (LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2.1 (LTS)         | `dotnet-runtime-21` |

Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für die .NET-Runtime zu installieren. In diesem Beispiel wird .NET 5.0 installiert:

```bash
sudo snap install dotnet-runtime-50 --classic
```

Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`. Sie können für `{alias}` einen beliebigen Namen auswählen. Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`. Beim Verwenden des Befehls `dotnet50` rufen Sie diese spezifische Version von .NET auf. Diese ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.

### <a name="ssl-certificate-errors"></a>SSL-Zertifikatfehler

Wenn .NET über Snap installiert wird, ist es möglich, dass bei einigen Distributionen die SSL-Zertifikate für .NET nicht gefunden werden und Sie während `restore` einen Fehler ähnlich dem folgenden erhalten:

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

Zur Behebung dieses Problems müssen Sie einige Umgebungsvariablen festlegen:

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

Der Speicherort des Zertifikats variiert je nach Distribution. Hier finden Sie die Speicherorte für die Distributionen, in denen das Problem aufgetreten ist.

* Fedora: `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
* OpenSUSE: `/etc/ssl/ca-bundle.pem`
* Solus: `/etc/ssl/certs/ca-certificates.crt`
