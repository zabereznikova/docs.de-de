---
title: Aktivieren des Abgleichs von Eigenschaftsnamen mit System.Text.Json ohne Berücksichtigung der Groß-/Kleinschreibung
description: Erfahren Sie, wie Sie in .NET beim Serialisieren in und Deserialisieren aus JSON den Abgleich von Eigenschaftsnamen ohne Berücksichtigung der Groß-/Kleinschreibung aktivieren.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599075"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="4f2a4-103">Aktivieren des Abgleichs von Eigenschaftsnamen mit System.Text.Json ohne Berücksichtigung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="4f2a4-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="4f2a4-104">In diesem Artikel erfahren Sie, wie Sie den Abgleich von Eigenschaftsnamen mit dem `System.Text.Json`-Namespace ohne Berücksichtigung der Groß-/Kleinschreibung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4f2a4-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="4f2a4-105">Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="4f2a4-105">Case-insensitive property matching</span></span>

<span data-ttu-id="4f2a4-106">Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht.</span><span class="sxs-lookup"><span data-stu-id="4f2a4-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="4f2a4-107">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="4f2a4-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="4f2a4-108">Der [Webstandard](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) ist, dass die Groß-/Kleinschreibung nicht berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="4f2a4-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="4f2a4-109">Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="4f2a4-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="4f2a4-110">Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.</span><span class="sxs-lookup"><span data-stu-id="4f2a4-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="4f2a4-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f2a4-111">See also</span></span>

* [<span data-ttu-id="4f2a4-112">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="4f2a4-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="4f2a4-113">Instanziieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="4f2a4-113">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="4f2a4-114">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="4f2a4-114">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="4f2a4-115">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4f2a4-115">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="4f2a4-116">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="4f2a4-116">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="4f2a4-117">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="4f2a4-117">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="4f2a4-118">Beibehalten zirkulärer Verweise</span><span class="sxs-lookup"><span data-stu-id="4f2a4-118">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="4f2a4-119">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="4f2a4-119">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="4f2a4-120">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4f2a4-120">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="4f2a4-121">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4f2a4-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
