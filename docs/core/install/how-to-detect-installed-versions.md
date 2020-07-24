---
title: Überprüfen der Installation von .NET Core-Versionen unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie, wie Sie auflisten, welche .NET Core-Versionen auf Ihrem Computer installiert sind. Zu den Versionen zählen die .NET Core-Runtime und das .NET Core SDK.
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: b8825dee595c601e8adef0a52e651ac4a4f04831
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416038"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a>Überprüfen, ob .NET Core bereits installiert ist

In diesem Artikel erfahren Sie, wie Sie überprüfen, welche Versionen der .NET Core-Runtime und des .NET Core SDK auf Ihrem Computer installiert sind. .NET Core wurde möglicherweise bereits installiert, wenn Sie eine integrierte Entwicklungsumgebung wie z. B. Visual Studio oder Visual Studio für Mac besitzen.

Durch das Installieren eines SDK wird die entsprechende Runtime installiert.

Falls ein beliebiger Befehl in diesem Artikel fehlschlägt, haben Sie die Runtime oder den SDK nicht installiert. Weitere Informationen finden Sie in den Installationsartikeln für [Windows](windows.md), [macOS](macos.md) und [Linux](linux.md).

## <a name="check-sdk-versions"></a>Überprüfen der SDK-Versionen

Sie können sehen, welche Versionen des .NET Core SDK aktuell mit einem Terminal installiert sind. Öffnen Sie ein Terminal, und führen Sie den folgenden Befehl aus.

```dotnetcli
dotnet --list-sdks
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
2.2.101 [C:\program files\dotnet\sdk]
3.0.100 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
2.2.101 [/home/user/dotnet/sdk]
3.0.100 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
2.2.101 [/usr/local/share/dotnet/sdk]
3.0.100 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a>Überprüfen der Runtime-Versionen

Mit dem folgenden Befehl können Sie feststellen, welche Versionen der .NET Core-Runtime derzeit installiert sind.

```dotnetcli
dotnet --list-runtimes
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a>Überprüfen auf Installationsordner

Es ist möglich, dass .NET Core installiert ist, für Ihr Betriebssystem oder Benutzerprofil jedoch nicht zur `PATH`-Variable hinzugefügt wurde. Das Ausführen der Befehle aus den vorherigen Abschnitten funktioniert möglicherweise nicht. Alternativ können Sie überprüfen, ob die .NET Core-Installationsordner vorhanden sind.

Wenn Sie .NET Core über einen Installer oder ein Skript installieren, wird es in einem Standardordner installiert. Meistens bietet der Installer oder das Skript, den oder das Sie für die Installation von .NET Core verwenden, die Möglichkeit, in einen anderen Ordner zu installieren. Wenn Sie in einen anderen Ordner installieren möchten, passen Sie den Anfang des Ordnerpfads an.

::: zone pivot="os-windows"

- **Ausführbare dotnet-Datei**\
_C:\\Programme\\dotnet\\dotnet.exe_

- **.NET SDK**\
_C:\\Programme\\dotnet\\sdk\\{Version}\\_

- **.NET-Laufzeit**\
_C:\\Programme\\dotnet\\shared\\{Laufzeittyp}\\{Version}\\_

::: zone-end

::: zone pivot="os-linux"

- **Ausführbare dotnet-Datei**\
_/home/user/share/dotnet/dotnet_

- **.NET SDK**\
_/home/user/share/dotnet/sdk/{Version}/_

- **.NET-Laufzeit**\
_/home/user/share/dotnet/shared/{Laufzeittyp}/{Version}/_

::: zone-end

::: zone pivot="os-macos"

- **Ausführbare dotnet-Datei**\
_/usr/local/share/dotnet/dotnet_

- **.NET SDK**\
_/usr/local/share/dotnet/sdk/{Version}/_

- **.NET-Laufzeit**\
_/usr/local/share/dotnet/shared/{Laufzeittyp}/{Version}/_

::: zone-end

## <a name="more-information"></a>Weitere Informationen

Sie können sowohl die SDK-Versionen als auch die Runtime-Versionen mit dem `dotnet --info`-Befehl sehen. Sie erhalten auch umgebungsbezogene Informationen, wie z. B. die Betriebssystemversion und den Laufzeitbezeichner (Runtime Identifier, RID).

## <a name="next-steps"></a>Nächste Schritte

- [Installieren Sie die .NET Core-Runtime und das .NET Core SDK.](windows.md)
