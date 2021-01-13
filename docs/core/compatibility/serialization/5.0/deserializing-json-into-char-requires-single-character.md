---
title: 'Breaking Change: Die Deserialisierung von Char erfordert Zeichenfolgen mit einzelnem Zeichen'
description: Hier erfahren Sie mehr über die Breaking Change in .NET 5.0, bei der System.Text.Json bei der Deserialisierung in ein Char-Ziel eine Zeichenfolge mit einem einzelnen Zeichen im JSON-Format erfordert.
ms.date: 12/15/2020
ms.openlocfilehash: 39a2d25b00bf8855cfbf46a4d78b8545052703e5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633870"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a><span data-ttu-id="a6f41-103">System.Text.Json erfordert zum Deserialisieren eines Chars eine Zeichenfolge mit einem einzelnen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a6f41-103">System.Text.Json requires single-char string to deserialize a char</span></span>

<span data-ttu-id="a6f41-104">Um ein <xref:System.Char> mit <xref:System.Text.Json> erfolgreich zu deserialisieren, muss die JSON-Zeichenfolge ein einzelnes Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a6f41-104">To successfully deserialize a <xref:System.Char> using <xref:System.Text.Json>, the JSON string must contain a single character.</span></span>

## <a name="change-description"></a><span data-ttu-id="a6f41-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a6f41-105">Change description</span></span>

<span data-ttu-id="a6f41-106">In bisherigen .NET-Versionen wurde eine Zeichenfolge mit mehreren `char`-Variablen in der JSON-Datei erfolgreich in eine `char`-Eigenschaft oder ein CHAR-Feld deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="a6f41-106">In previous .NET versions, a multi-`char` string in the JSON is successfully deserialized to a `char` property or field.</span></span> <span data-ttu-id="a6f41-107">Es wird nur der erste `char` der Zeichenfolge verwendet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a6f41-107">Only the first `char` of the string is used, as in the following example:</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

<span data-ttu-id="a6f41-108">In .NET 5.0 und höher bewirkt etwas anderes wie eine Zeichenfolge mit einem einzelnen `char`, dass eine <xref:System.Text.Json.JsonException>-Ausnahme ausgelöst wird, wenn es sich bei dem Deserialisierungsziel um ein `char` handelt.</span><span class="sxs-lookup"><span data-stu-id="a6f41-108">In .NET 5.0 and later, anything other than a single-`char` string causes a <xref:System.Text.Json.JsonException> to be thrown when the deserialization target is a `char`.</span></span> <span data-ttu-id="a6f41-109">Die folgende Beispielzeichenfolge wird in allen .NET-Versionen erfolgreich deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="a6f41-109">The following example string is successfully deserialized in all .NET versions:</span></span>

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="a6f41-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a6f41-110">Version introduced</span></span>

<span data-ttu-id="a6f41-111">5.0</span><span class="sxs-lookup"><span data-stu-id="a6f41-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a6f41-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a6f41-112">Reason for change</span></span>

<span data-ttu-id="a6f41-113">Das Parsen für die Deserialisierung sollte nur erfolgreich sein, wenn die bereitgestellten Nutzdaten für den Zieltyp gültig sind.</span><span class="sxs-lookup"><span data-stu-id="a6f41-113">Parsing for deserialization should only succeed when the provided payload is valid for the target type.</span></span> <span data-ttu-id="a6f41-114">Bei einem `char`-Typ bestehen gültige Nutzdaten aus einer Zeichenfolge mit einem einzelnen `char`-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a6f41-114">For a `char` type, the only valid payload is a single-`char` string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a6f41-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a6f41-115">Recommended action</span></span>

<span data-ttu-id="a6f41-116">Wenn Sie JSON-Werte in ein `char`-Ziel deserialisieren, stellen Sie sicher, dass die Zeichenfolge aus einem einzelnen `char` besteht.</span><span class="sxs-lookup"><span data-stu-id="a6f41-116">When you deserialize JSON into a `char` target, make sure the string consists of a single `char`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a6f41-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a6f41-117">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
