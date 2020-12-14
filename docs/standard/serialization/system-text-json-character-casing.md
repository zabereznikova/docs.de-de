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
ms.openlocfilehash: 3e2fb8cbdd35e772b5e97c731199f69aa834bd0a
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009741"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="8819b-103">Aktivieren des Abgleichs von Eigenschaftsnamen mit System.Text.Json ohne Berücksichtigung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="8819b-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="8819b-104">In diesem Artikel erfahren Sie, wie Sie den Abgleich von Eigenschaftsnamen mit dem `System.Text.Json`-Namespace ohne Berücksichtigung der Groß-/Kleinschreibung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8819b-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="8819b-105">Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="8819b-105">Case-insensitive property matching</span></span>

<span data-ttu-id="8819b-106">Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht.</span><span class="sxs-lookup"><span data-stu-id="8819b-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="8819b-107">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="8819b-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="8819b-108">Der [Webstandard](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) ist, dass die Groß-/Kleinschreibung nicht berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="8819b-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="8819b-109">Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="8819b-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="8819b-110">Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.</span><span class="sxs-lookup"><span data-stu-id="8819b-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="8819b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8819b-111">See also</span></span>

* [<span data-ttu-id="8819b-112">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="8819b-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8819b-113">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="8819b-113">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="8819b-114">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="8819b-114">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="8819b-115">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="8819b-115">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="8819b-116">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8819b-116">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="8819b-117">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="8819b-117">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="8819b-118">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="8819b-118">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="8819b-119">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="8819b-119">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="8819b-120">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="8819b-120">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="8819b-121">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8819b-121">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="8819b-122">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8819b-122">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="8819b-123">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="8819b-123">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="8819b-124">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="8819b-124">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="8819b-125">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8819b-125">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="8819b-126">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8819b-126">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="8819b-127">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8819b-127">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="8819b-128">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="8819b-128">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
