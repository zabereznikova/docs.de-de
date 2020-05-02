---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung – .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159571"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a>Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (Marshallen) in .NET

In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für JSON-Serialisierungsklassen erstellen, die im <xref:[!OP.NO-LOC(System.Text.Json)]>-Namespace bereitgestellt werden. Eine Einführung zu `[!OP.NO-LOC(System.Text.Json)]` finden Sie unter [Serialisieren und Deserialisieren von JSON-Daten in .NET](system-text-json-how-to.md).

Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert. Der `[!OP.NO-LOC(System.Text.Json)]`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-Primitiven entsprechen. Sie können benutzerdefinierte Konverter schreiben:

* Um das Standardverhalten eines integrierten Konverters außer Kraft zu setzen. Vielleicht möchten Sie zum Beispiel `DateTime`-Werte im Format „mm/dd/yyyy“ anstatt im Standardformat ISO 8601-1:2019 darstellen.
* Um einen benutzerdefinierten Werttyp zu unterstützen. Beispielsweise eine `PhoneNumber`-Struktur.

Sie können auch benutzerdefinierte Konverter schreiben, um `[!OP.NO-LOC(System.Text.Json)]` mit Funktionen anzupassen oder zu erweitern, die nicht im aktuellen Release enthalten sind. Folgende Szenarien werden später in diesem Artikel abgedeckt:

* [Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).
* [Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key).
* [Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization).

## <a name="custom-converter-patterns"></a>Benutzerdefinierte Konvertermuster

Es gibt zwei Muster zum Erstellen eines benutzerdefinierten Konverters: das grundlegende Muster und das Factorymuster. Das Factorymuster ist für Konverter vorgesehen, die den `Enum`-Typ oder offene generische Typen verarbeiten. Das grundlegende Muster ist für nicht generische und geschlossene generische Typen gedacht.  Konverter für die folgenden Typen erfordern z. B. das Factorymuster:

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

Einige Beispiele für Typen, die vom grundlegenden Muster verarbeitet werden können, sind u. a.:

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

Das grundlegende Muster erstellt eine Klasse, die einen Typ verarbeiten kann. Das Factorymuster erstellt eine Klasse, die zur Laufzeit bestimmt, welcher spezifische Typ erforderlich ist, und erstellt dynamisch den entsprechenden Konverter.

## <a name="sample-basic-converter"></a>Grundlegender Konverter – Beispiel

Das folgende Beispiel ist ein Konverter, der die Standardserialisierung für einen vorhandenen Datentyp außer Kraft setzt. Der Konverter verwendet das Format „mm/dd/yyyy“ für `DateTimeOffset`-Eigenschaften.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a>Factorymusterkonverter – Beispiel

