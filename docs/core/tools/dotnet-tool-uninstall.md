---
title: '.NET Core-CLI-Befehl: dotnet tool uninstall'
description: Der Befehl „dotnet tool uninstall“ deinstalliert das angegebene globale .NET Core-Tool auf Ihrem Computer.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 93a43e19df4c7f220ac1e2d2db397cba4d791e83
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389837"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet tool uninstall`: Deinstalliert das angegebene [globale .NET Core-Tool](global-tools.md) auf Ihrem Computer.

## <a name="synopsis"></a>Übersicht

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a>Beschreibung 

Der `dotnet tool uninstall`-Befehl ermöglicht Ihnen das Deinstallieren von globalen .NET Core-Tools auf Ihrem Computer. Um diesen Befehl verwenden zu können, müssen Sie entweder angeben, dass Sie ein benutzerweites Tool über die `--global`-Option entfernen möchten, oder Sie müssen mit der Option `--tool-path` einen Pfad zu dem Speicherort angeben, an dem das Tool installiert wird.

## <a name="arguments"></a>Argumente

`PACKAGE_NAME`

Name oder ID des NuGet-Pakets, das das zu deinstallierende globale .NET Core-Tool enthält. Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.

## <a name="options"></a>Optionen

`-g|--global`

Gibt an, dass das zu entfernende Tool von einer benutzerweiten Installation stammt. Kann nicht mit der Option `--tool-path` kombiniert werden. Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--tool-path <PATH>`

Gibt den Speicherort des globalen Tools an, das deinstalliert wird. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.

## <a name="examples"></a>Beispiele

Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool uninstall -g dotnetsay`

Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Windows-Ordner:

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Linux-/macOS-Ordner:

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>Siehe auch

* [.NET Core Global Tools (Globale .NET Core-Tools)](global-tools.md)