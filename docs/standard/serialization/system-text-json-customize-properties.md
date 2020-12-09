---
title: Anpassen von Eigenschaftsnamen und -werten mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Eigenschaftsnamen und -werte bei der Serialisierung mit System.Text.Json anpassen.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c754d41071e886bc1efcc3a30e249bf9e554ab5b
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599589"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a>Anpassen von Eigenschaftsnamen und -werten mit System.Text.Json

Standardmäßig bleiben Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung. Enumerationswerte werden als Zahlen dargestellt. In diesem Artikel lernen Sie Folgendes:

> [!NOTE]
> Der [Webstandard](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) ist die Camel-Case-Schreibweise.

* [Anpassen einzelner Eigenschaftsnamen](#customize-individual-property-names)
* [Konvertieren aller Eigenschaftsnamen in Camel-Case-Schreibweise](#use-camel-case-for-all-json-property-names)
* [Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften](#use-a-custom-json-property-naming-policy)
* [Konvertieren von Wörterbuchschlüsseln in Camel-Case-Schreibweise](#camel-case-dictionary-keys)
* [Konvertieren von Enumerationen in Zeichenfolgen und Camel-Case-Schreibweise](#enums-as-strings)

Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).

## <a name="customize-individual-property-names"></a>Anpassen einzelner Eigenschaftsnamen

Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das Attribut [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).

Hier finden Sie einen zu serialisierenden Beispieltyp und die daraus resultierende JSON-Ausgabe:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Der über dieses Attribut festgelegte Eigenschaftsname:

* Dies gilt in beide Richtungen, für Serialisierung und Deserialisierung.
* Es hat Vorrang vor Benennungsrichtlinien für Eigenschaften.

## <a name="use-camel-case-for-all-json-property-names"></a>Verwenden der Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen

Um die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen zu verwenden, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Die Camel-Case-Benennungsrichtlinie für Eigenschaften:

* Gilt für Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Camel-Case-Schreibweise.

## <a name="use-a-custom-json-property-naming-policy"></a>Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften

Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und setzen Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode außer Kraft, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihre Benennungsrichtlinienklasse fest:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Die Benennungsrichtlinie für JSON-Eigenschaften:

* Gilt für Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.

## <a name="camel-case-dictionary-keys"></a>Wörterbuchschlüssel in Camel-Case-Schreibweise

Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die Schlüssel vom Typ `string` in Camel-Case-Schreibweise konvertiert werden. Legen Sie hierzu <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

Das Serialisieren eines Objekts mit einem Wörterbuch namens `TemperatureRanges`, das die Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` enthält, würde zu einer JSON-Ausgabe wie im folgenden Beispiel führen:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung. Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei auch dann, wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.

## <a name="enums-as-strings"></a>Enumerationen als Zeichenfolgen

Standardmäßig werden Enumerationen als Zahlen serialisiert. Um Enumerationen als Zeichenfolgen zu serialisieren, verwenden Sie <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Angenommen, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

Wenn die Zusammenfassung `Hot` ist, hat das serialisierte JSON standardmäßig den numerischen Wert 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

Das resultierende JSON sieht wie im folgenden Beispiel aus:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Zeichenfolgennamen von Enumerationen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
