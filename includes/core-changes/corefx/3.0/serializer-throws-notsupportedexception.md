---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021643"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="be42a-101">JSON-Serialisierungsausnahmetyp von `JsonException` in `NotSupportedException` geändert</span><span class="sxs-lookup"><span data-stu-id="be42a-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="be42a-102">In .NET Core 3.0 Vorschau 6 bis 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="be42a-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="be42a-103">Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul stattdessen eine <xref:System.NotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="be42a-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="be42a-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="be42a-104">Change description</span></span>

<span data-ttu-id="be42a-105">In .NET Core 3.0 Vorschau 6 bis Vorschau 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="be42a-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="be42a-106">Ein *nicht unterstützter abgeleiteter Sammlungstyp* ist ein beliebiger Sammlungstyp, der keinem der folgenden Typen zugewiesen werden kann:</span><span class="sxs-lookup"><span data-stu-id="be42a-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="be42a-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="be42a-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="be42a-108">Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul eine <xref:System.NotSupportedException> aus, wenn ein nicht unterstützter Auflistungstyp vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="be42a-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="be42a-109">Der neue Ausnahmetyp spiegelt besser wider, warum der Deserialisierungsvorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="be42a-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="be42a-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="be42a-110">Version introduced</span></span>

<span data-ttu-id="be42a-111">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="be42a-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="be42a-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="be42a-112">Recommended action</span></span>

<span data-ttu-id="be42a-113">Wenn Sie <xref:System.Text.Json.JsonException> bei der Deserialisierung abfangen, sollten Sie auch <xref:System.NotSupportedException> abfangen.</span><span class="sxs-lookup"><span data-stu-id="be42a-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="be42a-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="be42a-114">Category</span></span>

<span data-ttu-id="be42a-115">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="be42a-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="be42a-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="be42a-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
