---
title: Warnung „SYSLIB0008“
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit die Warnung „SYSLIB0008“ generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440594"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a><span data-ttu-id="0834e-103">SYSLIB0008: „CreatePdbGenerator“ wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0834e-103">SYSLIB0008: CreatePdbGenerator is not supported</span></span>

<span data-ttu-id="0834e-104">Die API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> ist ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="0834e-104">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API is marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="0834e-105">Die Verwendung dieser API ruft zur Kompilierzeit die Warnung `SYSLIB0008` hervor.</span><span class="sxs-lookup"><span data-stu-id="0834e-105">Using this API generates warning `SYSLIB0008` at compile time.</span></span>

## <a name="suppress-the-warning"></a><span data-ttu-id="0834e-106">Unterdrücken der Warnung</span><span class="sxs-lookup"><span data-stu-id="0834e-106">Suppress the warning</span></span>

<span data-ttu-id="0834e-107">Wenn Sie den Code nicht ändern können, können Sie die Warnung über eine `#pragma`-Anweisung oder eine `<NoWarn>`-Projekteinstellung unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="0834e-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="0834e-108">Beispiele finden Sie unter [Unterdrücken von Warnungen](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="0834e-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
