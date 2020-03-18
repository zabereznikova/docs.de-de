---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503780"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
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
