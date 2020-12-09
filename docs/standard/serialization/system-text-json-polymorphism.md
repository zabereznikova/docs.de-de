---
title: Serialisieren von Eigenschaften abgeleiteter Klassen mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET polymorphe Objekte beim Serialisieren in und Deserialisieren aus JSON serialisieren können.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 4b99a402ea4f4c664d3bfd75627ffaf94948d493
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439790"
---
# <a name="how-to-serialize-properties-of-derived-classes-with-no-locsystemtextjson"></a>Serialisieren von Eigenschaften abgeleiteter Klassen mit System.Text.Json

In diesem Artikel erfahren Sie, wie Sie Eigenschaften abgeleiteter Klassen mit dem `System.Text.Json`-Namespace serialisieren können.

## <a name="serialize-properties-of-derived-classes"></a>Serialisieren von Eigenschaften abgeleiteter Klassen

Das Serialisieren einer polymorphen Typhierarchie wird _nicht_ unterstützt. Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert wird, werden nur die für die Schnittstelle oder abstrakte Klasse definierten Eigenschaften serialisiert, auch wenn der Laufzeittyp über zusätzliche Eigenschaften verfügt. Die Ausnahmen bei diesem Verhalten werden in diesem Abschnitt erläutert.

Nehmen Sie beispielsweise an, Sie besitzen eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFDerived":::

Ferner sei angenommen, dass das Typargument der `Serialize`-Methode zur Kompilierzeit `WeatherForecast` ist:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeDefault":::

In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch dann nicht, wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist. Nur die Basisklasseneigenschaften werden serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Dieses Verhalten soll die versehentliche Verfügbarmachung von Daten in einem abgeleiteten, zur Laufzeit erstellten Typ verhindern.

Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:

* Rufen Sie eine Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A> auf, bei der Sie den Typ zur Laufzeit angeben können:

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeGetType":::

* Deklarieren Sie das zu serialisierende Objekt als `object`.

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeObject":::

Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in die JSON-Ausgabe aufgenommen wird:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Diese Ansätze bieten polymorphe Serialisierung nur für das Stammobjekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stammobjekts.

Sie können polymorphe Serialisierung für Objekte auf niedrigerer Ebene erzielen, wenn Sie diese als `object`-Typ definieren. Angenommen, Ihre `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als `WeatherForecast`-Typ oder als `object`-Typ definiert werden kann:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPrevious":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPreviousAsObject":::

Wenn die Eigenschaft `PreviousForecast` eine Instanz von `WeatherForecastDerived` enthält:

* Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.
* Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.

Um `WeatherForecastWithPreviousAsObject` zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stammobjekt nicht das Objekt ist, das von einem abgeleiteten Typ sein darf. Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType` aufgerufen:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeSecondLevel":::

Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject` korrekt:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

Derselbe Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen. Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungsinstanzen enthalten:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/IForecast.cs":::

Wenn Sie eine Instanz von `Forecasts` serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object` definiert ist:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeInterface":::

Im folgenden Beispiel wird der JSON-Code gezeigt, der aus dem vorangehenden Code resultiert:

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

Weitere Informationen zur polymorphen **Serialisierung** sowie Informationen zur **Deserialisierung** finden Sie unter [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
