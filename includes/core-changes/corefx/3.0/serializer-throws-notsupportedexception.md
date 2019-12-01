---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568240"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="e2315-101">JSON-Serialisierungsausnahmetyp von `JsonException` in `NotSupportedException` geändert</span><span class="sxs-lookup"><span data-stu-id="e2315-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="e2315-102">In .NET Core 3.0 Vorschau 6 bis 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="e2315-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="e2315-103">Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul stattdessen eine <xref:System.NotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="e2315-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e2315-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e2315-104">Change description</span></span>

<span data-ttu-id="e2315-105">In .NET Core 3.0 Vorschau 6 bis Vorschau 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="e2315-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="e2315-106">Ein *nicht unterstützter abgeleiteter Sammlungstyp* ist ein beliebiger Sammlungstyp, der keinem der folgenden Typen zugewiesen werden kann:</span><span class="sxs-lookup"><span data-stu-id="e2315-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="e2315-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="e2315-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="e2315-108">Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul eine <xref:System.NotSupportedException> aus, wenn ein nicht unterstützter Auflistungstyp vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e2315-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="e2315-109">Der neue Ausnahmetyp spiegelt besser wider, warum der Deserialisierungsvorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e2315-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e2315-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e2315-110">Version introduced</span></span>

<span data-ttu-id="e2315-111">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="e2315-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e2315-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="e2315-112">Recommended action</span></span>

<span data-ttu-id="e2315-113">Wenn Sie <xref:System.Text.Json.JsonException> bei der Deserialisierung abfangen, sollten Sie auch <xref:System.NotSupportedException> abfangen.</span><span class="sxs-lookup"><span data-stu-id="e2315-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="e2315-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e2315-114">Category</span></span>

<span data-ttu-id="e2315-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="e2315-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e2315-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e2315-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
