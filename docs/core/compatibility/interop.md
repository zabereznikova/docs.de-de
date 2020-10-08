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
# <a name="interop-breaking-changes"></a><span data-ttu-id="3328b-103">Breaking Changes bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="3328b-103">Interop breaking changes</span></span>

<span data-ttu-id="3328b-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="3328b-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="3328b-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="3328b-105">Breaking change</span></span> | <span data-ttu-id="3328b-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3328b-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="3328b-107">Die Umwandlung des RCW in eine `InterfaceIsIInspectable`-Schnittstelle löst die PlatformNotSupportedException aus.</span><span class="sxs-lookup"><span data-stu-id="3328b-107">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | <span data-ttu-id="3328b-108">5.0</span><span class="sxs-lookup"><span data-stu-id="3328b-108">5.0</span></span> |
| [<span data-ttu-id="3328b-109">Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows</span><span class="sxs-lookup"><span data-stu-id="3328b-109">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="3328b-110">5.0</span><span class="sxs-lookup"><span data-stu-id="3328b-110">5.0</span></span> |
| [<span data-ttu-id="3328b-111">Integrierte Unterstützung für WinRT wird aus .NET entfernt</span><span class="sxs-lookup"><span data-stu-id="3328b-111">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="3328b-112">5.0</span><span class="sxs-lookup"><span data-stu-id="3328b-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="3328b-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3328b-113">.NET 5.0</span></span>

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
