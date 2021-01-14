---
title: 'Installieren von .NET unter Linux mithilfe von Snap: .NET'
description: In diesem Artikel wird veranschaulicht, wie Sie das .NET SDK oder die .NET-Runtime unter Linux mithilfe von Snap installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 741933b5ca6f01d73b388675fe7f8a43c4efb0f9
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970924"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a>Installieren des .NET SDK oder der .NET-Runtime mithilfe von Snap

Verwenden Sie ein Snap-Paket, um das .NET SDK oder die .NET-Runtime zu installieren. Snaps stellen eine gute Alternative zum in Ihre Linux-Distribution integrierten Paket-Manager dar. In diesem Artikel wird beschrieben, wie Sie .NET mithilfe von [Snap](https://snapcraft.io/dotnet-sdk) installieren.

Ein Snap ist ein Bündel aus einer Anwendung und ihren Abhängigkeiten, das ohne Änderungen in vielen verschiedenen Linux-Distributionen funktioniert. Snaps sind über den Snap Store abrufbar und installierbar. Weitere Informationen zu Snap finden Sie unter [Erste Schritte mit Snap](https://snapcraft.io/docs/getting-started).

> [!CAUTION]
> Snap-Pakete werden in WSL2 unter Windows 10 nicht unterstützt. Verwenden Sie alternativ das [`dotnet-install`-Skript](linux-scripted-manual.md#scripted-install) oder den Paket-Manager für die jeweilige WSL2-Distribution. Es ist nicht empfehlenswert, jedoch können Sie versuchen, Snap mit einer [nicht unterstützten Problemumgehung aus den Snapcraft-Foren](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033) zu aktivieren.

## <a name="net-releases"></a>.NET-Releases

Nur ✔️ unterstützte Versionen des .NET SDK sind über Snap verfügbar. Alle Versionen der .NET-Runtime sind ab Version 2.1 über Snap verfügbar. In der folgenden Tabelle sind die Versionen von .NET (und .NET Core) aufgelistet:

| ✔️ Unterstützt | ❌ Nicht unterstützt |
|-------------|---------------|
| 5.0         | 3.0           |
| 3.1 (LTS)   | 2.2           |
| 2.1 (LTS)   | 2.0           |
|             | 1.1           |
|             | 1.0           |

Weitere Informationen zum Lebenszyklus von .NET-Versionen finden Sie in der [Richtlinie zur Unterstützung von .NET Core und .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="sdk-or-runtime"></a>SDK oder Runtime

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a>Installieren des SDK

Snap-Pakete für das .NET SDK werden alle unter demselben Bezeichner veröffentlicht: `dotnet-sdk`. Eine bestimmte Version des SDK kann durch Angabe des Kanals installiert werden. Das SDK enthält die entsprechende Runtime. In der folgenden Tabelle sind die Kanäle aufgeführt:

| .NET-Version | Snap-Paket oder -Kanal  |
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

Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`. Sie können für `{alias}` einen beliebigen Namen auswählen. Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-sdk.dotnet dotnet50`. Beim Verwenden des Befehls `dotnet50` rufen Sie diese spezifische Version von .NET auf. Die Auswahl eines anderen Alias ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verwendet wird.

## <a name="install-the-runtime"></a>Installieren der Runtime

Snap-Pakete für die .NET-Runtime werden mit jeweils eigenem Paketbezeichner veröffentlicht. In der folgenden Tabelle sind die Paketbezeichner aufgeführt:

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

Der Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`. Sie können für `{alias}` einen beliebigen Namen auswählen. Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`. Beim Verwenden des Befehls `dotnet50` rufen Sie eine spezifische Version von .NET auf. Die Auswahl eines anderen Alias ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.

## <a name="tlsssl-certificate-errors"></a>TLS/SSL-Zertifikatfehler

Wenn .NET über Snap installiert wird, ist es möglich, dass bei einigen Distributionen die TLS/SSL-Zertifikate für .NET nicht gefunden werden und während `restore` eine Fehlermeldung angezeigt wird:

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

Zum Lösen dieses Problems müssen Sie einige Umgebungsvariablen festlegen:

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

Der Speicherort des Zertifikats variiert je nach Distribution. Hier finden Sie die Speicherorte für die Distributionen, in denen das Problem aufgetreten ist.

| Distribution | Standort                                            |
|--------------|-----------------------------------------------------|
| **Fedora**   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| **OpenSUSE** | `/etc/ssl/ca-bundle.pem`                            |
| **Solus**    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI](../tools/enable-tab-autocomplete.md)
- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
