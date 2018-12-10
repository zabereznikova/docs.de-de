---
title: '.NET Core-CLI-Befehl: dotnet build-server'
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 12/04/2018
ms.openlocfilehash: 2746ade12cc819089258483e84a8c0f02a64c755
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125677"
---
# <a name="dotnet-build-server"></a>dotnet build-server

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

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