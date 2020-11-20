---
title: 'Installieren von .NET unter Alpine: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter Alpine zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506816"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Installieren des .NET SDK oder der .NET-Runtime unter Alpine

In diesem Artikel wird beschrieben, wie Sie .NET unter Alpine installieren. Wenn für eine Alpine-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt. Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn sie nicht unterstützt werden.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Es sind keine Installationsprogramme für Alpine vorhanden. Sie müssen entweder das [Installationsskript](#scripted-install) verwenden oder die Anweisungen zur [manuellen Installation](#manual-install) befolgen.

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Alpine-Versionen, die diese unterstützen. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Alpine das Ende ihrer Lebensdauer](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases) erreicht.

- ✔️ gibt an, dass die Version von Alpine oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Alpine oder .NET in diesem Alpine-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Alpine als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Alpine  | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|-------- |---------------|---------------|----------------|
| ✔️ 3.12 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.11 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.10 | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.9  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.8  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |

Die folgenden Versionen von .NET werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Abhängigkeiten

.NET unter Alpine Linux erfordert die Installation der folgenden Abhängigkeiten:

- icu-libs
- krb5-libs
- libgcc
- libintl
- libssl1.1 (Alpine 3.9 oder höher)
- libssl1.0 (Alpine 3.8 oder weniger)
- libstdc++
- zlib

## <a name="scripted-install"></a>Per Skript gesteuerte Installation

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Manuelle Installation

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
