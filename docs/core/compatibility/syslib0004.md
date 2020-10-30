---
title: Warnung „SYSLIB0004“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0004“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: ba7cd8a890a89000b241d286c9d8069ba1398849
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333090"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="e2b92-103">SYSLIB0004: Das Feature „Eingeschränkte Ausführungsregion“ (Constrained Execution Region, CER) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2b92-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="e2b92-104">Das Feature [Eingeschränkte Ausführungsregion (Constrained Execution Region, CER)](../../framework/performance/constrained-execution-regions.md) wird nur in .NET Framework unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2b92-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="e2b92-105">Daher sind verschiedene CER-bezogene APIs ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e2b92-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="e2b92-106">Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0004` hervor.</span><span class="sxs-lookup"><span data-stu-id="e2b92-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="e2b92-107">Die folgenden CER-bezogenen APIs sind veraltet:</span><span class="sxs-lookup"><span data-stu-id="e2b92-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="e2b92-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2b92-108">See also</span></span>

- [<span data-ttu-id="e2b92-109">Eingeschränkte Ausführungsbereiche</span><span class="sxs-lookup"><span data-stu-id="e2b92-109">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
