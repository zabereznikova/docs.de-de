---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (.net)
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 0f8b89ec7d7b1677de085631958b888e154aa4fa
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116713"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a>Schreiben von benutzerdefinierten Konvertern für JSON-Serialisierung (Marshalling) in .net

In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für die JSON-Serialisierungsklassen erstellen, die im <xref:System.Text.Json>-Namespace bereitgestellt werden. Eine Einführung in `System.Text.Json`finden Sie unter Gewusst [wie: Serialisieren und Deserialisieren von JSON in .net](system-text-json-how-to.md).

Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert. Der `System.Text.Json`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-primitiven zugeordnet werden. Sie können benutzerdefinierte Konverter schreiben:

* , Um das Standardverhalten eines integrierten Konverters zu überschreiben. Beispielsweise kann es vorkommen, dass `DateTime` Werte durch das Format mm/dd/yyyy anstelle des Standard Formats ISO 8601-1:2019 dargestellt werden.
* Zur Unterstützung eines benutzerdefinierten Werttyps. Beispielsweise eine `PhoneNumber` Struktur.

Sie können auch benutzerdefinierte Konverter schreiben, um `System.Text.Json` mit Funktionen anzupassen oder zu erweitern, die nicht in der aktuellen Version enthalten sind. Die folgenden Szenarien werden später in diesem Artikel behandelt:

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
* Überschreiben Sie die `Read`-Methode, um den eingehenden JSON-Code zu deserialisieren und in Type `T`zu konvertieren. Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.
* Override the `Write` method to serialize the incoming object of type `T`. Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.
* Override the `CanConvert` method only if necessary. The default implementation returns `true` when the type to convert is of type `T`. Therefore, converters that support only type `T` don't need to override this method. For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.

You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.

## <a name="steps-to-follow-the-factory-pattern"></a>Steps to follow the factory pattern

The following steps explain how to create a converter by following the factory pattern:

* Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverterFactory> abgeleitet ist.
* Override the `CanConvert` method to return true when the type to convert is one that the converter can handle. For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`. 
* Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.
* Create the converter class that the `CreateConverter` method instantiates. 

The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types. A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes. Code must be written to handle each closed-generic type that the converter can handle.

The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes. 

## <a name="error-handling"></a>Fehlerbehandlung

If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message. This exception type automatically creates a message that includes the path to the part of the JSON that caused the error. For example, the statement `throw new JsonException();` produces an error message like the following example:

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.

## <a name="register-a-custom-converter"></a>Register a custom converter

*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it. Choose one of the following approaches:

* Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.
* Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.
* Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.

## <a name="registration-sample---converters-collection"></a>Registration sample - Converters collection 

Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:

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

Beim Deserialisieren in eine Eigenschaft vom Typ `object`wird ein `JsonElement` Objekt erstellt. Der Grund dafür ist, dass das Deserialisierungsprogramm nicht weiß, welcher CLR-Typ erstellt werden soll, und es wird nicht versucht, zu erraten. Wenn z. b. eine JSON-Eigenschaft "true" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass der Wert eine `Boolean`ist, und wenn ein Element "01/01/2019" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass es sich um eine `DateTime`handelt.

Der Typrückschluss kann ungenau sein. Wenn das Deserialisierungsprogramm eine JSON-Zahl analysiert, die keinen Dezimaltrennzeichen als `long`aufweist, kann dies zu Problemen außerhalb des gültigen Bereichs führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger`serialisiert wurde. Das Auswerten einer Zahl, die einen Dezimaltrennzeichen als `double` aufweist, kann die Genauigkeit verlieren, wenn die Zahl ursprünglich als `decimal`serialisiert wurde.

Für Szenarios, die einen Typrückschluss erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `object` Eigenschaften an. Der Code konvertiert Folgendes:

* `true` und `false` auf `Boolean`
* Zahlen ohne Dezimal `long`
* Zahlen mit einem Dezimaltrennzeichen, das `double`
* Datumsangaben zum `DateTime`
* Zu `string` Zeichenfolgen
* Alles andere `JsonElement`

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

Hier ist ein Beispiel für einen Typ mit `object` Eigenschaften:

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

Der [Ordner Komponententests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung zum `object` von Eigenschaften verarbeiten.

### <a name="support-dictionary-with-non-string-key"></a>Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen

Die integrierte Unterstützung für Wörterbuch Sammlungen ist für `Dictionary<string, TValue>`. Das heißt, der Schlüssel muss eine Zeichenfolge sein. Um ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.

Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

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

Der [Ordner "Unittests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher für nicht-Zeichen folgen Schlüssel verarbeiten.

### <a name="support-polymorphic-deserialization"></a>Unterstützung der polymorphen Deserialisierung

Integrierte Features bieten eine begrenzte Anzahl von [polymorphen Serialisierungen](system-text-json-how-to.md#serialize-properties-of-derived-classes) , aber keine Unterstützung für die Deserialisierung. Die Deserialisierung erfordert einen benutzerdefinierten Konverter.

Angenommen, Sie verfügen beispielsweise über eine `Person` abstrakte Basisklasse mit `Employee` und `Customer` abgeleiteten Klassen. Die polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können und dass `Customer` und `Employee` Objekte in der JSON-Datei zur Laufzeit ordnungsgemäß deserialisiert werden. Während der Deserialisierung müssen Sie nach Hinweisen suchen, mit denen der erforderliche Typ im JSON-Code identifiziert wird. Die möglichen verfügbaren Hinweise variieren in jedem Szenario. Beispielsweise kann eine diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist. Die aktuelle Version von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.

Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter. Der Konverter verwendet eine diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen. Der typdiskriminator ist nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

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

Mit dem Konvertercode im vorherigen Beispiel wird jede Eigenschaft manuell gelesen und geschrieben. Eine Alternative besteht darin, `Deserialize` oder `Serialize` aufzurufen, um einige der Aufgaben durchzuführen. Ein Beispiel finden Sie in [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/59744873/12509023).

## <a name="other-custom-converter-samples"></a>Weitere benutzerdefinierte konverterbeispiele

Der Artikel [Migrieren von "newtonsoft. JSON" zu "System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md) " enthält zusätzliche Beispiele für benutzerdefinierte Konverter.

Der [Ordner Komponententests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) im `System.Text.Json.Serialization` Quellcode enthält andere benutzerdefinierte konverterbeispiele, wie z. b.:

* [Int32 Converter, der bei der Deserialisierung NULL in 0 konvertiert.](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)
* [Int32 Converter, der beim Deserialisieren sowohl Zeichen folgen-als auch Zahlenwerte zulässt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)
* [Enumerationskonverter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)
* [Auflisten\<t > Konverters, der externe Daten annimmt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)
* [Long [] Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen funktioniert.](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs) 

Wenn Sie einen Konverter erstellen müssen, der das Verhalten eines vorhandenen integrierten Konverters ändert, können Sie [den Quellcode des vorhandenen Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) als Ausgangspunkt für die Anpassung erhalten.

## <a name="additional-resources"></a>Weitere Ressourcen

* [Quellcode für integrierte Konverter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)
* [DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON](../datetime/system-text-json-support.md)
* [Übersicht über System. Text. JSON](system-text-json-overview.md)
* [Verwenden von "System. Text. JSON"](system-text-json-how-to.md)
* [Vorgehensweise beim Migrieren von "newtonsoft. JSON"](system-text-json-migrate-from-newtonsoft-how-to.md)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [System. Text. JSON. Serialization-API-Referenz](xref:System.Text.Json.Serialization)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
