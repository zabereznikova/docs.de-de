---
title: Warnung „SYSLIB0004“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0004“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: f48fd8915a13f9f99b091eca895dcd74a8f18907
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440719"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="35671-103">SYSLIB0004: Das Feature „Eingeschränkte Ausführungsregion“ (Constrained Execution Region, CER) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35671-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="35671-104">Das Feature [Eingeschränkte Ausführungsregion (Constrained Execution Region, CER)](../../framework/performance/constrained-execution-regions.md) wird nur in .NET Framework unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35671-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="35671-105">Daher sind verschiedene CER-bezogene APIs ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="35671-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="35671-106">Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0004` hervor.</span><span class="sxs-lookup"><span data-stu-id="35671-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="35671-107">Die folgenden CER-bezogenen APIs sind veraltet:</span><span class="sxs-lookup"><span data-stu-id="35671-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="35671-108">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="35671-108">Workarounds</span></span>

- <span data-ttu-id="35671-109">Wenn Sie ein CER-Attribut auf eine Methode angewendet haben, entfernen Sie das Attribut.</span><span class="sxs-lookup"><span data-stu-id="35671-109">If you have applied a CER attribute to a method, remove the attribute.</span></span> <span data-ttu-id="35671-110">Diese Attribute haben keine Auswirkung auf .NET 5.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="35671-110">These attributes have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  // REMOVE the attribute below.
  [ReliabilityContract(Consistency.WillNotCorruptState, Cer.Success)]
  public void DoSomething()
  {
  }

  // REMOVE the attribute below.
  [PrePrepareMethod]
  public void DoSomething()
  {
  }
  ```

- <span data-ttu-id="35671-111">Wenn Sie `RuntimeHelpers.ProbeForSufficientStack` oder `RuntimeHelpers.PrepareContractedDelegate` aufrufen, entfernen Sie den Aufruf.</span><span class="sxs-lookup"><span data-stu-id="35671-111">If you are calling `RuntimeHelpers.ProbeForSufficientStack` or `RuntimeHelpers.PrepareContractedDelegate`, remove the call.</span></span> <span data-ttu-id="35671-112">Diese Aufrufe haben keine Auswirkung auf .NET 5.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="35671-112">These calls have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething()
  {
      // REMOVE the call below.
      RuntimeHelpers.ProbeForSufficientStack();

      // (Remainder of your method logic here.)
  }
  ```

- <span data-ttu-id="35671-113">Wenn Sie `RuntimeHelpers.PrepareConstrainedRegions` aufrufen, entfernen Sie den Aufruf.</span><span class="sxs-lookup"><span data-stu-id="35671-113">If you are calling `RuntimeHelpers.PrepareConstrainedRegions`, remove the call.</span></span> <span data-ttu-id="35671-114">Dieser Aufruf hat keine Auswirkung auf .NET 5.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="35671-114">This call has no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething_Old()
  {
      // REMOVE the call below.
      RuntimeHelpers.PrepareConstrainedRegions();
      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }

  public void DoSomething_Corrected()
  {
      // There is no call to PrepareConstrainedRegions. It's a normal try / finally block.

      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

- <span data-ttu-id="35671-115">Wenn Sie `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup` aufrufen, ersetzen Sie den Aufruf durch einen Standardblock _try / catch / finally_.</span><span class="sxs-lookup"><span data-stu-id="35671-115">If you are calling `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`, replace the call with a standard _try / catch / finally_ block.</span></span>

  ```csharp
  // The sample below produces warning SYSLIB0004.
  public void DoSomething_Old()
  {
      RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(MyTryCode, MyCleanupCode, null);
  }
  public void MyTryCode(object state) { /* try code */ }
  public void MyCleanupCode(object state, bool exceptionThrown) { /* cleanup code */ }

  // The corrected sample below does not produce warning SYSLIB0004.
  public void DoSomething_Corrected()
  {
      try
      {
          // try code
      }
      catch (Exception ex)
      {
          // exception handling code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="35671-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35671-116">See also</span></span>

- [<span data-ttu-id="35671-117">Eingeschränkte Ausführungsbereiche</span><span class="sxs-lookup"><span data-stu-id="35671-117">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
