---
title: Entfernen von .NET Core Runtime und SDK
description: In diesem Artikel wird beschrieben, wie Sie feststellen können, welche Versionen von .NET Core Runtime und SDK derzeit installiert sind, und wie Sie sie unter Windows, Mac und Linux entfernen.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: f1482c243ba22fa81c69ede847a0f6b36a9cb83c
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595762"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Entfernen von .NET Core-Runtime und SDK

Wenn Sie im Laufe der Zeit aktualisierte Versionen der .NET Core-Runtime und des SDK installieren, sollten Sie veraltete .NET Core-Versionen von Ihrem Computer entfernen. Durch das Entfernen älterer Runtime-Versionen ändert sich möglicherweise die für die Ausführung der freigegebenen Frameworkanwendungen ausgewählte Runtime. Dies wird im Artikel zu [Auswahl von .NET Core-Versionen](../versions/selection.md) ausführlich beschrieben.

## <a name="should-i-remove-a-version"></a>Sollte ich eine Version entfernen?

Durch das Verhalten bei der [.NET Core-Versionsauswahl](../versions/selection.md) und die Laufzeitkompatibilität von .NET Core zwischen Updates können frühere Versionen sicher entfernt werden. Updates für die .NET Core-Runtime sind innerhalb des „Bereichs“ einer Hauptversion kompatibel, wie z.B. 1.x und 2.x. Darüber hinaus können in neueren Versionen des .NET Core SDK in der Regel Anwendungen erstellt werden, die mit früheren Versionen der Laufzeit kompatibel sind.

Im Allgemeinen benötigen Sie nur das neueste SDK und die neueste Patchversion der Laufzeiten, die für Ihre Anwendung erforderlich sind. Instanzen, auf denen ältere SDK-Versionen oder Runtimeversionen verwendet werden sollten, beinhalten die Verwaltung von auf *project.json* basierenden Anwendungen. Sie können ältere Versionen sicher entfernen, wenn Ihre Anwendung keine bestimmten Gründe für frühere SDKs oder Laufzeiten aufweist.

## <a name="determine-what-is-installed"></a>Feststellen, was installiert ist

