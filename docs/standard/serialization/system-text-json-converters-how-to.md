---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (.net)
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 33d1cd7764e71d9e2fa382c9f3c5feb77e8defb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283348"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a>Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung in .net

In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für die JSON-Serialisierungsklassen erstellen, die im <xref:System.Text.Json>-Namespace bereitgestellt werden. Eine Einführung in `System.Text.Json`finden Sie unter Gewusst [wie: Serialisieren und Deserialisieren von JSON in .net](system-text-json-how-to.md).

Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert. Der `System.Text.Json`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-primitiven zugeordnet werden. Sie können benutzerdefinierte Konverter schreiben:

* , Um das Standardverhalten eines integrierten Konverters zu überschreiben. Beispielsweise kann es vorkommen, dass `DateTime` Werte durch das Format mm/dd/yyyy anstelle des Standard Formats ISO 8601-1:2019 dargestellt werden.
* Zur Unterstützung eines benutzerdefinierten Werttyps. Beispielsweise eine `PhoneNumber` Struktur.

Sie können auch benutzerdefinierte Konverter schreiben, um `System.Text.Json` mit Funktionen zu erweitern, die nicht in der aktuellen Version enthalten sind. Die folgenden Szenarien werden später in diesem Artikel behandelt:

* [Deserialisieren von abzurufbaren Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).
* [Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen](#support-dictionary-with-non-string-key).
* [Unterstützung der polymorphen Deserialisierung](#support-polymorphic-deserialization).

## <a name="custom-converter-patterns"></a>Benutzerdefinierte konvertermuster

Es gibt zwei Muster zum Erstellen eines benutzerdefinierten Konverters: das grundlegende Muster und das Factorymuster. Das Factorymuster ist für Konverter vorgesehen, die Typen `Enum` oder offene Generika verarbeiten. Das grundlegende Muster basiert auf nicht generischen und geschlossenen generischen Typen.  Konverter für die folgenden Typen erfordern z. b. das Factorymuster:

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

Einige Beispiele für Typen, die vom grundlegenden Muster behandelt werden können, sind:

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

Das grundlegende Muster erstellt eine Klasse, die einen Typ verarbeiten kann. Das Factorymuster erstellt eine Klasse, die zur Laufzeit bestimmt, welcher bestimmter Typ erforderlich ist, und erstellt dynamisch den entsprechenden Konverter.

## <a name="sample-basic-converter"></a>Sample-Grund Konverter

Das folgende Beispiel ist ein Konverter, der die Standardserialisierung für einen vorhandenen Datentyp überschreibt. Der Konverter verwendet das Format "mm/dd/yyyy" für `DateTimeOffset` Eigenschaften.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a>Sample Factory-Muster Konverter

Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert. Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und das zweite geöffnet ist. Die `CanConvert`-Methode gibt `true` nur für einen `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist. Der innere Konverter Ruft einen vorhandenen Konverter ab, um den Typ zu behandeln, der zur Laufzeit für `TValue`bereitgestellt wird. 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Der vorangehende Code ist identisch mit dem, was im [Unterstützungs Wörterbuch mit einem nicht-Zeichen folgen Schlüssel](#support-dictionary-with-non-string-key) weiter unten in diesem Artikel gezeigt wird.

## <a name="steps-to-follow-the-basic-pattern"></a>Schritte zum grundlegenden Muster

In den folgenden Schritten wird erläutert, wie Sie einen Konverter erstellen, indem Sie das grundlegende Muster befolgen:

* Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverter%601> abgeleitet ist, wobei `T` der Typ ist, der serialisiert und deserialisiert werden soll.
* Überschreiben Sie die `Read`-Methode, um den eingehenden JSON-Code zu deserialisieren und in Type `T`zu konvertieren. Verwenden Sie die <xref:System.Text.Json.Utf8JsonReader>, die an die-Methode weitergegeben wird, um die JSON zu lesen.
* Überschreiben Sie die `Write`-Methode, um das eingehende Objekt vom Typ `T`zu serialisieren. Verwenden Sie die <xref:System.Text.Json.Utf8JsonWriter>, die an die-Methode zum Schreiben der JSON-Datei übermittelt wird.
* Überschreiben Sie die `CanConvert`-Methode nur bei Bedarf. Die Standard Implementierung gibt `true` zurück, wenn der zu konvertierende Typ `T`ist. Daher müssen Konverter, die nur den-Typ unterstützen `T` diese Methode nicht überschreiben. Ein Beispiel für einen Konverter, der diese Methode überschreiben muss, finden Sie im Abschnitt [polymorphe Deserialisierung](#support-polymorphic-deserialization) weiter unten in diesem Artikel.

Sie können den [integrierten Konverter-Quellcode](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) als Referenzimplementierungen zum Schreiben von benutzerdefinierten Konvertern bezeichnen.

## <a name="steps-to-follow-the-factory-pattern"></a>Schritte zum Befolgen des Factorymusters

In den folgenden Schritten wird erläutert, wie Sie einen Konverter erstellen, indem Sie das Factorymuster befolgen:

* Erstellen Sie eine von der <xref:System.Text.Json.Serialization.JsonConverterFactory>-Klasse abgeleitete Klasse.
* Überschreiben Sie die `CanConvert`-Methode, um true zurückzugeben, wenn der zu konvertierende Typ eine ist, die der Konverter verarbeiten kann. Wenn der Konverter z. b. für `List<T>` ist, kann er nur `List<int>`, `List<string>`und `List<DateTime>`verarbeiten. 
* Überschreiben Sie die `CreateConverter`-Methode, um eine Instanz einer Konverterklasse zurückzugeben, die den zu konvertierenden Typ zur Laufzeit behandelt.
* Erstellen Sie die Konverterklasse, die von der `CreateConverter`-Methode instanziiert wird. 

Das Factorymuster ist für geöffnete Generika erforderlich, da der Code zum Konvertieren eines Objekts in eine und aus einer Zeichenfolge nicht für alle Typen identisch ist. Ein Konverter für einen offenen generischen Typ (z. b.`List<T>`) muss im Hintergrund einen Konverter für einen geschlossenen generischen Typ erstellen (z. b.`List<DateTime>`). Code muss geschrieben werden, um jeden geschlossenen generischen Typ zu verarbeiten, den der Konverter verarbeiten kann.

Der `Enum` Typ ähnelt einem offenen generischen Typ: ein Konverter für `Enum` muss im Hintergrund einen Konverter für eine bestimmte `Enum` erstellen (z. b.`WeekdaysEnum`). 

## <a name="error-handling"></a>Fehlerbehandlung

Wenn Sie im Fehler Behandlungs Code eine Ausnahme auslösen müssen, sollten Sie ein <xref:System.Text.Json.JsonException> ohne eine Meldung auslösen. Dieser Ausnahmetyp erstellt automatisch eine Meldung, die den Pfad zu dem Teil der JSON enthält, der den Fehler verursacht hat. Beispielsweise erzeugt die-Anweisung `throw new JsonException();` eine Fehlermeldung wie im folgenden Beispiel:

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Wenn Sie eine Meldung angeben (z. b. `throw new JsonException("Error occurred")`, stellt die Ausnahme weiterhin den Pfad in der <xref:System.Text.Json.JsonException.Path>-Eigenschaft bereit.

## <a name="register-a-custom-converter"></a>Registrieren eines benutzerdefinierten Konverters

*Registrieren* Sie einen benutzerdefinierten Konverter, damit der `Serialize` und `Deserialize` Methoden ihn verwenden. Wählen Sie einen der folgenden Ansätze:

* Fügen Sie der <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> Auflistung eine Instanz der Konverterklasse hinzu.
* Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf die Eigenschaften an, die den benutzerdefinierten Konverter benötigen.
* Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf eine Klasse oder eine Struktur an, die einen benutzerdefinierten Werttyp darstellt.

## <a name="registration-sample---converters-collection"></a>Registrierungs Beispiel: Konverter-Auflistung 

Im folgenden finden Sie ein Beispiel, mit dem die <xref:System.ComponentModel.DateTimeOffsetConverter> der Standardeinstellung für Eigenschaften vom Typ <xref:System.DateTimeOffset>wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

Angenommen, Sie serialisieren eine Instanz des folgenden Typs:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Hier ist ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Der folgende Code verwendet den gleichen Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset` Konverters:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a>Registrierungs Beispiel-[jsonconverter] für eine Eigenschaft

Der folgende Code wählt einen benutzerdefinierten Konverter für die `Date`-Eigenschaft aus:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

Für den Code zum Serialisieren `WeatherForecastWithConverterAttribute` ist die Verwendung `JsonSerializeOptions.Converters`nicht erforderlich:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

Der Code zum Deserialisieren erfordert auch nicht die Verwendung von `Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a>Registrierungs Beispiel-[jsonconverter] für einen Typ

Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

Dies ist der benutzerdefinierte Konverter für die vorangehende Struktur:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

Das `[JsonConvert]`-Attribut in der Struktur registriert den benutzerdefinierten Konverter als Standardwert für Eigenschaften vom Typ `Temperature`. Der Konverter wird bei der Serialisierung oder Deserialisierung automatisch in der `TemperatureCelsius`-Eigenschaft des folgenden Typs verwendet:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a>Priorität der konverterregistrierung

Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element in der folgenden Reihenfolge ein Konverter ausgewählt, der von der höchsten Priorität bis zum niedrigsten aufgelistet wird:

* `[JsonConverter]` auf eine Eigenschaft angewendet.
* Ein Konverter, der der `Converters` Auflistung hinzugefügt wird.
* `[JsonConverter]` auf einen benutzerdefinierten Werttyp oder poco angewendet.

Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters` Auflistung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` "true" zurückgibt.

Ein integrierter Konverter wird nur ausgewählt, wenn kein entsprechender benutzerdefinierter Konverter registriert ist.

## <a name="converter-samples-for-common-scenarios"></a>Konverterbeispiele für gängige Szenarien

In den folgenden Abschnitten werden konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.

* [Deserialisieren von abzurufbaren Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties)
* [Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen](#support-dictionary-with-non-string-key)
* [Unterstützung der polymorphen Deserialisierung](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserialisieren von abzurufbaren Typen in Objekteigenschaften

Beim Deserialisieren in eine Eigenschaft vom Typ `Object`wird ein `JsonElement` Objekt erstellt. Der Grund dafür ist, dass das Deserialisierungsprogramm nicht weiß, welcher CLR-Typ erstellt werden soll, und es wird nicht versucht, zu erraten. Wenn z. b. eine JSON-Eigenschaft "true" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass der Wert eine `Boolean`ist, und wenn ein Element "01/01/2019" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass es sich um eine `DateTime`handelt.

Der Typrückschluss kann ungenau sein. Wenn das Deserialisierungsprogramm eine JSON-Zahl analysiert, die keinen Dezimaltrennzeichen als `long`aufweist, kann dies zu Problemen außerhalb des gültigen Bereichs führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger`serialisiert wurde. Das Auswerten einer Zahl, die einen Dezimaltrennzeichen als `double` aufweist, kann die Genauigkeit verlieren, wenn die Zahl ursprünglich als `decimal`serialisiert wurde.

Für Szenarios, die einen Typrückschluss erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `Object` Eigenschaften an. Der Code konvertiert Folgendes:

* `true` und `false` auf `Boolean`
* Zahlen zum `long` oder `double`
* Datumsangaben zum `DateTime`
* Zu `string` Zeichenfolgen
* Alles andere `JsonElement`

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

Hier ist ein Beispiel für einen Typ mit `Object` Eigenschaften:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

Das folgende JSON-Beispiel für die Deserialisierung enthält Werte, die als `DateTime`, `long`und `string`deserialisiert werden:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.

Der [Ordner "Unittests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung zu Objekteigenschaften verarbeiten.

### <a name="support-dictionary-with-non-string-key"></a>Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen

Die integrierte Unterstützung für Wörterbuch Sammlungen ist für `Dictionary<string, TValue>`. Das heißt, der Schlüssel muss eine Zeichenfolge sein. Um ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.

Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die Folgendes `Enum`verwendet:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

Die JSON-Ausgabe der Serialisierung sieht wie im folgenden Beispiel aus:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

Der [Ordner "Unittests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher für nicht-Zeichen folgen Schlüssel verarbeiten.

### <a name="support-polymorphic-deserialization"></a>Unterstützung der polymorphen Deserialisierung

Die [polymorphe Serialisierung](system-text-json-how-to.md#serialize-properties-of-derived-classes) erfordert keinen benutzerdefinierten Konverter, aber die Deserialisierung erfordert einen benutzerdefinierten Konverter.

Angenommen, Sie verfügen beispielsweise über eine `Person` abstrakte Basisklasse mit `Employee` und `Customer` abgeleiteten Klassen. Die polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können und dass `Customer` und `Employee` Objekte in der JSON-Datei zur Laufzeit ordnungsgemäß deserialisiert werden. Während der Deserialisierung müssen Sie nach Hinweisen suchen, mit denen der erforderliche Typ im JSON-Code identifiziert wird. Die möglichen verfügbaren Hinweise variieren in jedem Szenario. Beispielsweise kann eine diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist. Die aktuelle Version von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.

Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter. Der Konverter verwendet eine diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen. Der typdiskriminator ist nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

Der Konverter kann JSON deserialisieren, das mit dem gleichen Konverter zum Serialisieren erstellt wurde, z. b.:

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

## <a name="other-custom-converter-samples"></a>Weitere benutzerdefinierte konverterbeispiele

Der [Ordner Komponententests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) im `System.Text.Json.Serialization` Quellcode enthält andere benutzerdefinierte konverterbeispiele, wie z. b.:

* `Int32` Konverter, der bei der Deserialisierung NULL in 0 konvertiert.
* `Int32` Konverter, der beim Deserialisieren sowohl Zeichen folgen-als auch Zahlenwerte zulässt.
* `Enum` Konverter
* `List<T>` Konverter, der externe Daten annimmt
* `Long[]` Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen funktioniert. 

## <a name="additional-resources"></a>Weitere Ressourcen

* [Übersicht über System. Text. JSON](system-text-json-overview.md)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [Verwenden von "System. Text. JSON"](system-text-json-how-to.md)
* [Quellcode für integrierte Konverter](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* GitHub-Probleme im Zusammenhang mit benutzerdefinierten Konvertern für `System.Text.Json`
  * [36639 Einführung in benutzerdefinierte Konverter](https://github.com/dotnet/corefx/issues/36639)
  * [38713 Informationen zur Deserialisierung in ein Objekt](https://github.com/dotnet/corefx/issues/38713)
  * [40120 Informationen zu nicht-Zeichen folgen Schlüssel Wörterbüchern](https://github.com/dotnet/corefx/issues/40120)
  * [37787 Informationen zur polymorphen Deserialisierung](https://github.com/dotnet/corefx/issues/37787)