Im folgenden Code wird ein benutzerdefinierter Konverter gezeigt, der mit `Dictionary<Enum,TValue>` arbeitet. Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und der zweite offen ist. Die `CanConvert`-Methode gibt `true` nur für ein `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist. Der innere Konverter ruft einen vorhandenen Konverter ab, um jeglichen Typ zu verarbeiten, der zur Laufzeit für `TValue` bereitgestellt wird.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Der vorangehende Code ist identisch mit dem, der weiter unten in diesem Artikel unter [Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key) gezeigt wird.

## <a name="steps-to-follow-the-basic-pattern"></a>Schritte zum Einhalten des grundlegenden Musters

Die folgenden Schritte erläutern, wie Sie einen Konverter erstellen, indem Sie dem grundlegenden Muster folgen:

* Erstellen Sie eine Klasse, die von <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> abgeleitet ist, wobei `T` der Typ ist, der serialisiert und deserialisiert werden soll.
* Setzen Sie die `Read`-Methode außer Kraft, um den eingehenden JSON-Code zu deserialisieren und in den Typ `T` zu konvertieren. Verwenden Sie den <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader>, der an die Methode übergeben wird, um den JSON-Code zu lesen.
* Setzen Sie die `Write`-Methode außer Kraft, um das eingehende Objekt vom Typ `T` zu serialisieren. Verwenden Sie den <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter>, der an die Methode übergeben wird, um den JSON-Code zu schreiben.
* Setzen Sie die `CanConvert`-Methode nur außer Kraft, wenn dies notwendig ist. Die Standardimplementierung gibt `true` zurück, wenn der zu konvertierende Typ vom Typ `T` ist. Daher müssen Konverter, die nur den Typ `T` unterstützen, diese Methode nicht außer Kraft setzen. Ein Beispiel für einen Konverter, der diese Methode außer Kraft setzen muss, finden Sie im weiter unten in diesem Artikel im Abschnitt [Polymorphe Deserialisierung](#support-polymorphic-deserialization).

Sie können den [Quellcode des integrierten Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) als Referenzimplementierungen zum Schreiben von benutzerdefinierten Konvertern verwenden.

## <a name="steps-to-follow-the-factory-pattern"></a>Schritte zum Einhalten des Factorymusters

Die folgenden Schritte erläutern, wie Sie einen Konverter erstellen, indem Sie dem Factorymuster folgen:

* Erstellen Sie eine von der <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>-Klasse abgeleitete Klasse.
* Überschreiben Sie die `CanConvert`-Methode, um „true“ zurückzugeben, wenn der zu konvertierende Typ einer ist, den der Konverter verarbeiten kann. Wenn der Konverter z. B. für `List<T>` ist, kann er eventuell nur `List<int>`, `List<string>` und `List<DateTime>` verarbeiten.
* Stezen Sie die `CreateConverter`-Methode außer Kraft, um eine Instanz einer Konverterklasse zurückzugeben, die den zur Laufzeit bereitgestellten zu konvertierenden Typ verarbeitet.
* Erstellen Sie die Konverterklasse, die von der `CreateConverter`-Methode instanziiert wird.

Das Factorymuster ist für offene generische Typen erforderlich, da der Code, mit dem ein Objekt in eine und aus einer Zeichenfolge konvertiert werden soll, nicht für alle Typen identisch ist. Ein Konverter für einen offenen generischen Typ (z. B. `List<T>`) muss verdeckt einen Konverter für einen geschlossenen generischen Typ erstellen (z. B. `List<DateTime>`). Es muss Code geschrieben werden, um jeden geschlossenen generischen Typ zu verarbeiten, den der Konverter verarbeiten kann.

Der Typ `Enum` ähnelt einem offenen generischen Typ: Ein Konverter für `Enum` muss verdeckt einen Konverter für einen spezifischen `Enum` (z. B. `WeekdaysEnum`) erstellen.

## <a name="error-handling"></a>Fehlerbehandlung

Wenn Sie im Fehlerbehandlungscode eine Ausnahme auslösen müssen, sollten Sie erwägen, eine <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> ohne Meldung auszulösen. Dieser Ausnahmetyp erstellt automatisch eine Meldung, die den Pfad zu dem Teil des JSON-Codes enthält, der den Fehler verursacht hat. Beispielsweise erzeugt die Anweisung `throw new JsonException();` eine Fehlermeldung wie im folgenden Beispiel:

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Wenn Sie eine Meldung angeben (z. B. `throw new JsonException("Error occurred")`), stellt die Ausnahme immer noch den Pfad in der <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path>-Eigenschaft bereit.

## <a name="register-a-custom-converter"></a>Registrieren eines benutzerdefinierten Konverters

*Registrieren Sie* einen benutzerdefinierten Konverter, damit die Methoden `Serialize` und `Deserialize` diesen verwenden. Wählen Sie einen der folgenden Ansätze aus:

* Hinzufügen einer Instanz des Konverters zu der <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType>-Sammlung.
* Anwenden des [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute)-Attributs auf die Eigenschaften, die den benutzerdefinierten Konverter benötigen.
* Anwenden des [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute)-Attributs auf eine Klasse oder Struktur, die einen benutzerdefinierten Werttyp darstellt.

## <a name="registration-sample---converters-collection"></a>Registrierungsbeispiel – Converters-Sammlung

Im Folgenden finden Sie ein Beispiel, mit dem der <xref:System.ComponentModel.DateTimeOffsetConverter> zum Standard für Eigenschaften vom Typ <xref:System.DateTimeOffset> gemacht wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

Angenommen, Sie serialisieren eine Instanz des folgenden Typs:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Hier sehen Sie ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Der folgende Code verwendet denselben Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset`-Konverters:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a>Registrierungsbeispiel – [JsonConverter]-Attribut für eine Eigenschaft

Im folgenden Code wird ein benutzerdefinierter Konverter für die `Date`-Eigenschaft ausgewählt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

Der Code zum Serialisieren von `WeatherForecastWithConverterAttribute` erfordert nicht die Verwendung von `JsonSerializeOptions.Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

Der Code zum Deserialisieren erfordert ebenfalls nicht die Verwendung von `Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a>Registrierungsbeispiel – [JsonConverter]-Attribut für einen Typ

Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

Hier sehen Sie den benutzerdefinierten Konverter für die vorangehende Struktur:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

Das `[JsonConvert]`-Attribut der Struktur registriert den benutzerdefinierten Konverter als Standard für Eigenschaften vom Typ `Temperature`. Der Konverter wird automatisch für die `TemperatureCelsius`-Eigenschaft des folgenden Typs verwendet, wenn Sie sie serialisieren oder deserialisieren:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a>Rangfolge für die Registrierung von Konvertern

Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element ein Konverter in der folgenden Reihenfolge ausgewählt, wobei die Auflistung von der höchsten Priorität zur niedrigsten erfolgt:

* Auf eine Eigenschaft angewendeter `[JsonConverter]`.
* Ein der `Converters`-Sammlung hinzugefügt er Konverter.
* Auf einen benutzerdefinierten Werttyp oder ein POCO angewendeter `[JsonConverter]`.

Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters`-Sammlung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` „true“ zurückgibt.

Ein integrierter Konverter wird nur ausgewählt, wenn kein anwendbarer benutzerdefinierter Konverter registriert ist.

## <a name="converter-samples-for-common-scenarios"></a>Konverterbeispiele für gängige Szenarien

In den folgenden Abschnitten werden Konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.

