---
ms.openlocfilehash: 39d1b2dba8077bf9bf998775f8967d455f36b549
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119083"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="9e5de-101">JSON-Serialisierungsausnahmetyp von `JsonException` in `NotSupportedException` geändert</span><span class="sxs-lookup"><span data-stu-id="9e5de-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="9e5de-102">In .NET Core 3.0 Vorschau 6 bis 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="9e5de-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="9e5de-103">Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul stattdessen eine <xref:System.NotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="9e5de-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9e5de-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9e5de-104">Change description</span></span>

<span data-ttu-id="9e5de-105">In .NET Core 3.0 Vorschau 6 bis Vorschau 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="9e5de-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="9e5de-106">Ein *nicht unterstützter abgeleiteter Sammlungstyp* ist ein beliebiger Sammlungstyp, der keinem der folgenden Typen zugewiesen werden kann:</span><span class="sxs-lookup"><span data-stu-id="9e5de-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

 - <xref:System.Collections.IList>
 - <xref:System.Collections.Generic.ICollection%601>
 - <xref:System.Collections.Generic.Stack%601>
 - <xref:System.Collections.Generic.Queue%601>`
 - <xref:System.Collections.IDictionary>
 - [<span data-ttu-id="9e5de-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="9e5de-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="9e5de-108">Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul eine <xref:System.NotSupportedException> aus, wenn ein nicht unterstützter Auflistungstyp vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9e5de-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="9e5de-109">Der neue Ausnahmetyp spiegelt besser wider, warum der Deserialisierungsvorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="9e5de-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9e5de-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9e5de-110">Version introduced</span></span>

<span data-ttu-id="9e5de-111">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="9e5de-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9e5de-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="9e5de-112">Recommended action</span></span>

<span data-ttu-id="9e5de-113">Wenn Sie <xref:System.Text.Json.JsonException> bei der Deserialisierung abfangen, sollten Sie auch <xref:System.NotSupportedException> abfangen.</span><span class="sxs-lookup"><span data-stu-id="9e5de-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="9e5de-114">Category (Kategorie)</span><span class="sxs-lookup"><span data-stu-id="9e5de-114">Category</span></span>

<span data-ttu-id="9e5de-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="9e5de-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9e5de-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9e5de-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
