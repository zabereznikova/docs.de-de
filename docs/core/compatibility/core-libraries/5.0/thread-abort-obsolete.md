---
title: 'Breaking Change: Thread.Abort ist veraltet'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Thread.Abort-APIs als veraltet gelten.
ms.date: 11/01/2020
ms.openlocfilehash: 6d7dfce8fda393bfd88c9b4cf0c59d53942cee25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759220"
---
# <a name="threadabort-is-obsolete"></a><span data-ttu-id="61252-103">Thread.Abort ist veraltet</span><span class="sxs-lookup"><span data-stu-id="61252-103">Thread.Abort is obsolete</span></span>

<span data-ttu-id="61252-104">Die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-APIs sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="61252-104">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="61252-105">Bei Projekten für .NET 5.0 und höher wird bei Aufruf dieser Methoden zur Kompilierzeit die Warnung `SYSLIB0006` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="61252-105">Projects that target .NET 5.0 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

## <a name="change-description"></a><span data-ttu-id="61252-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="61252-106">Change description</span></span>

<span data-ttu-id="61252-107">Zuvor wurden bei Aufrufen von <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> keine Warnungen zur Kompilierzeit erzeugt. Die Methode löste jedoch zur Laufzeit die Ausnahme <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="61252-107">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="61252-108">Ab .NET 5.0 ist <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> mit einer Warnung als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="61252-108">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="61252-109">Beim Aufrufen dieser Methode wird die Compilerwarnung `SYSLIB0006` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="61252-109">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="61252-110">Die Implementierung der Methode bleibt unverändert, und die Ausnahme <xref:System.PlatformNotSupportedException> wird weiterhin ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="61252-110">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="61252-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="61252-111">Reason for change</span></span>

<span data-ttu-id="61252-112">Da <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> immer für alle .NET-Implementierungen außer das .NET Framework die Ausnahme <xref:System.PlatformNotSupportedException> auslöst, wurde der Methode <xref:System.ObsoleteAttribute> hinzugefügt, um die Aufmerksamkeit auf die Stellen zu lenken, an denen diese Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="61252-112">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="61252-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="61252-113">Version introduced</span></span>

<span data-ttu-id="61252-114">5.0</span><span class="sxs-lookup"><span data-stu-id="61252-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="61252-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="61252-115">Recommended action</span></span>

- <span data-ttu-id="61252-116">Verwenden Sie <xref:System.Threading.CancellationToken>, um die Verarbeitung einer Arbeitseinheit abzubrechen, statt <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="61252-116">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="61252-117">Im folgenden Beispiel wird die Verwendung von <xref:System.Threading.CancellationToken> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="61252-117">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

  <span data-ttu-id="61252-118">Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="61252-118">For more information, see [Cancellation in managed threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="61252-119">Unterdrücken Sie den Warnungscode `SYSLIB0006`, um die Warnung zur Kompilierzeit zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="61252-119">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="61252-120">Dieser Warnungscode ist spezifisch für <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Bei seiner Unterdrückung werden folglich in Ihrem Code keine anderen Warnungen aufgrund von veralteten Elementen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="61252-120">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="61252-121">Es wird jedoch empfohlen, die Aufrufe von <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zu entfernen statt die Warnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="61252-121">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="61252-122">Sie können die Warnung auch in der Projektdatei unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="61252-122">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a><span data-ttu-id="61252-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="61252-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
