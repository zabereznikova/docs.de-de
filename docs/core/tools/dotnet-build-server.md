---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 02/14/2020
ms.openlocfilehash: 882b697c07aac0e20266f3ad4e6c11888a0b7acc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463725"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]

dotnet build-server shutdown -h|--help

dotnet build-server -h|--help
```

## <a name="commands"></a>Befehle

- **`shutdown`**

  Fährt Buildserver herunter, die über dotnet gestartet wurden. Standardmäßig werden alle Server heruntergefahren.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--msbuild`**

  Fährt den MSBuild-Buildserver herunter.

- **`--razor`**

  Fährt den Razor-Buildserver herunter.

- **`--vbcscompiler`**

  Fährt den VB/C#-Compiler-Buildserver herunter.
