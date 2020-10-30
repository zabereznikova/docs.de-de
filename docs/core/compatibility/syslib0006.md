---
title: Warnung SYSLIB0006
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0006 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 45d2d8ec6ad99996f8b8f46d0c2e0ac2e02cf450
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333095"
---
# <a name="syslib0006-threadabort-is-not-supported"></a>SYSLIB0006: Thread.Abort wird nicht unterstützt

Die folgenden APIs sind ab .NET 5.0 als veraltet markiert. Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0006` hervor.

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workaround"></a>Problemumgehung

Verwenden Sie <xref:System.Threading.CancellationToken>, um die Verarbeitung einer Arbeitseinheit abzubrechen, statt <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aufzurufen. Im folgenden Beispiel wird die Verwendung von <xref:System.Threading.CancellationToken> veranschaulicht.

```csharp
void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
{
    if (QueryIsMoreWorkPending())
    {
        // If the CancellationToken is marked as "needs to cancel",
        // this will throw the appropriate exception.
        cancellationToken.ThrowIfCancellationRequested();

        WorkItem work = DequeueWorkItem();
        ProcessWorkItem(work);
    }
}
```

## <a name="see-also"></a>Siehe auch

- [Thread.Abort ist veraltet – Breaking Change](3.1-5.0.md#threadabort-is-obsolete)
- [Abbruch in verwalteten Threads](../../standard/threading/cancellation-in-managed-threads.md)
