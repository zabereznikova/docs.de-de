---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844504"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="a7ec6-101">JsonSerializer.Deserialize erfordert Zeichenfolgen mit einzelnem Zeichen</span><span class="sxs-lookup"><span data-stu-id="a7ec6-101">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="a7ec6-102">Wenn der Typparameter <xref:System.Char> ist, muss das Zeichenfolgenargument für <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> ein einzelnes Zeichen enthalten, damit die Deserialisierung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-102">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a7ec6-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a7ec6-103">Change description</span></span>

<span data-ttu-id="a7ec6-104">In bisherigen .NET-Versionen war die Deserialisierung erfolgreich, wenn Sie eine Zeichenfolge mit mehreren Zeichen an <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> übergeben und der Typparameter <xref:System.Char> ist, und nur das erste Zeichen wird deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-104">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="a7ec6-105">In .NET 5.0 und höher wird eine <xref:System.Text.Json.JsonException>-Ausnahme ausgelöst, wenn der Parameter <xref:System.Char> ist und etwas anderes wie eine Zeichenfolge mit einzelnem Zeichen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-105">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a><span data-ttu-id="a7ec6-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a7ec6-106">Version introduced</span></span>

<span data-ttu-id="a7ec6-107">5.0</span><span class="sxs-lookup"><span data-stu-id="a7ec6-107">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a7ec6-108">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a7ec6-108">Reason for change</span></span>

<span data-ttu-id="a7ec6-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analysiert den Text, der einen einzelnen JSON-Wert darstellt, in eine Instanz des Typs, der durch einen generischen Typparameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="a7ec6-110">Das Parsen sollte nur erfolgreich sein, wenn die bereitgestellten Nutzdaten für den angegebenen generischen Typparameter gültig sind.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-110">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="a7ec6-111">Für einen <xref:System.Char>-Werttyp bestehen gültige Nutzdaten aus einer Zeichenfolge mit einzelnem Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-111">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a7ec6-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a7ec6-112">Recommended action</span></span>

<span data-ttu-id="a7ec6-113">Beim Parsen einer Zeichenfolge in einen <xref:System.Char>-Typ mithilfe von <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> sollten Sie dafür sorgen, dass die Zeichenfolge aus einem einzelnen Zeichen besteht.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-113">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

#### <a name="category"></a><span data-ttu-id="a7ec6-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a7ec6-114">Category</span></span>

<span data-ttu-id="a7ec6-115">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="a7ec6-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a7ec6-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a7ec6-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
