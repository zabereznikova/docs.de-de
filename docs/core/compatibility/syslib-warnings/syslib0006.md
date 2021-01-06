---
title: Warnung SYSLIB0006
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0006 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: c1eecade9280ac37917bc24aa2973756c7f08d87
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596287"
---
# <a name="syslib0006-threadabort-is-not-supported"></a><span data-ttu-id="1ad5e-103">SYSLIB0006: Thread.Abort wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="1ad5e-103">SYSLIB0006: Thread.Abort is not supported</span></span>

<span data-ttu-id="1ad5e-104">Die folgenden APIs sind ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="1ad5e-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="1ad5e-105">Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0006` hervor.</span><span class="sxs-lookup"><span data-stu-id="1ad5e-105">Use of these APIs generates warning `SYSLIB0006` at compile time.</span></span>

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="1ad5e-106">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="1ad5e-106">Workarounds</span></span>

<span data-ttu-id="1ad5e-107">Verwenden Sie <xref:System.Threading.CancellationToken>, um die Verarbeitung einer Arbeitseinheit abzubrechen, statt <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ad5e-107">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1ad5e-108">Im folgenden Beispiel wird die Verwendung von <xref:System.Threading.CancellationToken> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1ad5e-108">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="1ad5e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ad5e-109">See also</span></span>

- [<span data-ttu-id="1ad5e-110">Thread.Abort ist veraltet</span><span class="sxs-lookup"><span data-stu-id="1ad5e-110">Thread.Abort is obsolete</span></span>](../core-libraries/5.0/thread-abort-obsolete.md)
- [<span data-ttu-id="1ad5e-111">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="1ad5e-111">Cancellation in managed threads</span></span>](../../../standard/threading/cancellation-in-managed-threads.md)
