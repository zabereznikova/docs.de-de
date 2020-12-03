---
title: 'Breaking Change: Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den öffentliche parameterlose Konstruktoren nicht mehr für die Deserialisierung mit JsonSerializer verwendet werden.
ms.date: 10/18/2020
ms.openlocfilehash: 6bdcc92c61008aa4ee27370bbac4dbf4ee3ef7c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759530"
---
# <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="f735f-103">Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="f735f-103">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="f735f-104">Aus Gründen der Konsistenz in allen unterstützten Zielframeworkmonikern (TFMs) werden nicht öffentliche, parameterlose Konstruktoren nicht mehr standardmäßig für die Deserialisierung mit <xref:System.Text.Json.JsonSerializer> verwendet.</span><span class="sxs-lookup"><span data-stu-id="f735f-104">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

## <a name="change-description"></a><span data-ttu-id="f735f-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f735f-105">Change description</span></span>

<span data-ttu-id="f735f-106">Die eigenständigen [System.Text.Json-NuGet-Pakete](https://www.nuget.org/packages/System.Text.Json/), die .NET Standard 2.0 und die höheren Versionen 4.6.0 bis 4.7.2 unterstützen, verhalten sich im Vergleich zum integrierten Verhalten in .NET Core 3.0 und 3.1 inkonsistent.</span><span class="sxs-lookup"><span data-stu-id="f735f-106">The standalone [System.Text.Json NuGet packages](https://www.nuget.org/packages/System.Text.Json/) that support .NET Standard 2.0 and higher, that is, versions 4.6.0-4.7.2, behave inconsistently with the built-in behavior on .NET Core 3.0 and 3.1.</span></span> <span data-ttu-id="f735f-107">In .NET Core 3.x können interne und private Konstruktoren für die Deserialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f735f-107">On .NET Core 3.x, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="f735f-108">In den eigenständigen Paketen sind nicht öffentliche Konstruktoren nicht zulässig, und eine <xref:System.MissingMethodException> wird ausgelöst, wenn kein öffentlicher, parameterloser Konstruktor definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f735f-108">In the standalone packages, non-public constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="f735f-109">Ab .NET 5.0 und dem System.Text.Json-NuGet-Paket 5.0.0 ist das Verhalten des NuGet-Pakets und der integrierten APIs konsistent.</span><span class="sxs-lookup"><span data-stu-id="f735f-109">Starting with .NET 5.0 and System.Text.Json NuGet package 5.0.0, the behavior is consistent between the NuGet package and the built-in APIs.</span></span> <span data-ttu-id="f735f-110">Nicht öffentliche Konstruktoren einschließlich parameterloser Konstruktoren werden vom Serialisierungsprogramm standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f735f-110">Non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="f735f-111">Das Serialisierungsprogramm verwendet einen der folgenden Konstruktoren für die Deserialisierung:</span><span class="sxs-lookup"><span data-stu-id="f735f-111">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="f735f-112">öffentlicher Konstruktor mit der Anmerkung <xref:System.Text.Json.Serialization.JsonConstructorAttribute></span><span class="sxs-lookup"><span data-stu-id="f735f-112">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="f735f-113">öffentlicher, parameterloser Konstruktor</span><span class="sxs-lookup"><span data-stu-id="f735f-113">Public parameterless constructor.</span></span>
- <span data-ttu-id="f735f-114">öffentlicher, parametrisierter Konstruktor (falls dies der einzige öffentliche Konstruktor ist)</span><span class="sxs-lookup"><span data-stu-id="f735f-114">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="f735f-115">Wenn keiner dieser Konstruktoren verfügbar ist, wird eine <xref:System.NotSupportedException> ausgelöst, wenn Sie versuchen, den Typ zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="f735f-115">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f735f-116">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f735f-116">Version introduced</span></span>

<span data-ttu-id="f735f-117">5.0</span><span class="sxs-lookup"><span data-stu-id="f735f-117">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f735f-118">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f735f-118">Reason for change</span></span>

- <span data-ttu-id="f735f-119">Es soll ein konsistentes Verhalten aller Zielframeworkmoniker (TFMs) erzwungen werden, die <xref:System.Text.Json?displayProperty=fullName> für .NET Core 3.0 und höhere Versionen sowie .NET Standard 2.0 erstellt.</span><span class="sxs-lookup"><span data-stu-id="f735f-119">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions and .NET Standard 2.0)</span></span>
- <span data-ttu-id="f735f-120"><xref:System.Text.Json.JsonSerializer> soll den nicht öffentlichen Oberflächenbereich eines Typs nicht aufrufen, egal, ob es sich um einen Konstruktor, eine Eigenschaft oder ein Feld handelt.</span><span class="sxs-lookup"><span data-stu-id="f735f-120">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f735f-121">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f735f-121">Recommended action</span></span>

- <span data-ttu-id="f735f-122">Wenn Sie über den Typ verfügen, veröffentlichen Sie nach Möglichkeit den parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f735f-122">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="f735f-123">Implementieren Sie andernfalls einen `JsonConverter<T>` für den Typ, und steuern Sie das Deserialisierungsverhalten.</span><span class="sxs-lookup"><span data-stu-id="f735f-123">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f735f-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f735f-124">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
