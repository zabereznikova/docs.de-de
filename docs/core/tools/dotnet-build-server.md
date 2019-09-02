---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: b2dfd5f317466f18d9246bd1fb281a92c42f6d9d
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168108"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Dieser Artikel gilt für: ✓**.NET Core 2.1 SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>name

`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.

## <a name="synopsis"></a>Übersicht

```console
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Befehle

* **`shutdown`**

  Fährt Buildserver herunter, die über dotnet gestartet wurden. Standardmäßig werden alle Server heruntergefahren.

## <a name="options"></a>Optionen

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--msbuild`**

  Fährt den MSBuild-Buildserver herunter.

* **`--razor`**

  Fährt den Razor-Buildserver herunter.

* **`--vbcscompiler`**

  Fährt den VB/C#-Compiler-Buildserver herunter.