* [Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties)
* [Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key)
* [Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserialisieren abgeleiteter Typen in Objekteigenschaften

Beim Deserialisieren in eine Eigenschaft vom Typ `object` wird ein `JsonElement` Objekt erstellt. Der Grund dafür ist, dass der Deserialisierer nicht weiß, welcher CLR-Typ erstellt werden soll, und nicht versucht, diesen vorherzusagen. Wenn z. B. eine JSON-Eigenschaft den Wert „true“ hat, leitet der Deserialisierer nicht ab, dass der Wert vom Typ `Boolean` ist, und wenn ein Element „01/01/2019“ aufweist, leitet der Deserialisierer nicht ab, dass es sich um einen `DateTime`-Typ handelt.

Typableitung kann ungenau sein. Wenn der Deserialisierer eine JSON-Zahl, die kein Dezimaltrennzeichen aufweist, als `long` analysiert, kann dies zu einem „außerhalb des zulässigen Bereichs“-Probleme führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger` serialisiert wurde. Wird eine Zahl, die ein Dezimaltrennzeichen aufweist, als `double` analysiert, kann hierdurch die Genauigkeit verloren gehen, wenn die Zahl ursprünglich als `decimal` serialisiert wurde.

Für Szenarien, die eine Typableitung erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `object`-Eigenschaften an. Der Code konvertiert Folgendes:

* `true` un `false` in `Boolean`
* Zahlen ohne Dezimaltrennzeichen in `long`
* Zahlen mit Dezimaltrennzeichen in `double`
* Datumsangaben in `DateTime`
* Zeichenfolgen in `string`
* Alles andere in `JsonElement`

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

Hier ist ein Beispieltyp mit `object`-Eigenschaften:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

Das folgende Beispiel für zu deserialisierenden JSON-Code enthält Werte, die als `DateTime`, `long` und `string` deserialisiert werden:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.

Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung in `object`-Eigenschaften verarbeiten.

### <a name="support-dictionary-with-non-string-key"></a>Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind

Die integrierte Unterstützung für Wörterbuchsammlungen ist für `Dictionary<string, TValue>`. Das heißt, der Schlüssel muss eine Zeichenfolge sein. Um ein Wörterbuch mit einem Schlüssel vom Typ „integer“ (Ganzzahl) oder einem anderen Typ zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.

Im folgenden Code wird ein benutzerdefinierter Konverter gezeigt, der mit `Dictionary<Enum,TValue>` arbeitet:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die die folgende `Enum` verwendet:

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

Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind, verarbeiten.

### <a name="support-polymorphic-deserialization"></a>Unterstützung polymorpher Deserialisierung

Integrierte Funktionen bieten einen begrenzten Funktionsbereich der [polymorphen Serialisierung](system-text-json-how-to.md#serialize-properties-of-derived-classes), aber gar keine Unterstützung für Deserialisierung. Die Deserialisierung erfordert einen benutzerdefinierten Konverter.

Angenommen, Sie verfügen beispielsweise über eine abstrakte Basisklasse `Person` mit den abgeleiteten Klassen `Employee` und `Customer`. Polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können, und dass die Objekte `Customer` und `Employee` im JSON-Code zur Laufzeit ordnungsgemäß deserialisiert werden. Während der Deserialisierung müssen Sie nach Hinweisen suchen, die den erforderlichen Typ in JSON identifizieren. Die Arten der verfügbaren Hinweise variieren in jedem Szenario. Beispielsweise kann eine Diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist. Das aktuelle Release von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe Deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.

Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter für diese. Der Konverter verwendet eine Diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen. Der Typdiskriminator befindet sich nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

Der folgende Code registriert den Konverter:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

Das JSON kann mit demselben Konverter deserialisiert werde, mit dem es auch serialisiert wurde, z. B.:

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

Mit dem Konvertercode im vorherigen Beispiel wird jede Eigenschaft manuell gelesen und geschrieben. Eine Alternative besteht darin, `Deserialize` oder `Serialize` aufzurufen, um einen Teil der Arbeit zu erledigen. Ein Beispiel hierzu finden Sie in [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/59744873/12509023).

## <a name="other-custom-converter-samples"></a>Weitere Beispiele für benutzerdefinierte Konverter

Im Artikel [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) finden Sie zusätzliche Beispiele für benutzerdefinierte Konverter.

Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Quellcode enthält weitere Beispiele für benutzerdefinierte Konverter, wie z. B.:

* [Int32-Konverter, der bei der Deserialisierung Null in 0 konvertiert](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)
* [Int32-Konverter, der beim Deserialisieren sowohl Zeichenfolgen- als auch Zahlenwerte zulässt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)
* [Enum-Konverter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)
* [List\<T>-Konverter, der externe Daten akzeptiert](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)
* [„Long[]“-Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen arbeitet](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)

Wenn Sie einen Konverter erstellen müssen, der das Verhalten eines vorhandenen integrierten Konverters ändert, können Sie [den Quellcode des vorhandenen Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) abrufen, um diesen als Ausgangspunkt für die Anpassung zu verwenden.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Quellcode für integrierte Konverter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)
* [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Verwenden von System.Text.Json](system-text-json-how-to.md)
* [Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
