---
title: Ignorieren von Eigenschaften mit System.Text.Json
description: Erfahren Sie, wie Eigenschaften bei der Serialisierung mit System.Text.Json in .NET ignoriert werden.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439767"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a>Ignorieren von Eigenschaften mit System.Text.Json

Beim Serialisieren von C#-Objekten in JavaScript Object Notation (JSON) werden standardmäßig alle öffentlichen Eigenschaften serialisiert. Wenn Sie möchten, dass einige von ihnen nicht in der resultierenden JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten. In diesem Artikel erfahren Sie, wie Eigenschaften auf der Grundlage verschiedener Kriterien ignoriert werden:

::: zone pivot="dotnet-5-0"

* [Einzelne Eigenschaften](#ignore-individual-properties)
* [ Alle schreibgeschützten Eigenschaften](#ignore-all-read-only-properties)
* [Alle Nullwert-Eigenschaften](#ignore-all-null-value-properties)
* [Alle Eigenschaften mit Standardwert](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [Einzelne Eigenschaften](#ignore-individual-properties)
* [ Alle schreibgeschützten Eigenschaften](#ignore-all-read-only-properties)
* [Alle Nullwert-Eigenschaften](#ignore-all-null-value-properties)
::: zone-end

## <a name="ignore-individual-properties"></a>Ignorieren einzelner Eigenschaften

Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
Sie können einen bedingten Ausschluss angeben, indem Sie die Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) festlegen. Die Enumeration <xref:System.Text.Json.Serialization.JsonIgnoreCondition> bietet die folgenden Optionen:

* `Always`: Die Eigenschaft wird stets ignoriert. Wenn `Condition` nicht angegeben ist, wird diese Option angenommen.
* `Never`: Die Eigenschaft wird stets serialisiert und deserialisiert, und zwar unabhängig von den globalen Einstellungen `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` und `IgnoreReadOnlyFields`.
* `WhenWritingDefault`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um einen Verweistyp `null`, einen Nullwerte zulassenden Typ `null` oder einen Werttyp `default` handelt.
* `WhenWritingNull`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um einen Verweistyp `null` oder einen Nullwerte zulassenden Typ `null` handelt.

Das folgende Beispiel veranschaulicht die Verwendung der Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a>Ignorieren aller schreibgeschützten Eigenschaften

Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält. Um alle schreibgeschützten Eigenschaften bei der Serialisierung zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Diese Option gilt nur für Serialisierung. Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.

::: zone pivot="dotnet-5-0"
Diese Option gilt nur für Eigenschaften. Um schreibgeschützte Felder beim [Serialisieren von Feldern](system-text-json-how-to.md#include-fields) zu ignorieren, verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

## <a name="ignore-all-null-value-properties"></a>Ignorieren aller Eigenschaften mit dem Wert NULL

::: zone pivot="dotnet-5-0"
Um alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull> fest:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
Um bei der Serialisierung alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> auf `true` fest:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:

| Eigenschaft             | Wert                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a>Ignorieren aller Eigenschaften mit Standardwert

::: zone pivot="dotnet-5-0"
Um die Serialisierung von Standardwerten in Werttypeigenschaften zu verhindern, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> fest:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

Die Einstellung <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> verhindert auch die Serialisierung von Verweistypeigenschaften mit dem Wert NULL und Nullwerte zulassenden Typeigenschaften.

::: zone pivot="dotnet-core-3-1"
Es gibt keine in . NET Core 3.1 integrierte Möglichkeit, die Serialisierung von Eigenschaften mit Standardwerttypen in `System.Text.Json` zu verhindern.
::: zone-end

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
