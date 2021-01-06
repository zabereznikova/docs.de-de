---
title: Warnung SYSLIB0012
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0012 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 9b3fa94029efb2343e6dbbeb3ae36195f0956523
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596284"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="d4b40-103">SYSLIB0012: Assembly.CodeBase und Assembly.EscapedCodeBase sind veraltet</span><span class="sxs-lookup"><span data-stu-id="d4b40-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="d4b40-104">Die folgenden APIs sind ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d4b40-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="d4b40-105">Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0012` hervor.</span><span class="sxs-lookup"><span data-stu-id="d4b40-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="d4b40-106">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="d4b40-106">Workarounds</span></span>

<span data-ttu-id="d4b40-107">Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4b40-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]
