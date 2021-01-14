---
title: 'Manuelles Installieren von .NET unter Linux: .NET'
description: In diesem Artikel wird veranschaulicht, wie Sie das .NET SDK und die .NET-Runtime ohne Paket-Manager unter Linux installieren. Verwenden Sie das Installationsskript, oder extrahieren Sie die Binärdateien manuell.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 5879d4d66aba8bfa00caadbe3c33d6df0d7da59a
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970925"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a>Manuelles Installieren des .NET SDK oder der .NET-Runtime

.NET wird unter Linux unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET mithilfe des Installationsskripts oder durch Extrahieren der Binärdateien unter Linux installieren. Eine Liste der Distributionen, die den integrierten Paket-Manager unterstützen, finden Sie unter [Installieren von .NET unter Linux](linux.md).

Sie können .NET auch mithilfe von Snap installieren. Weitere Informationen finden Sie unter [Installieren des .NET SDK oder der .NET-Runtime mithilfe von Snap](linux-snap.md).

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a>.NET-Releases

In der folgenden Tabelle sind die Versionen von .NET (und .NET Core) aufgelistet:

| ✔️ Unterstützt | ❌ Nicht unterstützt |
|-------------|---------------|
| 5.0         | 3.0           |
| 3.1 (LTS)   | 2.2           |
| 2.1 (LTS)   | 2.0           |
|             | 1.1           |
|             | 1.0           |

Weitere Informationen zum Lebenszyklus von .NET-Versionen finden Sie in der [Richtlinie zur Unterstützung von .NET Core und .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="dependencies"></a>Abhängigkeiten

Es ist möglich, dass bei der Installation von .NET bestimmte Abhängigkeiten möglicherweise nicht installiert werden, z. B. wenn Sie [manuell installieren](#manual-install). In der folgenden Liste werden die von Microsoft unterstützten Linux-Distributionen mit Abhängigkeiten erläutert, die Sie möglicherweise installieren müssen. Weitere Informationen finden Sie auf der Seite zur Distribution:

- [Alpine](linux-alpine.md#dependencies)
- [Debian](linux-debian.md#dependencies)
- [CentOS](linux-centos.md#dependencies)
- [Fedora](linux-fedora.md#dependencies)
- [RHEL](linux-rhel.md#dependencies)
- [SLES](linux-sles.md#dependencies)
- [Ubuntu](linux-ubuntu.md#dependencies)

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self-contained Linux apps (Eigenständige Linux-Apps)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

### <a name="rpm-dependencies"></a>RPM-Abhängigkeiten

Wenn Ihre Distribution zuvor nicht aufgelistet wurde und auf RPM basiert, benötigen Sie möglicherweise die folgenden Abhängigkeiten:

- krb5-libs
- libicu
- openssl-libs

Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.

### <a name="deb-dependencies"></a>DEB-Abhängigkeiten

Wenn Ihre Distribution zuvor nicht aufgelistet wurde und auf Debian basiert, benötigen Sie möglicherweise die folgenden Abhängigkeiten:

- libc6
- libgcc1
- libgssapi-krb5-2
- libicu67
- libssl1.1
- libstdc++6
- zlib1g

### <a name="common-dependencies"></a>Allgemeine Abhängigkeiten

Für .NET-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:

- [libgdiplus (Version 6.0.1 oder höher)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen. Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Per Skript gesteuerte Installation

Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung sowie für Installationen von **SDK** und **Runtime** durch Benutzer ohne Administratorrechte verwendet. Sie können das Skript unter <https://dot.net/v1/dotnet-install.sh> herunterladen.

Das Skript installiert standardmäßig die neueste [LTS](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)-SDK-Version (Long-Term Support), die derzeit .NET Core 3.1 entspricht. Um die aktuelle Version zu installieren, bei der es sich möglicherweise nicht um eine LTS-Version handelt, nutzen Sie den Parameter `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Geben Sie den Parameter `--runtime` an, um die .NET-Runtime anstelle des SDK zu installieren.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Sie können eine bestimmte Version installieren, indem Sie mit dem Parameter `-c` die gewünschte Version angeben. Mit dem folgenden Befehl wird .NET SDK 5.0 installiert.

```bash
./dotnet-install.sh -c 5.0
```

Weitere Informationen finden Sie in der [ Referenz zu dotnet-install-Skripts](../tools/dotnet-install-script.md).

## <a name="manual-install"></a>Manuelle Installation

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

Als Alternative zu den Paket-Managern können Sie das SDK und die Runtime herunterladen und manuell installieren. Die manuelle Installation wird in der Regel im Rahmen von Continuous Integration-Tests oder unter nicht unterstützten Linux-Distributionen durchgeführt. Für Entwickler oder Benutzer ist die Verwendung eines Paket-Managers besser geeignet.

Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Laden Sie zunächst entweder für das SDK oder die Runtime eine **binäre** Version auf einer der folgenden Websites herunter:

- ✔️ [.NET 5.0-Downloads](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Alle .NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core)

Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von .NET verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET in PATH befindet.

Laden Sie zunächst ein binäres .NET-Release herunter, um die Runtime zu extrahieren und die .NET-CLI-Befehle im Terminal bereitzustellen. Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde. Je nachdem, was Sie heruntergeladen haben, kann der Name der Archivdatei abweichen.

**Verwenden Sie den folgenden Befehl, um die Runtime zu extrahieren:**

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Verwenden Sie den folgenden Befehl, um das SDK zu extrahieren:**

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Mit den oben aufgeführten `export`-Befehlen werden nur die .NET-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.
>
> Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen. Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen. Zum Beispiel:
>
> - **Bash-Shell**: *~/.bash_profile*, *~/.bashrc*
> - **Korn-Shell**: *~/.kshrc* oder *.profile*
> - **Z-Shell**: *~/.kshrc* oder *.profile*
>
> Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu. Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.
>
> Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.

Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI](../tools/enable-tab-autocomplete.md)
- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
