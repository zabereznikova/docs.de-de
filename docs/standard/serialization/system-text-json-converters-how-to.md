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
ms.openlocfilehash: 361818a0bda8863f8878b86e5fb377dc0faf5246
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73741903"
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

```csharp
private class ExampleDateTimeOffsetConverter : JsonConverter<DateTimeOffset>
{
    public override DateTimeOffset Read(
        ref Utf8JsonReader reader, 
        Type typeToConvert, 
        JsonSerializerOptions options)
    {
        return DateTimeOffset.ParseExact(reader.GetString(), 
            "MM/dd/yyyy", CultureInfo.InvariantCulture);
    }

    public override void Write(
        Utf8JsonWriter writer, 
        DateTimeOffset value, 
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString(
            "MM/dd/yyyy", CultureInfo.InvariantCulture));
    }
}
```

## <a name="sample-factory-pattern-converter"></a>Sample Factory-Muster Konverter

Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert. Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und das zweite geöffnet ist. Die `CanConvert`-Methode gibt `true` nur für einen `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist. Der innere Konverter Ruft einen vorhandenen Konverter ab, um den Typ zu behandeln, der zur Laufzeit für `TValue`bereitgestellt wird. 

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

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

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Wenn Sie eine Meldung angeben (z. b. `throw new JsonException("Error occurred)`, stellt die Ausnahme weiterhin den Pfad in der <xref:System.Text.Json.JsonException.Path>-Eigenschaft bereit.

## <a name="register-a-custom-converter"></a>Registrieren eines benutzerdefinierten Konverters

*Registrieren* Sie einen benutzerdefinierten Konverter, damit der `Serialize` und `Deserialize` Methoden ihn verwenden. Wählen Sie einen der folgenden Ansätze:

* Fügen Sie der <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> Auflistung eine Instanz der Konverterklasse hinzu.
* Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf die Eigenschaften an, die den benutzerdefinierten Konverter benötigen.
* Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf eine Klasse oder eine Struktur an, die einen benutzerdefinierten Werttyp darstellt.

## <a name="registration-sample---converters-collection"></a>Registrierungs Beispiel: Konverter-Auflistung 

Im folgenden finden Sie ein Beispiel, mit dem die `ExampleDateTimeOffsetConverter` der Standardeinstellung für Eigenschaften vom Typ `DateTimeOffset`wird:

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

Angenommen, Sie serialisieren den folgenden Typ:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Hier ist ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Der folgende Code verwendet den gleichen Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset` Konverters:

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a>Registrierungs Beispiel-[jsonconverter] für eine Eigenschaft

Der folgende Code wählt einen benutzerdefinierten Konverter für die `Date`-Eigenschaft aus:

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Für den Code zum Serialisieren und Deserialisieren `WeatherForecastWithConverter` ist die Verwendung `JsonSerializeOptions.Converters`nicht erforderlich:

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a>Registrierungs Beispiel-[jsonconverter] für einen Typ

Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:

```csharp
[JsonConverter(typeof(TemperatureConverter))]
public struct Temperature
{
    public Temperature(int degrees, bool celsius)
    {
        _degrees = degrees;
        _isCelsius = celsius;
    }
    private bool _isCelsius;
    private int _degrees;
    public int Degrees => _degrees;
    public bool IsCelsius => _isCelsius; 
    public bool IsFahrenheit => !_isCelsius;
    public override string ToString() =>
        $"{_degrees.ToString()}{(_isCelsius ? "C" : "F")}";
    public static Temperature Parse(string input)
    {
        int degrees = int.Parse(input.Substring(0, input.Length - 1));
        bool celsius = (input.Substring(input.Length - 1) == "C");
        return new Temperature(degrees, celsius);
    }
}
```

Dies ist der benutzerdefinierte Konverter für die vorangehende Struktur:

```csharp
public class TemperatureConverter : JsonConverter<Temperature>
{
    public override Temperature Read(
        ref Utf8JsonReader reader,
        Type typeToConvert,
        JsonSerializerOptions options)
    {
        Debug.Assert(typeToConvert == typeof(Temperature));
        return Temperature.Parse(reader.GetString());
    }

    public override void Write(
        Utf8JsonWriter writer,
        Temperature value,
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString());
    }
}
```

Das `[JsonConvert]`-Attribut in der Struktur registriert den benutzerdefinierten Konverter als Standardwert für Eigenschaften vom Typ `Temperature`. Der Konverter wird bei der Serialisierung oder Deserialisierung automatisch in der `TemperatureC`-Eigenschaft des folgenden Typs verwendet:

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a>Priorität der konverterregistrierung

Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element in der folgenden Reihenfolge ein Konverter ausgewählt, der von der höchsten Priorität bis zum niedrigsten aufgelistet wird:

* `[JsonConverter]` auf eine Eigenschaft angewendet.
* Ein Konverter, der der `Converters` Auflistung hinzugefügt wird.
* `[JsonConverter]` auf einen benutzerdefinierten Werttyp oder poco angewendet.

Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters` Auflistung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` "true" zurückgibt.

Ein integrierter Konverter wird nur ausgewählt, wenn kein entsprechender benutzerdefinierter Konverter registriert ist.

## <a name="converter-samples-for-common-scenarios"></a>Konverterbeispiele für gängige Szenarien

In den folgenden Abschnitten werden konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserialisieren von abzurufbaren Typen in Objekteigenschaften

Beim Deserialisieren in eine Eigenschaft vom Typ `Object`wird ein `JsonElement` Objekt erstellt. Der Grund dafür ist, dass das Deserialisierungsprogramm nicht weiß, welcher CLR-Typ erstellt werden soll, und es wird nicht versucht, zu erraten. Wenn z. b. eine JSON-Eigenschaft "true" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass der Wert eine `Boolean`ist, und wenn ein Element "01/01/2019" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass es sich um eine `DateTime`handelt.

Der Typrückschluss kann ungenau sein. Wenn das Deserialisierungsprogramm eine JSON-Zahl analysiert, die keinen Dezimaltrennzeichen als `long`aufweist, kann dies zu Problemen außerhalb des gültigen Bereichs führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger`serialisiert wurde. Das Auswerten einer Zahl, die einen Dezimaltrennzeichen als `double` aufweist, kann die Genauigkeit verlieren, wenn die Zahl ursprünglich als `decimal`serialisiert wurde.

