---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496466"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="edda3-101">WPF DispatcherSynchronizationContext.CreateCopy gibt jetzt anstelle der aktuellen Instanz eine neue Kopie zurück</span><span class="sxs-lookup"><span data-stu-id="edda3-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="edda3-102">Details</span><span class="sxs-lookup"><span data-stu-id="edda3-102">Details</span></span>

<span data-ttu-id="edda3-103">In .NET Framework 4 hat <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> in erster Linie einen Verweis auf die aktuelle Instanz zurückgegeben, um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="edda3-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="edda3-104">In .NET Framework 4.5 wird eine neue Instanz zurückgegeben, wodurch es erstmalig möglich ist zu Schlussfolgern, dass gleiche Verweise angeben, dass sich der ausführende Thread im richtigen Synchronisierungskontext befindet.</span><span class="sxs-lookup"><span data-stu-id="edda3-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="edda3-105">Es ist unwahrscheinlich, dass Code, der die Identität dieser Verweise prüft, betroffen ist. Aber aufgrund der Änderung sollte Code, der <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> aufruft, im Rahmen der Migration zu .NET Framework 4.5 oder einer höheren Version getestet werden.</span><span class="sxs-lookup"><span data-stu-id="edda3-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="edda3-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="edda3-106">Suggestion</span></span>

<span data-ttu-id="edda3-107">Beachten Sie, dass <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> jetzt ein neues <xref:System.Threading.SynchronizationContext?displayProperty=fullName>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="edda3-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="edda3-108">Zuvor wurde Code, der die Gleichheit von Verweisen verwendete, die auf diese Weise generiert wurden, tatsächlich nicht dahingehend überprüft, ob er sich im richtigen Kontext befunden hat. Dies wird jetzt jedoch durchgeführt, wenn bei der Erstellung .NET Framework 4.5 oder höher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="edda3-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="edda3-109">Obwohl es unwahrscheinlich ist, dass dies zu Problemen führt, sollte das Anwenden der betroffenen Codepfade ausreichend sein, um zu ermitteln, ob dies zu Problemen führen kann.</span><span class="sxs-lookup"><span data-stu-id="edda3-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="edda3-110">name</span><span class="sxs-lookup"><span data-stu-id="edda3-110">Name</span></span>    | <span data-ttu-id="edda3-111">Wert</span><span class="sxs-lookup"><span data-stu-id="edda3-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="edda3-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="edda3-112">Scope</span></span>   |<span data-ttu-id="edda3-113">Gering</span><span class="sxs-lookup"><span data-stu-id="edda3-113">Minor</span></span>|
|<span data-ttu-id="edda3-114">Version</span><span class="sxs-lookup"><span data-stu-id="edda3-114">Version</span></span>|<span data-ttu-id="edda3-115">4.5</span><span class="sxs-lookup"><span data-stu-id="edda3-115">4.5</span></span>|
|<span data-ttu-id="edda3-116">Typ</span><span class="sxs-lookup"><span data-stu-id="edda3-116">Type</span></span>|<span data-ttu-id="edda3-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="edda3-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="edda3-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="edda3-118">Affected APIs</span></span>

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
