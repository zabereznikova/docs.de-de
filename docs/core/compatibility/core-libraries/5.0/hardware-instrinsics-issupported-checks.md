---
title: 'Breaking Change: Hardwareintrinsische IsSupported-Überprüfungen können für geschachtelte Typen abweichen'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Überprüfung von X64.IsSupported auf intrinsische Hardwarefunktionen jetzt gegebenenfalls andere Ergebnisse zurückgibt.
ms.date: 11/01/2020
ms.openlocfilehash: 9acef15860de76a9743621cb4c5edba5aac3931c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759483"
---
# <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="abde6-103">Hardwareintrinsische IsSupported-Überprüfungen können für geschachtelte Typen abweichen</span><span class="sxs-lookup"><span data-stu-id="abde6-103">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="abde6-104">Bei der Überprüfung von `<Isa>.X64.IsSupported`, wobei `<Isa>` auf die Klassen im Namespace <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> verweist, kann das Ergebnis jetzt von früheren .NET-Versionen abweichen.</span><span class="sxs-lookup"><span data-stu-id="abde6-104">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="abde6-105">*ISA* steht für Industriestandardarchitektur.</span><span class="sxs-lookup"><span data-stu-id="abde6-105">*ISA* stands for industry standard architecture.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="abde6-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="abde6-106">Version introduced</span></span>

<span data-ttu-id="abde6-107">5.0</span><span class="sxs-lookup"><span data-stu-id="abde6-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="abde6-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="abde6-108">Change description</span></span>

<span data-ttu-id="abde6-109">In früheren .NET-Versionen machten einige der hardwareintrinsischen <xref:System.Runtime.Intrinsics.X86>-Typen wie <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> keine geschachtelte `X64`-Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="abde6-109">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="abde6-110">Für diese Typen wurde der Aufruf von `<Isa>.X64.IsSupported` in eine `IsSupported`-Eigenschaft in einer geschachtelten `X64`-Klasse aufgelöst, der die Klasse `<Isa>` übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="abde6-110">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="abde6-111">Das bedeutete, dass die Eigenschaft `true` zurückgeben konnte, auch wenn `<Isa>.IsSupported` `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="abde6-111">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="abde6-112">In .NET 5.0 und höher machen alle <xref:System.Runtime.Intrinsics.X86>-Typen eine geschachtelte `X64`-Klasse verfügbar, die Unterstützung entsprechend meldet.</span><span class="sxs-lookup"><span data-stu-id="abde6-112">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="abde6-113">Dadurch wird sichergestellt, dass die allgemeine Hierarchie korrekt erhalten bleibt. Wenn `<Isa>.X64.IsSupported` `true` entspricht, kann zudem angenommen werden, dass `<Isa>.IsSupported` `true` entspricht.</span><span class="sxs-lookup"><span data-stu-id="abde6-113">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="abde6-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="abde6-114">Reason for change</span></span>

<span data-ttu-id="abde6-115">Wenn `<Isa>.X64.IsSupported` `true` entspricht, ist beabsichtigt, dass für `<Isa>.IsSupported` `true` impliziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="abde6-115">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="abde6-116">Aufgrund der Funktionsweise der Memberauflösung in C# führten Klassen ohne geschachtelte `X64`-Klasse in Situationen, in denen das nicht der Fall war, zu Fehlern im Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="abde6-116">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="abde6-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="abde6-117">Recommended action</span></span>

<span data-ttu-id="abde6-118">Passen Sie Code mit Überprüfungen auf `IsSupported` ggf. an, damit die richtige ISA überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="abde6-118">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="abde6-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="abde6-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
