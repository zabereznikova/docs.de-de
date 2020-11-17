---
title: Warnung SYSLIB0012
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0012 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dc139d5c5cb6d6a34d161147b350b3324d15117e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440581"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="16954-103">SYSLIB0012: Assembly.CodeBase und Assembly.EscapedCodeBase sind veraltet</span><span class="sxs-lookup"><span data-stu-id="16954-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="16954-104">Die folgenden APIs sind ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="16954-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="16954-105">Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0012` hervor.</span><span class="sxs-lookup"><span data-stu-id="16954-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="16954-106">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="16954-106">Workarounds</span></span>

<span data-ttu-id="16954-107">Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16954-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]
