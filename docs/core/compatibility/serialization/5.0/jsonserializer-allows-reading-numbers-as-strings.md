---
title: 'Breaking Change: ASP.NET Core-Apps erlauben die Deserialisierung von Zahlen in Anführungszeichen'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den ASP.NET Core-Apps alle Zahlen, die als JSON-Zeichenfolgen dargestellt sind, erfolgreich deserialisieren, anstatt eine Ausnahme auszulösen.
ms.date: 10/21/2020
ms.openlocfilehash: fc8a4c6638be391c22c7cfb2fc7c216c88377f29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759369"
---
# <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="5a186-103">ASP.NET Core-Apps erlauben die Deserialisierung von Zahlen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="5a186-103">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="5a186-104">Ab .NET 5.0 verwenden ASP.NET Core-Apps, wie von <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> angegeben, die Standardoptionen für die Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="5a186-104">Starting in .NET 5.0, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a186-105">Die <xref:System.Text.Json.JsonSerializerDefaults.Web>-Optionen umfassen das Festlegen von <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> auf <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a186-105">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a186-106">Diese Änderung bedeutet, dass ASP.NET Core-Apps alle Zahlen, die als JSON-Zeichenfolgen dargestellt sind, erfolgreich deserialisieren können, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="5a186-106">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings instead of throwing an exception.</span></span>

## <a name="change-description"></a><span data-ttu-id="5a186-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5a186-107">Change description</span></span>

<span data-ttu-id="5a186-108">In .NET Core 3.0 bis 3.1 löst <xref:System.Text.Json.JsonSerializer> während der Deserialisierung eine Ausnahme des Typs <xref:System.Text.Json.JsonException> aus, wenn JSON-Nutzdaten eine Zahl in Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a186-108">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="5a186-109">Mithilfe der in Anführungszeichen gesetzten Zahlen werden Zuordnungen zu Zahleneigenschaften in Objektgraphen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="5a186-109">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="5a186-110">In .NET Core 3.0 bis 3.1 werden Zahlen nur aus <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType>-Token gelesen.</span><span class="sxs-lookup"><span data-stu-id="5a186-110">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="5a186-111">Ab .NET 5.0 gelten in Anführungszeichen gesetzte Zahlen in JSON-Nutzdaten für ASP.NET Core-Apps standardmäßig als gültig.</span><span class="sxs-lookup"><span data-stu-id="5a186-111">Starting in .NET 5.0, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="5a186-112">Während der Deserialisierung von in Anführungszeichen gesetzten Zahlen wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5a186-112">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="5a186-113">Es gibt keinen Behavior Change für die eigenständigen Standardklassen <xref:System.Text.Json.JsonSerializer> oder <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="5a186-113">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="5a186-114">Dies ist fachlich gesehen kein Breaking Change, da diese Änderung zu liberaleren statt restriktiveren Szenarios führt (d. h., eine JSON-Zeichenfolge wird erfolgreich in eine Zahl konvertiert, anstatt eine Ausnahme auszulösen).</span><span class="sxs-lookup"><span data-stu-id="5a186-114">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="5a186-115">Da es sich hierbei jedoch um einen bedeutenden Behavior Change handelt, der sich auf viele ASP.NET Core-Apps auswirkt, wird er hier dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="5a186-115">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="5a186-116">Die Erweiterungsmethoden <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> und <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> verwenden ebenfalls die <xref:System.Text.Json.JsonSerializerDefaults.Web>-Serialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="5a186-116">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5a186-117">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5a186-117">Version introduced</span></span>

<span data-ttu-id="5a186-118">5.0</span><span class="sxs-lookup"><span data-stu-id="5a186-118">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5a186-119">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="5a186-119">Reason for change</span></span>

<span data-ttu-id="5a186-120">Viele Benutzer haben um eine Möglichkeit für einen liberaleren Umgang mit Zahlen in <xref:System.Text.Json.JsonSerializer> gebeten.</span><span class="sxs-lookup"><span data-stu-id="5a186-120">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="5a186-121">Dieses Feedback zeigt, dass viele Entitäten, die JSON erzeugen (z. B. Dienste im Web), Zahlen in Anführungszeichen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="5a186-121">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="5a186-122">Wenn Sie das Lesen von in Anführungszeichen gesetzten Zahlen zulassen (Deserialisierung), können .NET-Apps diese Nutzdaten standardmäßig erfolgreich in Webkontexten analysieren.</span><span class="sxs-lookup"><span data-stu-id="5a186-122">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="5a186-123">Die Konfiguration wird über <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> verfügbar gemacht, sodass Sie dieselben Optionen für verschiedene Anwendungsebenen angeben können, z. B. Client, Server und freigegeben.</span><span class="sxs-lookup"><span data-stu-id="5a186-123">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5a186-124">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="5a186-124">Recommended action</span></span>

<span data-ttu-id="5a186-125">Ist diese Änderung disruptiv, weil Sie z. B. bei Überprüfungen von einer strikten Zahlenverarbeitung abhängig sind, können Sie das vorherige Verhalten wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="5a186-125">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="5a186-126">Legen Sie einfach die Option <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> auf <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType> fest.</span><span class="sxs-lookup"><span data-stu-id="5a186-126">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="5a186-127">Für MVC- und Web-API-Apps in ASP.NET Core können Sie mithilfe des folgenden Codes die Option in `Startup` konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5a186-127">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

## <a name="affected-apis"></a><span data-ttu-id="5a186-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5a186-128">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

- ASP.NET Core
- Serialization

-->