Ab .NET Core 2.1 verfügt die .NET-CLI über Optionen, mit denen Sie die auf Ihrem Computer installierten Versionen des SDK und der Runtime auflisten können.  Verwenden Sie [`dotnet --list-sdks`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten SDKs. Verwenden Sie [`dotnet --list-runtimes`](../tools/dotnet.md#options) zum Anzeigen der Liste der auf Ihrem Computer installierten Runtimes. Weitere Informationen finden Sie unter [Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md).

## <a name="uninstall-net-core"></a>Deinstallieren von .NET Core

::: zone pivot="os-windows"

.NET Core verwendet das Windows-Dialogfeld **Apps & Features**, um Versionen der .NET Core-Runtime und des .NET Core SDK zu entfernen. Auf der folgenden Abbildung sehen Sie das Dialogfeld **Apps & Features**. Sie können nach **Core SDK** filtern, um installierte Versionen von .NET Core zu suchen und anzuzeigen.

![Hinzufügen/Entfernen von Programmen zum Entfernen von .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Wählen Sie sämtliche Versionen aus, die Sie von Ihrem Computer entfernen möchten, und klicken Sie auf **Deinstallieren**.

::: zone-end

::: zone pivot="os-linux"

Für die Deinstallation von .NET Core (Runtime oder SDK) unter Linux gibt es weitere Optionen. Die beste Möglichkeit zur Deinstallation von .NET Core besteht in der Spiegelung der für die Installation von .NET Core verwendeten Aktion. Die Details hängen davon ab, welche Verteilung und Installationsmethode Sie auswählen.

> [!IMPORTANT]
> Informationen zur Installation und Deinstallation von .NET Core unter Red Hat finden Sie im [Leitfaden für erste Schritte von Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).

Ab .NET Core 2.1 muss das .NET Core SDK nicht mehr deinstalliert werden, wenn mithilfe eines Paket-Managers ein Upgrade durchgeführt wird. Mit dem Befehl `update` oder `refresh` des Paket-Managers werden die älteren Versionen nach erfolgreicher Installation einer neueren Version automatisch entfernt.

Wenn Sie .NET Core mithilfe eines Paket-Managers installiert haben, können Sie für die Deinstallation des .NET SDK oder der -Runtime denselben Paket-Manager verwenden. .NET Core-Installationen unterstützen die am häufigsten verwendeten Paket-Manager. In der Dokumentation zu dem Paket-Manager Ihrer Distribution finden Sie die genaue Syntax in Ihrer Umgebung:

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

Unter Linux müssen die SDKs und Runtimes separat entfernt werden, indem die Verzeichnisse mit Versionsangabe entfernt werden. Durch das Entfernen werden das SDK und die Runtime von der Festplatte gelöscht. Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.

::: zone-end

::: zone pivot="os-macos"

Auf einem Mac müssen die SDKs und Runtimes separat entfernt werden, indem die Verzeichnisse mit Versionsangabe entfernt werden. Durch das Entfernen werden das SDK und die Runtime von der Festplatte gelöscht. Zum Entfernen des SDK und der Runtime von Version 1.0.1 würden Sie beispielsweise die folgenden Bash-Befehle verwenden:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Die übergeordneten Verzeichnisse für das SDK und die Runtime werden in der Ausgabe des Befehls `dotnet --list-sdks` und `dotnet --list-runtimes` aufgeführt, wie in der obigen Tabelle dargestellt.

::: zone-end

## <a name="net-core-uninstall-tool"></a>.NET Core-Deinstallationstool

Mit dem [.NET Core-Deinstallationstool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und .NET Core-Runtimes aus einem System entfernen. Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, um anzugeben, welche Versionen deinstalliert werden sollen.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Visual Studio-Abhängigkeit von .NET Core SDK Versionen

Vor Visual Studio 2019 Version 16.3 haben Visual Studio-Installer den eigenständigen .NET Core SDK-Installer aufgerufen. Folglich werden die SDK-Versionen im Dialogfeld Windows-Dialogfeld **Apps & Features** angezeigt. Das Entfernen von .Core SDKs, die von Visual Studio mit dem eigenständigen Installer installiert wurden, kann dazu führen, dass Visual Studio nicht mehr funktioniert. Wenn in Visual Studio nach der Deinstallation von SDKs Probleme auftreten, führen Sie „Reparieren“ für diese bestimmte Version von Visual Studio aus. In der folgenden Tabelle werden einige der Visual Studio-Abhängigkeiten von .NET Core SDK-Versionen gezeigt:

| Visual Studio-Version           | .NET Core SDK-Version          |
|---------------------------------|--------------------------------|
| Visual Studio 2019 Version 16.2 | .NET Core SDK 2.2.4xx, 2.1.8xx |
| Visual Studio 2019 Version 16.1 | .NET Core SDK 2.2.3xx, 2.1.7xx |
| Visual Studio 2019, Version 16.0 | .NET Core SDK 2.2.2xx, 2.1.6xx |
| Visual Studio 2017 Version 15.9 | .NET Core SDK 2.2.1xx, 2.1.5xx |
| Visual Studio 2017 Version 15.8 | .NET Core SDK 2.1.4xx          |

Ab Visual Studio 2019, Version 16.3, verwaltet Visual Studio eine eigene Kopie des .NET Core SDK. Aus diesem Grund werden diese SDK-Versionen nicht mehr im Dialogfeld **Apps & Features** angezeigt.

## <a name="remove-the-nuget-fallback-folder"></a>Entfernen des NuGet-Fallbackordners

Vor dem .NET Core 3.0 SDK verwendeten die .NET Core SDK-Installer den Ordner *NuGetFallbackFolder*, um einen Cache mit NuGet-Paketen zu speichern. Dieser Cache wurde bei Vorgängen wie `dotnet restore` oder `dotnet build /t:Restore`verwendet. Der Ordner *NuGetFallbackFolder* befindet sich unter Windows unter *C:\Programme\dotnet\sdk* und unter macOS unter */usr/local/share/dotnet/sdk*.

Möglicherweise möchten Sie diesen Ordner entfernen, wenn Folgendes zutrifft:

- Sie entwickeln nur mit dem .NET Core 3.0 SDK oder höheren Versionen.
- Sie entwickeln mit .NET Core SDK-Versionen vor 3.0, können aber online arbeiten.

Wenn Sie den NuGet-Fallbackordner entfernen möchten, können Sie ihn löschen, aber hierfür benötigen Sie Administratorberechtigungen.

Es wird nicht empfohlen, den Ordner *dotnet* zu löschen. Dadurch würden Sie alle globalen Tools entfernen, die Sie zuvor installiert haben. Unter Windows gilt außerdem:

- Sie verlieren die Funktionalität von Visual Studio 2019 Version 16.3 und höheren Versionen. Zum Wiederherstellen können Sie **Reparieren** ausführen.
- Wenn .NET Core SDK-Einträge im Dialogfeld **Apps & Features** angezeigt werden, sind sie verwaist.
