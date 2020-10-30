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
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a>SYSLIB0004: Das Feature „Eingeschränkte Ausführungsregion“ (Constrained Execution Region, CER) wird nicht unterstützt.

Das Feature [Eingeschränkte Ausführungsregion (Constrained Execution Region, CER)](../../framework/performance/constrained-execution-regions.md) wird nur in .NET Framework unterstützt. Daher sind verschiedene CER-bezogene APIs ab .NET 5.0 als veraltet markiert. Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0004` hervor.

Die folgenden CER-bezogenen APIs sind veraltet:

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="see-also"></a>Siehe auch

- [Eingeschränkte Ausführungsbereiche](../../framework/performance/constrained-execution-regions.md)
