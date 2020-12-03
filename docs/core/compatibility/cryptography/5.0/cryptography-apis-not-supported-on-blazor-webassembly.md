---
title: 'Breaking Change: System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Kryptografie-APIs eine Ausnahme auslösen, wenn sie in einem Browser ausgeführt werden.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759227"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a>System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt

<xref:System.Security.Cryptography>-APIs lösen zur Laufzeit eine <xref:System.PlatformNotSupportedException> aus, wenn sie in einem Browser ausgeführt werden.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET waren die meisten <xref:System.Security.Cryptography>-APIs für Blazor WebAssembly-Apps nicht verfügbar. Ab .NET 5.0 sind Blazor WebAssembly-Apps zwar auf die gesamte API-Oberfläche für .NET 5 ausgerichtet, aber aufgrund von Browsereinschränkungen der Sandbox werden nicht alle .NET 5-APIs unterstützt. In .NET 5.0 und höheren Versionen lösen die nicht unterstützten <xref:System.Security.Cryptography>-APIs eine <xref:System.PlatformNotSupportedException> aus, wenn sie in WebAssembly ausgeführt werden.

> [!TIP]
> Wenn Sie ein Projekt erstellen, das die Browserplattform unterstützt, kennzeichnet das [Analysetool für die Plattformkompatibilität](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) sämtliche Aufrufe der betroffenen APIs. Dieses Analysetool wird standardmäßig in Apps für .NET 5.0 und höher ausgeführt.

## <a name="reason-for-change"></a>Grund für die Änderung

Microsoft kann OpenSSL nicht als Abhängigkeit mit der Blazor WebAssembly-Konfiguration integrieren. Wir haben versucht, dieses Problem zu umgehen, indem wir eine Integration in die API `SubtleCrypto` des Browsers vorgenommen haben. Leider waren dafür aber einschlägige API-Änderungen erforderlich, die die Integration zu kompliziert machten.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Zurzeit gibt es keine gute Möglichkeit, dieses Problem zu umgehen.

## <a name="affected-apis"></a>Betroffene APIs

Alle <xref:System.Security.Cryptography?displayProperty=fullName>-APIs außer:

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->
