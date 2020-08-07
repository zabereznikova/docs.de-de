---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302709"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="574d2-101">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="574d2-101">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="574d2-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> löst jetzt immer eine <xref:System.NotSupportedException> für nicht unterstützte Typparameter aus.</span><span class="sxs-lookup"><span data-stu-id="574d2-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="574d2-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="574d2-103">Change description</span></span>

<span data-ttu-id="574d2-104">Früher lösten Member von <xref:System.Numerics.Vector%601> nicht immer eine <xref:System.NotSupportedException> aus, wenn `T` ein [nicht unterstützter Typ](#unsupported-types) war.</span><span class="sxs-lookup"><span data-stu-id="574d2-104">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="574d2-105">Die Ausnahme wurde nicht immer ausgelöst, weil Codepfade die Hardwarebeschleunigung unterstützten.</span><span class="sxs-lookup"><span data-stu-id="574d2-105">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="574d2-106">Auf Plattformen ohne Hardwarebeschleunigung – wie etwa ARM32 –gab `Vector<bool> + Vector<bool>` beispielsweise `default` zurück, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="574d2-106">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="574d2-107">Bei nicht unterstützten Typen zeigten <xref:System.Numerics.Vector%601>-Member für verschiedene Plattformen und Hardwarekonfigurationen ein inkonsistentes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="574d2-107">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="574d2-108">Ab .NET 5.0 lösen <xref:System.Numerics.Vector%601>-Member in allen Hardwarekonfigurationen immer eine <xref:System.NotSupportedException> aus, wenn `T` kein unterstützter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="574d2-108">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

##### <a name="unsupported-types"></a><span data-ttu-id="574d2-109">Nicht unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="574d2-109">Unsupported types</span></span>

<span data-ttu-id="574d2-110">Der Typparameter von <xref:System.Numerics.Vector%601> unterstützt folgende Typen:</span><span class="sxs-lookup"><span data-stu-id="574d2-110">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

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

<span data-ttu-id="574d2-111">Die unterstützten Typen haben sich nicht geändert, eine Änderung in der Zukunft ist jedoch möglich.</span><span class="sxs-lookup"><span data-stu-id="574d2-111">The supported types have not changed, however, they may change in the future.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="574d2-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="574d2-112">Version introduced</span></span>

<span data-ttu-id="574d2-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="574d2-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="574d2-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="574d2-114">Recommended action</span></span>

<span data-ttu-id="574d2-115">Verwenden Sie keinen nicht unterstützten Typ für den Typparameter von <xref:System.Numerics.Vector%601>.</span><span class="sxs-lookup"><span data-stu-id="574d2-115">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

#### <a name="category"></a><span data-ttu-id="574d2-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="574d2-116">Category</span></span>

<span data-ttu-id="574d2-117">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="574d2-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="574d2-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="574d2-118">Affected APIs</span></span>

- <span data-ttu-id="574d2-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> und alle zugehörigen Member</span><span class="sxs-lookup"><span data-stu-id="574d2-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
