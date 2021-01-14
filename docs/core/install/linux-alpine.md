---
title: 'Installieren von .NET unter Alpine: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter Alpine zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6adaa905c400b45526ebbc3d8e2606522863eec3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970849"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Installieren des .NET SDK oder der .NET-Runtime unter Alpine

In diesem Artikel wird beschrieben, wie Sie .NET unter Alpine installieren. Wenn für eine Alpine-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt. Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn sie nicht unterstützt werden.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a>Installieren

Installationsprogramme sind für Alpine Linux nicht verfügbar. .NET muss auf eine der folgenden Arten installiert werden:

- [Snap-Paket](linux-snap.md)
- [Skriptgesteuerte Installation mit _install-dotnet.sh_](linux-scripted-manual.md#scripted-install)
- [Manuelle binäre Extraktion](linux-scripted-manual.md#manual-install)

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

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI](../tools/enable-tab-autocomplete.md)
- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
