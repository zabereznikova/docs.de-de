---
title: Entfernen von .NET Core Runtime und SDK
description: In diesem Artikel wird beschrieben, wie Sie feststellen können, welche Versionen von .NET Core Runtime und SDK derzeit installiert sind, und wie Sie sie unter Windows, Mac und Linux entfernen.
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 82fbccdec0323b54d313960279fcbfeeb6033319
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920400"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Entfernen von .NET Core-Runtime und SDK

Wenn Sie im Laufe der Zeit aktualisierte Versionen der .NET Core-Runtime und des SDK installieren, sollten Sie veraltete .NET Core-Versionen von Ihrem Computer entfernen. Durch das Entfernen älterer Runtime-Versionen ändert sich möglicherweise die für die Ausführung der freigegebenen Frameworkanwendungen ausgewählte Runtime. Dies wird im Artikel zu [Auswahl von .NET Core-Versionen](selection.md) ausführlich beschrieben.

## <a name="should-i-remove-a-version"></a>Sollte ich eine Version entfernen?

Durch das Verhalten bei der [.NET Core-Versionsauswahl](selection.md) und die Laufzeitkompatibilität von .NET Core zwischen Updates können frühere Versionen sicher entfernt werden. Updates für die .NET Core-Runtime sind innerhalb des „Bereichs“ einer Hauptversion kompatibel, wie z.B. 1.x und 2.x. Darüber hinaus können in neueren Versionen des .NET Core SDK in der Regel Anwendungen erstellt werden, die mit früheren Versionen der Laufzeit kompatibel sind.

Im Allgemeinen benötigen Sie nur das neueste SDK und die neueste Patchversion der Laufzeiten, die für Ihre Anwendung erforderlich sind. Instanzen mit älteren SDK- oder Runtimeversionen beinhalten die Verwaltung von auf **project.json** basierenden Anwendungen. Sie können ältere Versionen sicher entfernen, wenn Ihre Anwendung keine bestimmten Gründe für frühere SDKs oder Laufzeiten aufweist.

## <a name="determine-what-is-installed"></a>Feststellen, was installiert ist