Für Szenarios, die einen Typrückschluss erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `Object` Eigenschaften an. Der Code konvertiert Folgendes:

* `true` und `false` auf `Boolean`
* Zahlen zum `long` oder `double`
* Datumsangaben zum `DateTime`
* Zu `string` Zeichenfolgen
* Alles andere `JsonElement`

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ObjectToInferredTypesConverter
        : JsonConverter<object>
    {
        public override object Read(
            ref Utf8JsonReader reader,
            Type typeToConvert,
            JsonSerializerOptions options)
        {
            if (reader.TokenType == JsonTokenType.True)
            {
                return true;
            }

            if (reader.TokenType == JsonTokenType.False)
            {
                return false;
            }

            if (reader.TokenType == JsonTokenType.Number)
            {
                if (reader.TryGetInt64(out long l))
                {
                    return l;
                }

                return reader.GetDouble();
            }

            if (reader.TokenType == JsonTokenType.String)
            {
                if (reader.TryGetDateTime(out DateTime datetime))
                {
                    return datetime;
                }

                return reader.GetString();
            }

            // Use JsonElement as fallback.
            // Newtonsoft uses JArray or JObject.
            using (JsonDocument document = JsonDocument.ParseValue(ref reader))
            {
                return document.RootElement.Clone();
            }
        }

        public override void Write(
            Utf8JsonWriter writer,
            object value,
            JsonSerializerOptions options)
        {
            throw new InvalidOperationException("Should not get here.");
        }
    }
}
```

Der folgende Code registriert den Konverter:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

Hier ist ein Beispiel für einen Typ mit einer Objekt Eigenschaft:

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

Das folgende JSON-Beispiel für die Deserialisierung enthält Werte, die als `DateTime`, `long`und `string`deserialisiert werden:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.

Der [Ordner "Unittests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung zu Objekteigenschaften verarbeiten.

### <a name="support-dictionary-with-non-string-key"></a>Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen

Die integrierte Unterstützung für Wörterbuch Sammlungen ist für `Dictionary<string, TValue>`. Das heißt, der Schlüssel muss eine Zeichenfolge sein. Um ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.

Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert:

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

Der folgende Code registriert den Konverter:

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die Folgendes `Enum`verwendet:

```csharp
public class WeatherForecastWithEnumDictionary
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public Dictionary<SummaryWordsEnum, int> TemperatureRanges { get; set; }
}

