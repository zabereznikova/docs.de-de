---
title: '.NET Core SDK und Runtimeabhängigkeiten: .NET Core'
description: In diesem Artikel werden die Voraussetzungen für das Betriebssystem und die CPU-Architektur zum Installieren des .NET Core SDK und der Runtime unter Windows, Linux und macOS erläutert.
author: leecow
ms.author: leecow
ms.date: 04/30/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 280aa1431686ff99257580bb024a84b1e57f85c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895487"
---
# <a name="net-core-dependencies-and-requirements"></a>.NET Core-Abhängigkeiten und -Anforderungen

In diesem Artikel wird erläutert, welche Betriebssysteme und CPU-Architektur von .NET Core unterstützt werden.

## <a name="supported-operating-systems"></a>Unterstützte Betriebssysteme

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2012 R2 oder höher                       | x64, x86        |
| Nano Server                   | Version 1803 oder höher                  | x64, ARM32      |

Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2012 R2 oder höher                       | x64, x86        |
| Nano Server                   | Version 1803 oder höher                  | x64, ARM32      |

Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 oder höher                   | x64, x86        |
| Nano Server                   | Version 1803 oder höher                   | x64, ARM32      |

Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 oder höher                   | x64, x86        |
| Nano Server                   | Version 1803 oder höher                  | x64,            |

Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> Windows 7/Vista/8.1/Server 2008 R2/Server 2012 R2

Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:

- Windows 7 SP1
- Windows Vista SP 2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

Installieren Sie Folgendes:

- [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:

> Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt. Installieren Sie das Programm erneut, um das Problem zu beheben.
>
> \- oder -
>
> Das Programm kann nicht gestartet werden, da *api-ms-win-cor-timezone-l1-1-0.dll* auf dem Computer fehlt. Installieren Sie das Programm erneut, um das Problem zu beheben.
>
> \- oder -
>
> The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 behandelt Linux als ein einziges Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.

.NET Core 3.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                             | Version               | Architekturen    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | x64 |
| CentOS                         | 7 und höher                    | x64 |
| Oracle Linux                   | 7 und höher                    | x64 |
| Fedora                         | 30 und höher                   | x64 |
| Debian                         | 9 und höher                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04 und höher                | x64, ARM32, ARM64 |
| Linux Mint                     | 18 und höher                   | x64 |
| openSUSE                       | 15 und höher                   | x64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | x64 |
| Alpine Linux                   | 3.10 oder höher                 | x64, ARM64 |

Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

Weitere Informationen zum Installieren von .NET Core 3.1 unter ARM64 (Kernel 4.14 oder höher) finden Sie unter [Installieren von .NET Core 3.0 unter Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

> [!IMPORTANT]
> Für die Unterstützung von ARM64 ist Linux-Kernel 4.14 oder höher erforderlich. Einige Linux-Verteilungen erfüllen diese Anforderung, andere hingegen nicht. So wird Ubuntu 18.04 im Gegensatz zu Ubuntu 16.04 unterstützt.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 3.0 behandelt Linux als ein einziges Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.

.NET Core 3.0 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                             | Version               | Architekturen    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | x64 |
| CentOS                         | 7 und höher                    | x64 |
| Oracle Linux                   | 7 und höher                    | x64 |
| Fedora                         | 29 und höher                   | x64 |
| Debian                         | 9 und höher                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04 und höher                | x64, ARM32, ARM64 |
| Linux Mint                     | 18 und höher                   | x64 |
| openSUSE                       | 15 und höher                   | x64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | x64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 2.2 behandelt Linux als ein einziges Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.

.NET Core 2.2 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                             |  Version                |  Architekturen   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | x64 |
| CentOS                         |  7                      | x64 |
| Oracle Linux                   |  7                      | x64 |
| Fedora                         |  29, 30                 | x64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 18.10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | x64 |
| openSUSE                       |  15 und höher                    | x64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | x64 |
| Alpine Linux                   |  3.8+                   | x64 |

Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 behandelt Linux als ein einziges Betriebssystem. Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.

.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                             |  Version                |  Architekturen   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | x64 |
| CentOS                         |  7 und höher                     | x64 |
| Oracle Linux                   |  7 und höher                     | x64 |
| Fedora                         |  30 und höher                    | x64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 19.04, 19.10    | x64, ARM32 |
| Linux Mint                     |  17 oder höher                    | x64 |
| openSUSE                       |  15 und höher                    | x64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | x64 |
| Alpine Linux                   |  3.8+                   | x64 |

Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

## <a name="linux-distribution-dependencies"></a>Abhängigkeiten der Linux-Distributionen

Basierend auf den Linux-Verteilungen müssen Sie möglicherweise zusätzliche Abhängigkeiten installieren.

> [!IMPORTANT]
> Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.

### <a name="ubuntu"></a>Ubuntu

Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

- liblttng-ust0
- libcurl3 (für 14.x und 16.x)
- libcurl4 (für 18.x)
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52 (für 14.X)
- libicu55 (für 16.X)
- libicu57 (für 17.X)
- libicu60 (für 18.X)

Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:

- libgdiplus (Version 6.0.1 oder höher)

> [!WARNING]
> Die meisten Versionen von Ubuntu enthalten eine frühere Version von libgdiplus. Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen. Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.

### <a name="centos-and-fedora"></a>CentOS und Fedora

Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL Version 1.1 oder höher entspricht, müssen Sie **compat-openssl10** installieren.

Für .NET Core 2.0 sind außerdem die folgenden Abhängigkeiten erforderlich:

- libunwind
- libuuid

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:

- libgdiplus (Version 6.0.1 oder höher)

> [!WARNING]
> Die meisten Versionen von CentOS und Fedora enthalten eine frühere Version von libgdiplus. Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen. Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.

### <a name="alpine"></a>Alpine

Für Alpine-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:

- icu-lisb (nicht erforderlich bei deaktivierter Globalisierung)
- krb5-libs
- libcurl
- libintl
- libssl1.1 (für Alpine 3.9 oder höher) oder libssl1.0 (für ältere Versionen)
- libstdc++
- lttng-ust
- numactl (optional, nur für Geräte mit aktiviertem NUMA nützlich)
- zlib

Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:

- libgdiplus (nur im Edge/Testing-Repository verfügbar)

::: zone-end

::: zone pivot="os-macos"

.NET Core wird von den folgenden macOS-Versionen unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| .NET Core-Version | macOS                 | Architekturen |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13 oder höher)  | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13 oder höher)  | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12 oder höher)       | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12 oder höher)       | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird. Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird.

Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert. Vorherige Versionen wurden nicht notarisiert. Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET Core (und Ihre .NET Core-Apps) auswirkt, finden Sie unter [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.

Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS. Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>Nächste Schritte

- Installieren Sie das [.NET Core SDK](sdk.md) (einschließlich der Runtime), um Apps zu entwickeln und auszuführen.
- Installieren Sie die [.NET Core-Runtime](runtime.md), um von anderen erstellte Apps auszuführen.
