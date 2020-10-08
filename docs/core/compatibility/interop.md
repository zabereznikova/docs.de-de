---
title: Breaking Changes bei der Interoperabilität
description: Hier werden Breaking Changes für die Interoperabilität zwischen .NET Core und .NET 5.0 und höheren Versionen aufgeführt.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438046"
---
# <a name="interop-breaking-changes"></a>Breaking Changes bei der Interoperabilität

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [Die Umwandlung des RCW in eine `InterfaceIsIInspectable`-Schnittstelle löst die PlatformNotSupportedException aus.](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | 5.0 |
| [Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows](#no-aw-suffix-probing-on-non-windows-platforms) | 5.0 |
| [Integrierte Unterstützung für WinRT wird aus .NET entfernt](#built-in-support-for-winrt-is-removed-from-net) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
