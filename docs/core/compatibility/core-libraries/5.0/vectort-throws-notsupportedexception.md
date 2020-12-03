---
title: 'Breaking Change: Vector<T> löst „NotSupportedException“ aus.'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Vector<T> immer eine Ausnahme für nicht unterstützte Typparameter auslöst.
ms.date: 11/01/2020
ms.openlocfilehash: 63db7c6b720735b180ed11098227b31a14008f74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759464"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="5a5a6-103">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="5a5a6-103">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="5a5a6-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> löst jetzt immer eine <xref:System.NotSupportedException> für nicht unterstützte Typparameter aus.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

## <a name="change-description"></a><span data-ttu-id="5a5a6-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5a5a6-105">Change description</span></span>

<span data-ttu-id="5a5a6-106">Früher lösten Member von <xref:System.Numerics.Vector%601> nicht immer eine <xref:System.NotSupportedException> aus, wenn `T` ein [nicht unterstützter Typ](#unsupported-types) war.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-106">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="5a5a6-107">Die Ausnahme wurde nicht immer ausgelöst, weil Codepfade die Hardwarebeschleunigung unterstützten.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-107">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="5a5a6-108">Auf Plattformen ohne Hardwarebeschleunigung – wie etwa ARM32 –gab `Vector<bool> + Vector<bool>` beispielsweise `default` zurück, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-108">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="5a5a6-109">Bei nicht unterstützten Typen zeigten <xref:System.Numerics.Vector%601>-Member für verschiedene Plattformen und Hardwarekonfigurationen ein inkonsistentes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-109">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="5a5a6-110">Ab .NET 5.0 lösen <xref:System.Numerics.Vector%601>-Member in allen Hardwarekonfigurationen immer eine <xref:System.NotSupportedException> aus, wenn `T` kein unterstützter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-110">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

### <a name="unsupported-types"></a><span data-ttu-id="5a5a6-111">Nicht unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="5a5a6-111">Unsupported types</span></span>

<span data-ttu-id="5a5a6-112">Der Typparameter von <xref:System.Numerics.Vector%601> unterstützt folgende Typen:</span><span class="sxs-lookup"><span data-stu-id="5a5a6-112">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="5a5a6-113">Die unterstützten Typen haben sich nicht geändert, eine Änderung in der Zukunft ist jedoch möglich.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-113">The supported types have not changed, however, they may change in the future.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5a5a6-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5a5a6-114">Version introduced</span></span>

<span data-ttu-id="5a5a6-115">5.0</span><span class="sxs-lookup"><span data-stu-id="5a5a6-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5a5a6-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="5a5a6-116">Recommended action</span></span>

<span data-ttu-id="5a5a6-117">Verwenden Sie keinen nicht unterstützten Typ für den Typparameter von <xref:System.Numerics.Vector%601>.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-117">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5a5a6-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5a5a6-118">Affected APIs</span></span>

- <span data-ttu-id="5a5a6-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> und alle zugehörigen Member</span><span class="sxs-lookup"><span data-stu-id="5a5a6-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
