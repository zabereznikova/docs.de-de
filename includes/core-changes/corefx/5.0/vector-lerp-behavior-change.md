---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281300"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="592eb-101">Behavior Change für Vector2.Lerp und Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="592eb-101">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="592eb-102">Die Implementierung von <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> und <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> wurde so geändert, dass ein Rundungsfehler bei Gleitkommazahlen nun ordnungsgemäß berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="592eb-102">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

#### <a name="change-description"></a><span data-ttu-id="592eb-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="592eb-103">Change description</span></span>

<span data-ttu-id="592eb-104">Bisher waren <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> und <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> als `value1 + (value2 - value1) * amount` implementiert.</span><span class="sxs-lookup"><span data-stu-id="592eb-104">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="592eb-105">Aufgrund eines Rundungsfehlers bei Gleitkommazahlen gibt dieser Algorithmus nicht immer `value2` zurück, wenn `amount` auf `1.0f` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="592eb-105">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="592eb-106">Ab .NET 5.0 verwendet die Implementierung denselben Algorithmus wie <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, nämlich `(value1 * (1.0f - amount)) + (value2 * amount)`.</span><span class="sxs-lookup"><span data-stu-id="592eb-106">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="592eb-107">Dieser Algorithmus berücksichtigt den Rundungsfehler nun ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="592eb-107">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="592eb-108">Wenn `amount` nun also auf `1.0f` festgelegt ist, beträgt das Ergebnis genau `value2`.</span><span class="sxs-lookup"><span data-stu-id="592eb-108">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="592eb-109">Der aktualisierte Algorithmus ermöglicht es auch, dass der Algorithmus mithilfe von <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> (wenn verfügbar) frei optimiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="592eb-109">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="592eb-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="592eb-110">Version introduced</span></span>

<span data-ttu-id="592eb-111">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="592eb-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="592eb-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="592eb-112">Recommended action</span></span>

<span data-ttu-id="592eb-113">Es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="592eb-113">No action is necessary.</span></span> <span data-ttu-id="592eb-114">Wenn Sie das ehemalige Verhalten jedoch beibehalten möchten, können Sie eine eigene `Lerp`-Funktion implementieren, die den vorherigen Algorithmus von `value1 + (value2 - value1) * amount` verwendet.</span><span class="sxs-lookup"><span data-stu-id="592eb-114">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

#### <a name="category"></a><span data-ttu-id="592eb-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="592eb-115">Category</span></span>

<span data-ttu-id="592eb-116">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="592eb-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="592eb-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="592eb-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
