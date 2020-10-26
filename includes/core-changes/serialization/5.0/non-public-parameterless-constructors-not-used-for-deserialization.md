---
ms.openlocfilehash: 3692848a0cbd4bbbe3c7bb4d2c22a2b19de732e4
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050466"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="373f5-101">Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="373f5-101">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="373f5-102">Aus Gründen der Konsistenz in allen unterstützten Zielframeworkmonikern (TFMs) werden nicht öffentliche, parameterlose Konstruktoren nicht mehr standardmäßig für die Deserialisierung mit <xref:System.Text.Json.JsonSerializer> verwendet.</span><span class="sxs-lookup"><span data-stu-id="373f5-102">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="373f5-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="373f5-103">Change description</span></span>

<span data-ttu-id="373f5-104">Die eigenständigen [System.Text.Json-NuGet-Pakete](https://www.nuget.org/packages/System.Text.Json/), die .NET Standard 2.0 und die höheren Versionen 4.6.0 bis 4.7.2 unterstützen, verhalten sich im Vergleich zum integrierten Verhalten in .NET Core 3.0 und 3.1 inkonsistent.</span><span class="sxs-lookup"><span data-stu-id="373f5-104">The standalone [System.Text.Json NuGet packages](https://www.nuget.org/packages/System.Text.Json/) that support .NET Standard 2.0 and higher, that is, versions 4.6.0-4.7.2, behave inconsistently with the built-in behavior on .NET Core 3.0 and 3.1.</span></span> <span data-ttu-id="373f5-105">In .NET Core 3.x können interne und private Konstruktoren für die Deserialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="373f5-105">On .NET Core 3.x, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="373f5-106">In den eigenständigen Paketen sind nicht öffentliche Konstruktoren nicht zulässig, und eine <xref:System.MissingMethodException> wird ausgelöst, wenn kein öffentlicher, parameterloser Konstruktor definiert ist.</span><span class="sxs-lookup"><span data-stu-id="373f5-106">In the standalone packages, non-public constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="373f5-107">Ab .NET 5.0 und dem System.Text.Json-NuGet-Paket 5.0.0 ist das Verhalten des NuGet-Pakets und der integrierten APIs konsistent.</span><span class="sxs-lookup"><span data-stu-id="373f5-107">Starting with .NET 5.0 and System.Text.Json NuGet package 5.0.0, the behavior is consistent between the NuGet package and the built-in APIs.</span></span> <span data-ttu-id="373f5-108">Nicht öffentliche Konstruktoren einschließlich parameterloser Konstruktoren werden vom Serialisierungsprogramm standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="373f5-108">Non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="373f5-109">Das Serialisierungsprogramm verwendet einen der folgenden Konstruktoren für die Deserialisierung:</span><span class="sxs-lookup"><span data-stu-id="373f5-109">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="373f5-110">öffentlicher Konstruktor mit der Anmerkung <xref:System.Text.Json.Serialization.JsonConstructorAttribute></span><span class="sxs-lookup"><span data-stu-id="373f5-110">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="373f5-111">öffentlicher, parameterloser Konstruktor</span><span class="sxs-lookup"><span data-stu-id="373f5-111">Public parameterless constructor.</span></span>
- <span data-ttu-id="373f5-112">öffentlicher, parametrisierter Konstruktor (falls dies der einzige öffentliche Konstruktor ist)</span><span class="sxs-lookup"><span data-stu-id="373f5-112">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="373f5-113">Wenn keiner dieser Konstruktoren verfügbar ist, wird eine <xref:System.NotSupportedException> ausgelöst, wenn Sie versuchen, den Typ zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="373f5-113">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="373f5-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="373f5-114">Version introduced</span></span>

<span data-ttu-id="373f5-115">5.0</span><span class="sxs-lookup"><span data-stu-id="373f5-115">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="373f5-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="373f5-116">Reason for change</span></span>

- <span data-ttu-id="373f5-117">Es soll ein konsistentes Verhalten aller Zielframeworkmoniker (TFMs) erzwungen werden, die <xref:System.Text.Json?displayProperty=fullName> für .NET Core 3.0 und höhere Versionen sowie .NET Standard 2.0 erstellt.</span><span class="sxs-lookup"><span data-stu-id="373f5-117">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions and .NET Standard 2.0)</span></span>
- <span data-ttu-id="373f5-118"><xref:System.Text.Json.JsonSerializer> soll den nicht öffentlichen Oberflächenbereich eines Typs nicht aufrufen, egal, ob es sich um einen Konstruktor, eine Eigenschaft oder ein Feld handelt.</span><span class="sxs-lookup"><span data-stu-id="373f5-118">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="373f5-119">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="373f5-119">Recommended action</span></span>

- <span data-ttu-id="373f5-120">Wenn Sie über den Typ verfügen, veröffentlichen Sie nach Möglichkeit den parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="373f5-120">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="373f5-121">Implementieren Sie andernfalls einen `JsonConverter<T>` für den Typ, und steuern Sie das Deserialisierungsverhalten.</span><span class="sxs-lookup"><span data-stu-id="373f5-121">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="373f5-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="373f5-122">Category</span></span>

<span data-ttu-id="373f5-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="373f5-123">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="373f5-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="373f5-124">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