Ab .NET Core 2.1 verfügt die .NET-CLI über Optionen, mit denen Sie die auf Ihrem Computer installierten Versionen des SDK und der Runtime auflisten können.  Verwenden Sie [`dotnet --list-sdks`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten SDKs. Verwenden Sie [`dotnet --list-runtimes`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten Runtimes. Der folgende Text zeigt eine typische Ausgabe für Windows, macOS oder Linux:

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[macOS](#tab/macos)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

---

## <a name="uninstall-net-core"></a>Deinstallieren von .NET Core

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

.NET Core entfernt über das Windows-Dialogfeld **Programme hinzufügen/entfernen** Versionen der .NET Core-Runtime und des SDK. Die folgende Abbildung zeigt das Dialogfeld **Programme hinzufügen/entfernen** mit mehreren installierten Versionen der .NET-Runtime und des SDK.

![Hinzufügen/Entfernen von Programmen zum Entfernen von .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Wählen Sie sämtliche Versionen aus, die Sie von Ihrem Computer entfernen möchten, und klicken Sie auf **Deinstallieren**.

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

Für die Deinstallation von .NET Core (Runtime oder SDK) unter Linux gibt es weitere Optionen. Die beste Möglichkeit zur Deinstallation von .NET Core besteht in der Spiegelung der für die Installation von .NET Core verwendeten Aktion. Die Details hängen davon ab, welche Verteilung und Installationsmethode Sie auswählen.

> [!IMPORTANT]
> Informationen zur Installation und Deinstallation von .NET Core unter Red Hat finden Sie im [Leitfaden für erste Schritte von Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).

Ab .NET Core 2.1 muss das .NET Core SDK nicht mehr deinstalliert werden, wenn mithilfe eines Paket-Managers ein Upgrade durchgeführt wird. Mit dem Befehl `update` oder `refresh` des Paket-Managers werden die älteren Versionen nach erfolgreicher Installation einer neueren Version automatisch entfernt.

Wenn Sie .NET Core mithilfe eines Paket-Managers installiert haben, können Sie für die Deinstallation des .NET SDK oder der -Runtime denselben Paket-Manager verwenden. .NET Core-Installationen unterstützen die am häufigsten verwendeten Paket-Manager. In der Dokumentation zu dem Paket-Manager Ihrer Verteilung finden Sie die genaue Syntax in Ihrer Umgebung:

- [apt-get(8)](https://linux.die.net/man/8/apt-get) wird von Debian-basierten Systemen, einschließlich Ubuntu, verwendet.
- [yum(8)](https://linux.die.net/man/8/yum) wird unter Fedora, CentOS und Oracle Linux verwendet.
- [zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) wird unter openSUSE und SUSE Linux Enterprise System (SLES) verwendet.
- [dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) wird unter Fedora verwendet.

In fast allen Fällen lautet der Befehl zum Entfernen eines Pakets `remove`.

Der Paketname für die .NET Core SDK-Installation lautet bei den meisten Paket-Managern `dotnet-sdk`, gefolgt von der Versionsnummer. Ab Version 2.1.300 des .NET Core SDK und Version `2.1` der Runtime sind nur die Nummern der Haupt-und Nebenversionen erforderlich: So kann beispielsweise mit dem Paket `dotnet-sdk-2.1` auf Version 2.1.300 des .NET Core SDK verwiesen werden. Bei früheren Versionen ist die gesamte Versionszeichenfolge erforderlich: Für Version 2.1.200 des .NET Core SDK wäre z.B. `dotnet-sdk-2.1.200` erforderlich.

Bei Computern, auf denen nur die Runtime und nicht das SDK installiert ist, lautet der Paketname für die .NET Core-Runtime `dotnet-runtime-<version>` und für den gesamten Laufzeitstapel `aspnetcore-runtime-<version>`.

Bei .NET Core-Installationen vor Version 2.0 wurde die Hostanwendung nicht deinstalliert, wenn das SDK mit dem Paket-Manager deinstalliert wurde. Bei Verwendung von `apt-get` lautet der Befehl wie folgt:

```bash
apt-get remove dotnet-host
```

Beachten Sie, dass keine Version an `dotnet-host` angefügt ist.

Wenn Sie die Installation mit einem Tarball durchgeführt haben, müssen Sie .NET Core manuell entfernen.

Die SDKs und Runtimes werden separat entfernt, indem das Verzeichnis entfernt wird, das diese Version enthält. Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Unter Mac müssen die SDKs und Runtimes separat entfernt werden, indem das Verzeichnis entfernt wird, das diese Version enthält. Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.

---

## <a name="net-core-uninstall-tool"></a>.NET Core-Deinstallationstool

Mit dem [.NET Core-Deinstallationstool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und .NET Core-Runtimes aus einem System entfernen. Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, um anzugeben, welche Versionen deinstalliert werden sollen.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Visual Studio-Abhängigkeit von .NET Core SDK Versionen

Vor Visual Studio 2019 Version 16.3 haben Visual Studio-Installer den eigenständigen .NET Core SDK-Installer aufgerufen. Folglich werden die SDK-Versionen im Dialogfeld Windows-Dialogfeld **Software** angezeigt. Das Entfernen von .Core SDKs, die von Visual Studio mit dem eigenständigen Installer installiert wurden, kann dazu führen, dass Visual Studio nicht mehr funktioniert. Wenn in Visual Studio nach der Deinstallation von SDKs Probleme auftreten, führen Sie „Reparieren“ für diese bestimmte Version von Visual Studio aus. In der folgenden Tabelle werden einige der Visual Studio-Abhängigkeiten von .NET Core SDK-Versionen gezeigt:

| Visual Studio-Version | .NET Core SDK-Version |
| -- | -- |
| Visual Studio 2019 Version 16.2 | .NET Core SDK 2.2.4xx, 2.1.8xx |
| Visual Studio 2019 Version 16.1 | .NET Core SDK 2.2.3xx, 2.1.7xx |
| Visual Studio 2019, Version 16.0 | .NET Core SDK 2.2.2xx, 2.1.6xx |
| Visual Studio 2017 Version 15.9 | .NET Core SDK 2.2.1xx, 2.1.5xx |
| Visual Studio 2017 Version 15.8 | .NET Core SDK 2.1.4xx |

Ab Visual Studio 2019, Version 16.3, verwaltet Visual Studio eine eigene Kopie des .NET Core SDK. Aus diesem Grund werden diese SDK-Versionen nicht mehr im Dialogfeld **Software** angezeigt.

## <a name="remove-the-nuget-fallback-folder"></a>Entfernen des NuGet-Fallbackordners

Vor dem .NET Core 3.0 SDK verwendeten die .NET Core SDK-Installer den Ordner *NuGetFallbackFolder-*, um einen Cache mit NuGet-Paketen zu speichern. Dieser Cache wurde bei Vorgängen wie `dotnet restore` oder `dotnet build /t:Restore`verwendet. `NuGetFallbackFolder` befindet sich unter Windows unter *C:\Programme\dotnet\sdk* und unter macOS unter */usr/local/share/dotnet/sdk*.

Möglicherweise möchten Sie diesen Ordner entfernen, wenn Folgendes zutrifft:

* Sie entwickeln nur mit dem .NET Core 3.0 SDK oder höheren Versionen.
* Sie entwickeln mit .NET Core SDK-Versionen vor 3.0, können aber online arbeiten, und Geschwindigkeit ist nicht immer wichtig.

Wenn Sie den NuGet-Fallbackordner entfernen möchten, können Sie ihn löschen, aber hierfür benötigen Sie Administratorberechtigungen.

Es wird nicht empfohlen, den Ordner *dotnet* zu löschen. Dadurch würden Sie alle globalen Tools entfernen, die Sie zuvor installiert haben. Unter Windows gilt außerdem:

- Sie verlieren die Funktionalität von Visual Studio 2019 Version 16.3 und höheren Versionen. Zum Wiederherstellen können Sie **Reparieren** ausführen.
- Wenn .NET Core SDK-Einträge im Dialogfeld **Software** angezeigt werden, sind sie verwaist.
