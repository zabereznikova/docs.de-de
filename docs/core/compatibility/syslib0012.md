---
title: Warnung SYSLIB0012
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0012 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2ed93b6eefbaa861faca319f0cc9bf19ac741f3b
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333057"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="144e8-103">SYSLIB0012: Assembly.CodeBase und Assembly.EscapedCodeBase sind veraltet</span><span class="sxs-lookup"><span data-stu-id="144e8-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="144e8-104">Die folgenden APIs sind ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="144e8-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="144e8-105">Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0012` hervor.</span><span class="sxs-lookup"><span data-stu-id="144e8-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

<span data-ttu-id="144e8-106">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="144e8-106">Workaround</span></span>

<span data-ttu-id="144e8-107">Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="144e8-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>
