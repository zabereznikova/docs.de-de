---
title: Behandeln von Überlauf-JSON mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Überlauf-JSON beim Serialisieren in und Deserialisieren aus JSON behandeln können.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2c40d42b26bc5bd05f592cc51c6b5b9b4c6bbd9e
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439797"
---
# <a name="how-to-handle-overflow-json-with-no-locsystemtextjson"></a>Behandeln von Überlauf-JSON mit System.Text.Json

In diesem Artikel erfahren Sie, wie Überlauf-JSON mit dem `System.Text.Json`-Namespace behandelt wird.

## <a name="handle-overflow-json"></a>Verarbeiten von Überlauf-JSON

Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, die nicht von Eigenschaften des Zieltyps dargestellt werden. Angenommen, Ihr Zieltyp ist folgender:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

Und der zu deserialisierende JSON-Code ist wie folgt:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das Attribut [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithExtensionData":::

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

| Eigenschaft | Wert | Notizen |
|--|--|--|
| `Date` | `"8/1/2019 12:00:00 AM -07:00"` |  |
| `TemperatureCelsius` | `0` | Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird. |
| `Summary` | `"Hot"` |  |
| `ExtensionData` | `temperatureCelsius: 25` | Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch. |
| `DatesAvailable` | `[ "8/1/2019 12:00:00 AM -07:00", "8/2/2019 12:00:00 AM -07:00" ]` | Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert. |
| `SummaryWords` | `[ "Cool", "Windy", "Humid" ]` | Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert. |

Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu genau solchen JSON-Eigenschaften, wie sie im eingehenden JSON-Code waren:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code vorkommt. Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert würden.

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