public enum SummaryWordsEnum
{
    Cold, Hot
}
```

Die JSON-Ausgabe der Serialisierung sieht wie im folgenden Beispiel aus:

```json
{

  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
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

```csharp
public class Person
{
    public string Name { get; set; }
}

public class Customer : Person
{
    public decimal CreditLimit { get; set; }
}

public class Employee : Person
{
    public string OfficeNumber { get; set; }
}
```

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class PersonConverterWithTypeDiscriminator : JsonConverter<Person>
    {
        enum TypeDiscriminator
        {
            Customer = 1,
            Employee = 2
        }

        public override bool CanConvert(Type typeToConvert)
        {
            return typeof(Person).IsAssignableFrom(typeToConvert);
        }

        public override Person Read(ref Utf8JsonReader reader, Type typeToConvert, JsonSerializerOptions options)
        {
            if (reader.TokenType != JsonTokenType.StartObject)
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.PropertyName)
            {
                throw new JsonException();
            }

            string propertyName = reader.GetString();
            if (propertyName != "TypeDiscriminator")
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.Number)
            {
                throw new JsonException();
            }

            Person value;
            TypeDiscriminator typeDiscriminator = (TypeDiscriminator)reader.GetInt32();
            switch (typeDiscriminator)
            {
                case TypeDiscriminator.Customer:
                    value = new Customer();
                    break;

                case TypeDiscriminator.Employee:
                    value = new Employee();
                    break;

                default:
                    throw new JsonException();
            }

            while (reader.Read())
            {
                if (reader.TokenType == JsonTokenType.EndObject)
                {
                    return value;
                }

                if (reader.TokenType == JsonTokenType.PropertyName)
                {
                    propertyName = reader.GetString();
                    reader.Read();
                    switch (propertyName)
                    {
                        case "CreditLimit":
                            decimal creditLimit = reader.GetDecimal();
                            ((Customer)value).CreditLimit = creditLimit;
                            break;
                        case "OfficeNumber":
                            string officeNumber = reader.GetString();
                            ((Employee)value).OfficeNumber = officeNumber;
                            break;
                        case "Name":
                            string name = reader.GetString();
                            value.Name = name;
                            break;
                    }
                }
            }

            throw new JsonException();
        }

        public override void Write(Utf8JsonWriter writer, Person value, JsonSerializerOptions options)
        {
            writer.WriteStartObject();

            if (value is Customer customer)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Customer);
                writer.WriteNumber("CreditLimit", customer.CreditLimit);
            }
            else if (value is Employee employee)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Employee);
                writer.WriteString("OfficeNumber", employee.OfficeNumber);
            }

            writer.WriteString("Name", value.Name);

            writer.WriteEndObject();
        }
    }
}
```

Der folgende Code registriert den Konverter:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

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

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Übersicht über System. Text. JSON](system-text-json-overview.md)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [Verwenden von "System. Text. JSON"](system-text-json-how-to.md)
* [Quellcode für integrierte Konverter](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* GitHub-Probleme im Zusammenhang mit benutzerdefinierten Konvertern für `System.Text.Json`
  * [36639 Einführung in benutzerdefinierte Konverter](https://github.com/dotnet/corefx/issues/36639)
  * [38713 Informationen zur Deserialisierung in ein Objekt](https://github.com/dotnet/corefx/issues/38713)
  * [40120 Informationen zu nicht-Zeichen folgen Schlüssel Wörterbüchern](https://github.com/dotnet/corefx/issues/40120)
  * [37787 Informationen zur polymorphen Deserialisierung](https://github.com/dotnet/corefx/issues/37787)
