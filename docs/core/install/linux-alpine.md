---
title: 'Installieren von .NET Core unter Alpine: .NET Core'
description: Hier werden verschiedene Möglichkeiten veranschaulicht, das.NET Core SDK und die NET Core-Runtime unter Alpine zu installieren.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: bbaf4ee9020dcd33c894b5376bf04ad65db8d378
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84771488"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a>Installieren des .NET Core SDK oder der .NET Core-Runtime unter Alpine

In diesem Artikel wird beschrieben, wie Sie .NET Core unter Alpine installieren. Wenn für eine Alpine-Version kein Support mehr geboten wird, wird .NET Core mit dieser Version nicht mehr unterstützt. Diese Anweisungen können Ihnen jedoch helfen, .NET Core in diesen Versionen auszuführen, auch wenn kein Support dafür geboten wird.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Es sind keine Installationsprogramme für Alpine vorhanden. Sie müssen entweder das [Installationsskript](#scripted-install) verwenden oder die Anweisungen zur [manuellen Installation](#manual-install) befolgen.

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle enthält die derzeit unterstützten .NET Core-Releases und die Alpine-Versionen, die diese unterstützen. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Alpine das Ende ihrer Lebensdauer erreicht](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- ✔️ gibt an, dass die Version von Alpine oder .NET Core weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Alpine oder .NET Core in diesem Alpine-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Alpine als auch eine Version von .NET Core mit ✔️ versehen sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Alpine                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview |
|--------------------------|---------------|---------------|----------------|
| ✔️ 3.12  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ✔️ 3.11  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ✔️ 3.10  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ✔️ 3.9   | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ❌ 3.8   | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 Preview |

Die folgenden Versionen von .NET Core werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Abhängigkeiten

.NET Core unter Alpine Linux erfordert die Installation der folgenden Abhängigkeiten:

- icu-libs
- krb5-libs
- libintl
- libssl1.1 (Alpine 3.9 oder höher)
- libssl1.0 (Alpine 3.8)
- libstdc++
- lttng-ust
- numactl (optional)
- zlib

## <a name="scripted-install"></a>Per Skript gesteuerte Installation

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Manuelle Installation

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
