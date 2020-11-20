---
title: Warnung SYSLIB0009
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0009 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 47b4f595a54800370da90f61d838c665df8b6091
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439975"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a><span data-ttu-id="29028-103">SYSLIB0009: Die AuthenticationManager-Methoden „Authenticate“ und „PreAuthenticate“ werden nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="29028-103">SYSLIB0009: The AuthenticationManager Authenticate and PreAuthenticate methods are not supported</span></span>

<span data-ttu-id="29028-104">Die folgenden APIs sind ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="29028-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="29028-105">Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0009` hervor.</span><span class="sxs-lookup"><span data-stu-id="29028-105">Use of these APIs generates warning `SYSLIB0009` at compile time.</span></span>

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a><span data-ttu-id="29028-106">Unterdrücken der Warnung</span><span class="sxs-lookup"><span data-stu-id="29028-106">Suppress the warning</span></span>

<span data-ttu-id="29028-107">Wenn Sie den Code nicht ändern können, können Sie die Warnung über eine `#pragma`-Anweisung oder eine `<NoWarn>`-Projekteinstellung unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="29028-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="29028-108">Beispiele finden Sie unter [Unterdrücken von Warnungen](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="29028-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
