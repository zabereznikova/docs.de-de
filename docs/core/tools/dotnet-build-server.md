---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: fa663bc045e8abfc3375a0226be7d16331b49740
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632099"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Dieser Artikel gilt für: ✓**.NET Core 2.1 SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>name

`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.

## <a name="synopsis"></a>Übersicht

```
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
