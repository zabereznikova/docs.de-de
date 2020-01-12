---
title: Migrieren von "newtonsoft. JSON" zu "System. Text. JSON" (.net)
author: tdykstra
ms.author: tdykstra
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8b3ffc885691264548a19f694d159ce07aba7550
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904695"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Migrieren von "newtonsoft. JSON" zu "System. Text. JSON"

In diesem Artikel wird gezeigt, wie Sie von " [newtonsoft. JSON](https://www.newtonsoft.com/json) " zu <xref:System.Text.Json>migrieren.

 `System.Text.Json` konzentriert sich hauptsächlich auf die Konformität von Leistung, Sicherheit und Standards. Sie hat einige wesentliche Unterschiede im Standardverhalten und zielt nicht darauf ab, Featureparität mit `Newtonsoft.Json`zu haben. In einigen Szenarien verfügt `System.Text.Json` über keine integrierte Funktionalität, es gibt jedoch empfohlene Problem Umgehungen. In anderen Szenarien sind Problem Umgehungen nicht praktikabel. Wenn Ihre Anwendung von einer fehlenden Funktion abhängig ist, sollten Sie erwägen, [ein Problem](https://github.com/dotnet/runtime/issues/new) zu beheben, um herauszufinden, ob die Unterstützung für das Szenario hinzugefügt werden kann.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

In diesem Artikel wird in den meisten Fällen erläutert, wie Sie die <xref:System.Text.Json.JsonSerializer>-API verwenden. Sie enthält jedoch auch Anleitungen zur Verwendung des <xref:System.Text.Json.JsonDocument> (der die Dokumentobjektmodell-oder Dom-Typen darstellt), <xref:System.Text.Json.Utf8JsonReader>und <xref:System.Text.Json.Utf8JsonWriter>. Der Artikel ist in Abschnitte in der folgenden Reihenfolge gegliedert:

* [Unterschiede in jsonSerializer- **Standard** Verhalten im Vergleich zu "newtonsoft. JSON"](#differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson)
* [Szenarios mit jsonSerializer, die Problem Umgehungen erfordern](#scenarios-using-jsonserializer-that-require-workarounds)
* [Szenarios, die jsonSerializer derzeit nicht unterstützt](#scenarios-that-jsonserializer-currently-doesnt-support)
* ["Jsondocument" und "jsonelement" im Vergleich zu jtoken (z. b. jobject, jarray)](#jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray)
* [Utf8JsonReader im Vergleich zu "jsontextreader"](#utf8jsonreader-compared-to-jsontextreader)
* [Utf8JsonWriter im Vergleich zu JsonTextWriter](#utf8jsonwriter-compared-to-jsontextwriter)

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Unterschiede in jsonSerializer-Standardverhalten im Vergleich zu "newtonsoft. JSON"

<xref:System.Text.Json> ist standardmäßig strikt und vermeidet jegliche Vermutung oder Interpretation im Auftrag des Aufrufers, wobei deterministisches Verhalten hervorgehoben wird. Die Bibliothek ist auf diese Weise absichtlich für Leistung und Sicherheit konzipiert. `Newtonsoft.Json` ist standardmäßig flexibel. Dieser grundlegende Unterschied beim Entwurf liegt hinter vielen der folgenden spezifischen Unterschiede im Standardverhalten.

### <a name="case-insensitive-deserialization"></a>Deserialisierung der Groß-/Kleinschreibung 

Während der Deserialisierung wird in `Newtonsoft.Json` standardmäßig die Groß-/Kleinschreibung nicht beachtet. Beim <xref:System.Text.Json> Standard wird die Groß-/Kleinschreibung beachtet, was eine bessere Leistung bietet, da eine genaue Entsprechung vorliegt. Informationen dazu, wie die Groß-/Kleinschreibung nicht beachtet wird, finden Sie unter Nichtbeachtung der [Groß-/Kleinschreibung](system-text-json-how-to.md#case-insensitive-property-matching)

Wenn Sie `System.Text.Json` indirekt mit ASP.net Core verwenden, müssen Sie nichts tun, um Verhalten wie `Newtonsoft.Json`zu erhalten. ASP.net Core gibt die Einstellungen für [Eigenschaftsnamen mit Kamel](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) Schreibweise und die Groß-/Kleinschreibung bei der Verwendung von `System.Text.Json`an.

### <a name="comments"></a>Kommentare

Während der Deserialisierung ignoriert `Newtonsoft.Json` Kommentare in der JSON-Datei standardmäßig. Der Standard <xref:System.Text.Json> ist das Auslösen von Ausnahmen für Kommentare, da die [RFC 8259](https://tools.ietf.org/html/rfc8259) -Spezifikation diese nicht enthält. Weitere Informationen zum Zulassen von Kommentaren finden Sie unter [Zulassen von Kommentaren und nachfolgenden Kommas](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Nachfolgende Kommas

Während der Deserialisierung ignoriert `Newtonsoft.Json` nachfolgende Kommas standardmäßig. Außerdem werden mehrere nachfolgende Kommas (z. b. `[{"Color":"Red"},{"Color":"Green"},,]`) ignoriert. Der Standard <xref:System.Text.Json> ist das Auslösen von Ausnahmen für nachfolgende Kommas, da die [RFC 8259](https://tools.ietf.org/html/rfc8259) -Spezifikation Sie nicht zulässt. Informationen dazu, wie Sie `System.Text.Json` akzeptieren, finden Sie unter [Zulassen von Kommentaren und nachfolgenden Kommas](system-text-json-how-to.md#allow-comments-and-trailing-commas). Es gibt keine Möglichkeit, mehrere nachfolgende Kommas zuzulassen.

### <a name="json-strings-property-names-and-string-values"></a>JSON-Zeichen folgen (Eigenschaftsnamen und Zeichen folgen Werte)

Während der Deserialisierung akzeptiert `Newtonsoft.Json` Eigenschaftsnamen, die in doppelten Anführungszeichen, einfachen Anführungszeichen oder ohne Anführungszeichen eingeschlossen sind. Sie akzeptiert Zeichen folgen Werte, die in doppelten Anführungszeichen oder einfachen Anführungszeichen eingeschlossen sind. Beispielsweise akzeptiert `Newtonsoft.Json` den folgenden JSON-Code:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json` akzeptiert nur Eigenschaftsnamen und Zeichen folgen Werte in doppelten Anführungszeichen, da dieses Format für die [RFC 8259](https://tools.ietf.org/html/rfc8259) -Spezifikation erforderlich ist und das einzige Format ist, das als gültiger JSON-Code gilt.

Ein in einfache Anführungszeichen eingeschlossener Wert führt zu einer [jsonexception](xref:System.Text.Json.JsonException) mit der folgenden Meldung:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Nicht-Zeichen folgen Werte für Zeichen folgen Eigenschaften

`Newtonsoft.Json` akzeptiert Werte, die keine Zeichenfolge sind, wie z. b. eine Zahl oder die Literale `true` und `false`, für die Deserialisierung von Eigenschaften vom Typ "String". Im folgenden finden Sie ein Beispiel für JSON, das `Newtonsoft.Json` erfolgreich in die folgende Klasse deserialisiert wurde:

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json` deserialisiert keine Werte, die keine Zeichen folgen sind, in Zeichen folgen Eigenschaften. Ein für ein Zeichen folgen Feld empfangener Wert, der keine Zeichenfolge ist, führt zu einer [jsonexception](xref:System.Text.Json.JsonException) mit der folgenden Meldung:

```
The JSON value could not be converted to System.String.
```

### <a name="converter-registration-precedence"></a>Priorität der konverterregistrierung

Die Rangfolge der `Newtonsoft.Json` Registrierung für benutzerdefinierte Konverter lautet wie folgt:

* Attribut für Eigenschaft
* Attribut für Typ
* [Konverter](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) -Auflistung

Diese Reihenfolge bedeutet, dass ein benutzerdefinierter Konverter in der `Converters` Auflistung von einem Konverter überschrieben wird, der durch Anwenden eines Attributs auf der Typebene registriert wird. Beide Registrierungen werden von einem Attribut auf der Eigenschaften Ebene überschrieben.

Die Rangfolge der <xref:System.Text.Json> Registrierung für benutzerdefinierte Konverter ist unterschiedlich:

* Attribut für Eigenschaft
* <xref:System.Text.Json.JsonSerializerOptions.Converters> Sammlung
* Attribut für Typ

Der Unterschied besteht darin, dass ein benutzerdefinierter Konverter in der `Converters`-Auflistung ein Attribut auf Typebene überschreibt. Die Absicht hinter dieser Rangfolge besteht darin, dass Lauf Zeit Änderungen zur Entwurfszeit Auswahl überschrieben werden. Es gibt keine Möglichkeit, die Rangfolge zu ändern.

Weitere Informationen über die benutzerdefinierte konverterregistrierung finden Sie unter [Registrieren eines benutzerdefinierten Konverters](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="character-escaping"></a>Escapezeichen

Während der Serialisierung ist `Newtonsoft.Json` relativ vorsichtig, wenn Sie Zeichen durchlassen, ohne Sie zu entweichen. Dies bedeutet, dass Sie nicht durch `\uxxxx` ersetzt wird, wobei `xxxx` der Codepunkt des Zeichens ist. Wenn Sie diese Escapezeichen mit Escapezeichen versehen, wird eine `\` vor dem Zeichen ausgegeben (z. b. `"` wird `\"`). <xref:System.Text.Json> schützt standardmäßig mehr Zeichen, um Schutz vor Cross-Site Scripting (XSS)-oder Information-Disclosure-Angriffen bereitzustellen. dabei wird die sechs Zeichenfolge verwendet. `System.Text.Json` schützt alle nicht-ASCII-Zeichen standardmäßig, sodass Sie keine Aktion ausführen müssen, wenn Sie `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`verwenden. `System.Text.Json` schützt auch standardmäßig HTML-sensible Zeichen. Weitere Informationen zum Überschreiben des standardmäßigen `System.Text.Json` Verhaltens finden Sie unter [Anpassen der Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).

### <a name="deserialization-of-object-properties"></a>Deserialisierung von Objekteigenschaften

Wenn `Newtonsoft.Json` deserialisiert, um Eigenschaften in POCOS oder in Wörterbüchern vom Typ `Dictionary<string, object>`zu `object`, liegt Folgendes vor:

* Leitet den Typ primitiver Werte in der JSON-Nutzlast (außer `null`) ab und gibt die gespeicherten `string`, `long`, `double`, `boolean`oder `DateTime` als geschachteltes Objekt zurück. *Primitive Werte* sind einzelne JSON-Werte, wie z. b. eine JSON-Zahl, eine Zeichenfolge, eine `true`, `false`oder `null`.
* Gibt eine `JObject` oder `JArray` für komplexe Werte in der JSON-Nutzlast zurück. *Komplexe Werte* sind Auflistungen von JSON-Schlüssel-Wert-Paaren in geschweiften Klammern (`{}`) oder Listen mit Werten innerhalb von Klammern (`[]`). Die Eigenschaften und Werte in geschweiften Klammern oder Klammern können zusätzliche Eigenschaften oder Werte aufweisen.
* Gibt einen NULL-Verweis zurück, wenn die Nutzlast das `null` JSON-Literals hat.

<xref:System.Text.Json> speichert einen geschachtelten `JsonElement` sowohl für primitive als auch für komplexe Werte innerhalb der `System.Object`-Eigenschaft oder des-Wörterbuch Werts. Sie behandelt jedoch `null` identisch mit `Newtonsoft.Json` und gibt einen NULL-Verweis zurück, wenn die Nutzlast das `null` JSON-Literale enthält.

Um den Typrückschluss für `object` Eigenschaften zu implementieren, erstellen Sie einen Konverter wie in dem Beispiel zum [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="maximum-depth"></a>Maximale Tiefe

`Newtonsoft.Json` hat standardmäßig keine Obergrenze für die Tiefe. Für <xref:System.Text.Json> gibt es ein Standard Limit von 64 und kann durch Festlegen von <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>konfiguriert werden.

### <a name="stack-type-handling"></a>Verarbeitung von Stapel Typen

In <xref:System.Text.Json>wird die Reihenfolge der Inhalte eines Stapels bei der Serialisierung rückgängig gemacht. Dieses Verhalten gilt für die folgenden Typen und Schnittstellen sowie benutzerdefinierte Typen, die von Ihnen abgeleitet werden:

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

Ein benutzerdefinierter Konverter könnte implementiert werden, um den Stapel Inhalt in der gleichen Reihenfolge zu behalten.

### <a name="omit-null-value-properties"></a>NULL-Wert-Eigenschaften weglassen

`Newtonsoft.Json` verfügt über eine globale Einstellung, die bewirkt, dass NULL-Wert-Eigenschaften von der Serialisierung ausgeschlossen werden: [nullvaluehandult. Ignore](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_NullValueHandling.htm). Die entsprechende Option in <xref:System.Text.Json> ist <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues%2A>.

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Szenarios mit jsonSerializer, die Problem Umgehungen erfordern

Die folgenden Szenarien werden von der integrierten Funktionalität nicht unterstützt, aber der Beispielcode wird für Problem Umgehungen bereitgestellt. Die meisten der Problem Umgehungen erfordern, dass Sie [benutzerdefinierte Konverter](system-text-json-converters-how-to.md)implementieren.

### <a name="specify-date-format"></a>Datumsformat angeben

`Newtonsoft.Json` bietet mehrere Möglichkeiten, um zu steuern, wie Eigenschaften von `DateTime` und `DateTimeOffset` Typen serialisiert und deserialisiert werden:

* Die `DateTimeZoneHandling` Einstellung kann verwendet werden, um alle `DateTime` Werte als UTC-Datumsangaben zu serialisieren.
* Die `DateFormatString` Einstellung und `DateTime` Konverter können verwendet werden, um das Format von Datums Zeichenfolgen anzupassen.

In <xref:System.Text.Json>ist das einzige Format, das über die integrierte Unterstützung verfügt, ISO 8601-1:2019, da es weitgehend übernommen und eindeutig ist und Roundtrips genau durchführt. Wenn Sie ein anderes Format verwenden möchten, erstellen Sie einen benutzerdefinierten Konverter. Weitere Informationen finden Sie [unter DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON](../datetime/system-text-json-support.md).

### <a name="quoted-numbers"></a>Zahlen in Anführungszeichen

`Newtonsoft.Json` können Zahlen Serialisieren oder Deserialisieren, die durch JSON-Zeichen folgen (in Anführungszeichen eingeschlossen) dargestellt werden. Beispielsweise kann Sie Folgendes akzeptieren: `{"DegreesCelsius":"23"}` anstelle von `{"DegreesCelsius":23}`. Um dieses Verhalten in <xref:System.Text.Json>zu aktivieren, implementieren Sie einen benutzerdefinierten Konverter wie im folgenden Beispiel. Der Konverter behandelt Eigenschaften, die als `long`definiert sind:

* Sie werden als JSON-Zeichen folgen serialisiert. 
* Er akzeptiert JSON-Zahlen und-Zahlen in Anführungszeichen während der Deserialisierung.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) für einzelne `long` Eigenschaften oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung.

### <a name="dictionary-with-non-string-key"></a>Wörterbuch mit nicht-Zeichen folgen Schlüssel

`Newtonsoft.Json` unterstützt Auflistungen vom Typ `Dictionary<TKey, TValue>`. Die integrierte Unterstützung für Wörterbuch Auflistungen in <xref:System.Text.Json> ist auf `Dictionary<string, TValue>`beschränkt. Das heißt, der Schlüssel muss eine Zeichenfolge sein.

Wenn Sie ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel unterstützen möchten, erstellen Sie einen Konverter wie in dem Beispiel zum [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Polymorphe Serialisierung

`Newtonsoft.Json` automatisch polymorphe Serialisierung. Informationen zu den eingeschränkten polymorphen Serialisierungsfunktionen von <xref:System.Text.Json>finden Sie unter [Serialisieren von Eigenschaften abgeleiteter Klassen](system-text-json-how-to.md#serialize-properties-of-derived-classes).

Die hier beschriebene Problem Umgehung besteht darin, Eigenschaften zu definieren, die abgeleitete Klassen als Typ `object`enthalten können. Wenn dies nicht möglich ist, besteht die Möglichkeit, einen Konverter mit einer `Write`-Methode für die gesamte Vererbungs Typen Hierarchie zu erstellen, wie z. b. im Beispiel zum [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Polymorphe Deserialisierung

`Newtonsoft.Json` verfügt über eine `TypeNameHandling` Einstellung, mit der dem JSON-Code beim Serialisieren Typnamen Metadaten hinzugefügt werden. Die Metadaten werden während der Deserialisierung verwendet, um die polymorphe Deserialisierung durchzuführen. <xref:System.Text.Json> können einen begrenzten Bereich der [polymorphen Serialisierung](system-text-json-how-to.md#serialize-properties-of-derived-classes) , aber nicht die polymorphe Deserialisierung durchführen.

Um die polymorphe Deserialisierung zu unterstützen, erstellen Sie einen Konverter wie in dem Beispiel zum [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="required-properties"></a>Erforderliche Eigenschaften

Während der Deserialisierung löst <xref:System.Text.Json> keine Ausnahme aus, wenn im JSON-Code für eine der Eigenschaften des Zieltyps kein Wert empfangen wird. Wenn Sie z. b. über eine `WeatherForecast`-Klasse verfügen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Der folgende JSON-Code wird ohne Fehler deserialisiert:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Um die Deserialisierung fehlschlagen zu lassen, wenn sich keine `Date` Eigenschaft im JSON-Format befindet, implementieren Sie einen benutzerdefinierten Konverter. Der folgende Beispiel-Konvertercode löst eine Ausnahme aus, wenn die `Date`-Eigenschaft nach Abschluss der Deserialisierung nicht festgelegt ist:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs in der poco-Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung.

Wenn Sie dieses Muster befolgen, übergeben Sie das Options-Objekt nicht, wenn Sie <xref:System.Text.Json.JsonSerializer.Serialize%2A> oder <xref:System.Text.Json.JsonSerializer.Deserialize%2A>rekursiv aufrufen. Das Options-Objekt enthält die <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> Auflistung. Wenn Sie Sie an `Serialize` oder `Deserialize`übergeben, ruft der benutzerdefinierte Konverter sich selbst auf, wodurch eine Endlosschleife entsteht, die zu einer Stapelüberlauf Ausnahme führt. Wenn die Standardoptionen nicht möglich sind, erstellen Sie eine neue Instanz der Optionen mit den Einstellungen, die Sie benötigen. Diese Vorgehensweise ist langsam, da jede neue Instanz unabhängig zwischengespeichert wird.

Der vorherige Konvertercode ist ein vereinfachtes Beispiel. Zusätzliche Logik wäre erforderlich, wenn Sie Attribute (z. b. [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) oder andere Optionen (z. b. benutzerdefinierte Encoder) behandeln müssen. Außerdem werden im Beispielcode keine Eigenschaften behandelt, für die im Konstruktor ein Standardwert festgelegt ist. Diese Vorgehensweise unterscheidet sich nicht zwischen den folgenden Szenarien:

* Im JSON-Code fehlt eine Eigenschaft.
* Eine Eigenschaft für einen Typ, der keine NULL-Werte zulässt, ist im JSON-Code vorhanden, aber der Wert ist der Standardwert für den Typ, z. b. 0 (null) für einen `int`.
* Eine Eigenschaft für einen Typ, der NULL-Werte zulässt, ist im JSON-Code vorhanden, aber der Wert ist NULL.

### <a name="deserialize-null-to-non-nullable-type"></a>Deserialisieren von NULL in einen Typ, der keine NULL-Werte zulässt 

`Newtonsoft.Json` löst im folgenden Szenario keine Ausnahme aus:

* `NullValueHandling` ist auf `Ignore`festgelegt, und
* Während der Deserialisierung enthält der JSON-Wert einen NULL-Wert für einen Typ, der keine NULL-Werte zulässt.

Im gleichen Szenario löst <xref:System.Text.Json> eine Ausnahme aus. (Die entsprechende Einstellung für die NULL-Behandlung ist <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)

Wenn Sie den Zieltyp besitzen, besteht die beste Lösung darin, dass die betreffende Eigenschaft NULL-Werte zulässt (z. b. ändern `int` in `int?`).

Eine weitere Problem Umgehung besteht darin, einen Konverter für den Typ zu erstellen, z. b. das folgende Beispiel, das NULL-Werte für `DateTimeOffset` Typen behandelt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Eigenschaft](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung.

**Hinweis:** Der vorherige Konverter **verarbeitet NULL-Werte anders** als `Newtonsoft.Json` für POCOS, die Standardwerte angeben. Nehmen Sie beispielsweise an, der folgende Code stellt das Zielobjekt dar:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Angenommen, der folgende JSON-Code wird mithilfe des vorherigen Konverters deserialisiert:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Nach der Deserialisierung hat die `Date`-Eigenschaft 1/1/0001 (`default(DateTimeOffset)`), d. h., der im Konstruktor festgelegte Wert wird überschrieben. Beim gleichen poco und JSON würde `Newtonsoft.Json` Deserialisierung 1/1/2001 in der `Date`-Eigenschaft belassen.

### <a name="deserialize-to-immutable-classes-and-structs"></a>In unveränderliche Klassen und Strukturen Deserialisieren

`Newtonsoft.Json` können in unveränderliche Klassen und Strukturen deserialisieren, da Sie Konstruktoren mit Parametern verwenden können. <xref:System.Text.Json> unterstützt nur öffentliche Parameter lose Konstruktoren. Um dieses Problem zu umgehen, können Sie einen Konstruktor mit Parametern in einem benutzerdefinierten Konverter aufzurufen.

Im folgenden finden Sie eine unveränderliche Struktur mit mehreren Konstruktorparametern:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

Und hier ist ein Konverter, der diese Struktur serialisiert und deserialisiert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter, indem Sie den Konverter der <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung [Hinzufügen](system-text-json-converters-how-to.md#registration-sample---converters-collection) .

Ein Beispiel für einen ähnlichen Konverter, der offene generische Eigenschaften behandelt, finden Sie unter der [integrierte Konverter für Schlüssel-Wert-Paare](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Zu verwendenden Konstruktor angeben

Mit dem `Newtonsoft.Json` `[JsonConstructor]`-Attribut können Sie angeben, welcher Konstruktor beim Deserialisieren in ein poco aufgerufen werden soll. <xref:System.Text.Json> unterstützt nur Parameter lose Konstruktoren. Um dieses Problem zu umgehen, können Sie den beliebigen Konstruktor, den Sie benötigen, in einem benutzerdefinierten Konverter abrufen. Weitere Informationen finden Sie im Beispiel für die [Deserialisierung in unveränderliche Klassen und Strukturen](#deserialize-to-immutable-classes-and-structs).

### <a name="conditionally-ignore-a-property"></a>Bedingt eine Eigenschaft ignorieren

`Newtonsoft.Json` bietet mehrere Möglichkeiten, eine Eigenschaft bei der Serialisierung oder Deserialisierung bedingt zu ignorieren:

* mit `DefaultContractResolver` können Sie basierend auf beliebigen Kriterien Eigenschaften auswählen, die ein-oder ausgeschlossen werden sollen. 
* Mit den Einstellungen für `NullValueHandling` und `DefaultValueHandling` auf `JsonSerializerSettings` können Sie angeben, dass alle NULL-Wert-oder Standardwert Eigenschaften ignoriert werden sollen.
* Mit den Einstellungen für `NullValueHandling` und `DefaultValueHandling` des `[JsonProperty]`-Attributs können Sie einzelne Eigenschaften angeben, die ignoriert werden sollen, wenn Sie auf NULL oder den Standardwert festgelegt werden.

<xref:System.Text.Json> bietet die folgenden Möglichkeiten, um während der Serialisierung Eigenschaften auszulassen:

* Das [[jsonignore]](system-text-json-how-to.md#exclude-individual-properties) -Attribut für eine Eigenschaft bewirkt, dass die-Eigenschaft während der Serialisierung aus dem JSON-Code weggelassen wird.
* Mit der globalen Option [ignorenullvalues](system-text-json-how-to.md#exclude-all-null-value-properties) können Sie alle NULL-Wert-Eigenschaften ausschließen.
* Mit der globalen Option [ignorereadonlyproperties](system-text-json-how-to.md#exclude-all-read-only-properties) können Sie alle schreibgeschützten Eigenschaften ausschließen.

Diese Optionen erlauben Ihnen **nicht** Folgendes:

* Ignorieren Sie alle Eigenschaften, die über den Standardwert für den Typ verfügen.
* Ignoriert ausgewählte Eigenschaften, die über den Standardwert für den Typ verfügen.
* Ausgewählte Eigenschaften ignorieren, wenn deren Wert NULL ist.
* Die ausgewählten Eigenschaften werden auf der Grundlage beliebiger Kriterien ignoriert, die zur Laufzeit ausgewertet werden. 

Für diese Funktion können Sie einen benutzerdefinierten Konverter schreiben. Im folgenden finden Sie ein Beispiel poco und einen benutzerdefinierten Konverter, der diesen Ansatz veranschaulicht:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Der Konverter bewirkt, dass die `Summary`-Eigenschaft bei der Serialisierung weggelassen wird, wenn der Wert NULL, eine leere Zeichenfolge oder "N/v" ist. 

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung.

Diese Vorgehensweise erfordert zusätzliche Logik, wenn Folgendes erforderlich ist:

* Das poco umfasst komplexe Eigenschaften.
* Sie müssen Attribute wie z. b. `[JsonIgnore]` oder Optionen (z. b. benutzerdefinierte Encoder) behandeln.

### <a name="callbacks"></a>Callbacks

`Newtonsoft.Json` ermöglicht Ihnen das Ausführen von benutzerdefiniertem Code an mehreren Punkten im Serialisierungs-oder Deserialisierungsprozess:

* Ondeserialize (beim Starten der Deserialisierung eines Objekts)
* OnDeserialized (nach Abschluss der Deserialisierung eines Objekts)
* Onserialisieren (beim Beginn der Serialisierung eines Objekts)
* OnSerialized (nach Abschluss der Serialisierung eines Objekts)

In <xref:System.Text.Json>können Sie Rückrufe simulieren, indem Sie einen benutzerdefinierten Konverter schreiben. Das folgende Beispiel zeigt einen benutzerdefinierten Konverter für ein poco. Der Konverter enthält Code, der eine Meldung an jedem Punkt anzeigt, der einem `Newtonsoft.Json` Rückruf entspricht.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung.

Wenn Sie einen benutzerdefinierten Konverter verwenden, der auf das vorangehende Beispiel folgt:

* Der `OnDeserializing` Code hat keinen Zugriff auf die neue poco-Instanz. Um die neue poco-Instanz zu Beginn der Deserialisierung zu bearbeiten, fügen Sie den Code in den poco-Konstruktor ein.
* Übergeben Sie das Options-Objekt nicht, wenn rekursiv `Serialize` oder `Deserialize`aufgerufen wird. Das Options-Objekt enthält die `Converters` Auflistung. Wenn Sie Sie an `Serialize` oder `Deserialize`übergeben, wird der Konverter verwendet, wodurch eine Endlosschleife entsteht, die zu einer Stapelüberlauf Ausnahme führt.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Szenarios, die jsonSerializer derzeit nicht unterstützt

Problem Umgehungen sind in den folgenden Szenarien möglich, einige davon sind jedoch relativ schwierig zu implementieren. In diesem Artikel werden keine Codebeispiele für Problem Umgehungen für diese Szenarien bereitgestellt.

Dabei handelt es sich nicht um eine vollständige Liste der `Newtonsoft.Json` Features, die in `System.Text.Json`keine Entsprechungen aufweisen. Die Liste enthält viele der Szenarien, die bei [GitHub-Problemen](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) oder [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) -Beiträgen angefordert wurden.

Wenn Sie eine Problem Umgehung für eines dieser Szenarien implementieren und den Code freigeben können, wählen Sie unten auf der Seite die Schaltfläche "**This page" (Diese Seite**) aus. Dadurch wird ein GitHub-Problem erstellt und den im unteren Bereich der Seite aufgeführten Problemen hinzugefügt.

### <a name="types-without-built-in-support"></a>Typen ohne integrierte Unterstützung

<xref:System.Text.Json> bietet keine integrierte Unterstützung für die folgenden Typen:

* <xref:System.Data.DataTable> und verwandte Typen
* F#Typen, z. b. Unterscheidungs- [Unions](../../fsharp/language-reference/discriminated-unions.md), [Daten Satz Typen](../../fsharp/language-reference/records.md)und [anonyme Daten Satz Typen](../../fsharp/language-reference/anonymous-records.md).
* Sammlungs Typen im <xref:System.Collections.Specialized>-Namespace
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> und die zugehörigen generischen Typen

Benutzerdefinierte Konverter können für Typen implementiert werden, die über keine integrierte Unterstützung verfügen.

### <a name="public-and-non-public-fields"></a>Öffentliche und nicht öffentliche Felder

`Newtonsoft.Json` können Felder sowie Eigenschaften serialisieren und deserialisieren. <xref:System.Text.Json> funktioniert nur mit öffentlichen Eigenschaften. Diese Funktion kann von benutzerdefinierten Konvertern bereitgestellt werden.

### <a name="internal-and-private-property-setters-and-getters"></a>Interne und private Eigenschaften Setter und-Getter

`Newtonsoft.Json` können private und interne Eigenschaften Setter und Getter über das `JsonProperty`-Attribut verwenden. <xref:System.Text.Json> unterstützt nur öffentliche Setter. Diese Funktion kann von benutzerdefinierten Konvertern bereitgestellt werden.

### <a name="preserve-object-references-and-handle-loops"></a>Objekt Verweise und handle-Schleifen beibehalten

Standardmäßig `Newtonsoft.Json` als Wert serialisiert. Wenn ein Objekt z. b. zwei Eigenschaften enthält, die einen Verweis auf das gleiche `Person` Objekt enthalten, werden die Werte dieser `Person` Objekteigenschaften in der JSON dupliziert.

`Newtonsoft.Json` verfügt über eine `PreserveReferencesHandling` Einstellung für `JsonSerializerSettings`, die die Serialisierung als Verweis ermöglicht:

* Eine bezeichnermetadaten werden dem JSON-Code hinzugefügt, der für das erste `Person` Objekt erstellt wurde.
* Der JSON-Code, der für das zweite `Person` Objekt erstellt wird, enthält einen Verweis auf diesen Bezeichner anstelle von Eigenschafts Werten.

`Newtonsoft.Json` verfügt auch über eine `ReferenceLoopHandling` Einstellung, die es Ihnen ermöglicht, Zirkel Verweise zu ignorieren, anstatt eine Ausnahme auszulösen.

<xref:System.Text.Json> unterstützt nur die Serialisierung nach Wert und löst eine Ausnahme für zirkuläre Verweise aus.

### <a name="systemruntimeserialization-attributes"></a>System. Runtime. Serialization-Attribute

<xref:System.Text.Json> unterstützt keine Attribute aus dem `System.Runtime.Serialization`-Namespace, z. b. `DataMemberAttribute` und `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Oktale Zahlen

`Newtonsoft.Json` behandelt Zahlen mit einer führenden Null als oktale Zahl. <xref:System.Text.Json> lässt keine führenden Nullen zu, da Sie von der Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) nicht zugelassen werden.

### <a name="populate-existing-objects"></a>Auffüllen vorhandener Objekte

Die `JsonConvert.PopulateObject`-Methode in `Newtonsoft.Json` deserialisiert ein JSON-Dokument in eine vorhandene Instanz einer-Klasse, anstatt eine neue-Instanz zu erstellen. <xref:System.Text.Json> erstellt immer eine neue Instanz des Zieltyps mit dem standardmäßigen öffentlichen Parameter losen Konstruktor. Benutzerdefinierte Konverter können in eine vorhandene-Instanz deserialisieren.

### <a name="reuse-rather-than-replace-properties"></a>Wieder verwenden, anstatt Eigenschaften zu ersetzen

Mit der Einstellung `Newtonsoft.Json` `ObjectCreationHandling` können Sie angeben, dass Objekte in Eigenschaften wieder verwendet werden sollen, anstatt während der Deserialisierung ersetzt zu werden. <xref:System.Text.Json> ersetzt Objekte immer in Eigenschaften.  Diese Funktion kann von benutzerdefinierten Konvertern bereitgestellt werden.

### <a name="add-to-collections-without-setters"></a>Zu Sammlungen ohne Setter hinzufügen

Während der Deserialisierung fügt `Newtonsoft.Json` einer Auflistung Objekte hinzu, auch wenn die Eigenschaft über keinen Setter verfügt. <xref:System.Text.Json> ignoriert Eigenschaften, die keine Setter haben. Diese Funktion kann von benutzerdefinierten Konvertern bereitgestellt werden.

### <a name="missingmemberhandling"></a>Missingmembership Handling

`Newtonsoft.Json` kann so konfiguriert werden, dass während der Deserialisierung Ausnahmen ausgelöst werden, wenn die JSON-Eigenschaften enthält, die im Zieltyp fehlen. <xref:System.Text.Json> ignoriert zusätzliche Eigenschaften im JSON-Code, es sei denn, Sie verwenden das [[jsonextensiondata]-Attribut](system-text-json-how-to.md#handle-overflow-json). Für das Feature für fehlende Mitglieder gibt es keine Problem Umgehung.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json` ermöglicht das Debuggen mithilfe einer `TraceWriter` zum Anzeigen von Protokollen, die von der Serialisierung oder Deserialisierung generiert werden. <xref:System.Text.Json> führt keine Protokollierung durch.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>"Jsondocument" und "jsonelement" im Vergleich zu jtoken (z. b. jobject, jarray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, ein Schreib geschütztes Dokumentobjektmodell ( **Read-Only** , DOM) aus vorhandenen JSON-Nutzlasten zu analysieren und zu erstellen. Das Dom bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement> Typ zugegriffen werden. Der `JsonElement`-Typ stellt APIs zum Konvertieren von JSON-Text in allgemeine .NET-Typen bereit. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

### <a name="jsondocument-is-idisposable"></a>Jsondocument kann nicht gelöscht werden.

`JsonDocument` erstellt eine Speicher interne Ansicht der Daten in einem in einem Pool zusammengefassten Puffer. Im Gegensatz zu `JObject` oder `JArray` von `Newtonsoft.Json`implementiert der `JsonDocument` Typ `IDisposable` und muss innerhalb eines using-Blocks verwendet werden. 

Geben Sie nur eine `JsonDocument` von ihrer API zurück, wenn Sie die Lebensdauer übertragen und die Verantwortung für den Aufrufer verwerfen möchten. In den meisten Szenarien ist dies nicht erforderlich. Wenn der Aufrufer mit dem gesamten JSON-Dokument arbeiten muss, geben Sie den <xref:System.Text.Json.JsonElement.Clone%2A> des <xref:System.Text.Json.JsonDocument.RootElement%2A>zurück, bei dem es sich um einen <xref:System.Text.Json.JsonElement>handelt. Wenn der Aufrufer mit einem bestimmten Element innerhalb des JSON-Dokuments arbeiten muss, geben Sie die <xref:System.Text.Json.JsonElement.Clone%2A> dieser <xref:System.Text.Json.JsonElement>zurück. Wenn Sie die `RootElement` oder ein Unterelement direkt zurückgeben, ohne eine `Clone`zu erstellen, kann der Aufrufer nicht auf die zurückgegebene `JsonElement` zugreifen, nachdem der `JsonDocument`, der den Besitzer besitzt, verworfen wird.

Es folgt ein Beispiel, in dem Sie eine `Clone`erstellen müssen:

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());
   
    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

Der vorangehende Code erwartet eine `JsonElement`, die eine `fileName`-Eigenschaft enthält. Die JSON-Datei wird geöffnet, und es wird eine `JsonDocument`erstellt. Die Methode geht davon aus, dass der Aufrufer mit dem gesamten Dokument arbeiten möchte, sodass er die `Clone` der `RootElement`zurückgibt. 

Wenn Sie eine `JsonElement` erhalten und ein untergeordnetes Element zurückgibt, ist es nicht erforderlich, eine `Clone` des unter Elements zurückzugeben. Der Aufrufer ist dafür verantwortlich, den `JsonDocument` zu bewahren, zu dem die Übergabe `JsonElement` gehört. Beispiel:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>"Jsondocument" ist schreibgeschützt.

Das <xref:System.Text.Json> Dom kann JSON-Elemente nicht hinzufügen, entfernen oder ändern. Diese Methode ist für die Leistung und die Reduzierung von Zuordnungen zum übernehmen allgemeiner JSON-Nutz Last Größen (< 1 MB) konzipiert. Wenn in Ihrem Szenario derzeit ein änderbares Dom verwendet wird, kann eine der folgenden Problem Umgehungen möglich sein:

* Um eine `JsonDocument` von Grund auf neu zu erstellen (d. h., ohne eine vorhandene JSON-Nutzlast an die `Parse`-Methode zu übergeben), schreiben Sie den JSON-Text mithilfe des `Utf8JsonWriter`, und analysieren Sie die Ausgabe, um eine neue `JsonDocument`zu erstellen.
* Um einen vorhandenen `JsonDocument`zu ändern, verwenden Sie ihn, um JSON-Text zu schreiben, Änderungen vorzunehmen, während Sie schreiben, und die Ausgabe daraus zu analysieren, um eine neue `JsonDocument`zu erstellen.
* Informationen zum Zusammenführen vorhandener JSON-Dokumente, die den `JObject.Merge`-oder `JContainer.Merge`-APIs von `Newtonsoft.Json`entsprechen, finden Sie in [diesem GitHub-Problem](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>Jsonelement ist eine Union-Struktur.

`JsonDocument` macht die `RootElement` als Eigenschaft des Typs <xref:System.Text.Json.JsonElement>verfügbar. dabei handelt es sich um einen Union-, Strukturtyp, der ein beliebiges JSON-Element umfasst. in `Newtonsoft.Json` werden dedizierte hierarchische Typen wie `JObject`,`JArray`, `JToken`usw. verwendet. `JsonElement` ist das, was Sie durchsuchen und aufzählen können, und Sie können `JsonElement` verwenden, um JSON-Elemente in .NET-Typen zu materialisieren.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Vorgehensweise beim Durchsuchen von "jsondocument" und "jsonelement" nach untergeordneten Elementen

Sucht nach JSON-Token mithilfe von `JObject` oder `JArray` von `Newtonsoft.Json` ist tendenziell relativ schnell, da Sie in einem Wörterbuch gesucht werden. Im Vergleich dazu erfordert die Suche nach `JsonElement` eine sequenzielle Suche der Eigenschaften und ist daher relativ langsam (z. b. bei Verwendung `TryGetProperty`). <xref:System.Text.Json> ist so konzipiert, dass die anfängliche Analysezeit und nicht die Such Zeit minimiert werden. Verwenden Sie daher die folgenden Ansätze, um die Leistung beim Durchsuchen eines `JsonDocument` Objekts zu optimieren:

* Verwenden Sie die integrierten Enumeratoren (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> und <xref:System.Text.Json.JsonElement.EnumerateObject%2A>), anstatt ihre eigene Indizierung oder Schleifen zu verwenden.
* Führen Sie keine sequenzielle Suche in der gesamten `JsonDocument` durch, indem Sie `RootElement`verwenden. Suchen Sie stattdessen nach geschposteten JSON-Objekten, die auf der bekannten Struktur der JSON-Daten basieren. Wenn Sie z. b. nach einer `Grade`-Eigenschaft in `Student` Objekten suchen, durchlaufen Sie die `Student` Objekte und erhalten den Wert `Grade` für jede, anstatt alle `JsonElement` Objekte zu durchsuchen, die nach `Grade` Eigenschaften suchen. Durch die letztgenannte Durchführung werden unnötige Daten übermittelt.

Ein Codebeispiel finden Sie unter [Verwenden von jsondocument für den Zugriff auf Daten](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader im Vergleich zu "jsontextreader"

bei <xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> handelt es sich um einen vorwärts gerichteten Reader mit hoher Leistung für UTF-8-codierten JSON-Text, der aus einem Read- [lyspan-\<Byte >](xref:System.ReadOnlySpan%601) oder einer [\<Byte > von "Read onlysequence](xref:System.Buffers.ReadOnlySequence%601)" gelesen wird. Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parser und deserialisierern verwendet werden kann.

In den folgenden Abschnitten werden die empfohlenen Programmier Muster für die Verwendung von `Utf8JsonReader`erläutert.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader ist eine Ref-Struktur.

Da der `Utf8JsonReader` Typ eine *ref-Struktur*ist, gelten [bestimmte Einschränkungen](../../csharp/language-reference/keywords/ref.md#ref-struct-types). Sie kann z. b. nicht als Feld in einer anderen Klasse oder Struktur als einer ref-Struktur gespeichert werden. Um eine hohe Leistung zu erzielen, muss dieser Typ eine `ref struct` sein, da er die Eingabe "read- [lyspan"\<Byte->](xref:System.ReadOnlySpan%601)Zwischenspeichern muss, das wiederum eine Ref-Struktur ist. Außerdem ist dieser Typ änderbar, da er den Status aufweist. **Übergeben Sie Sie** daher anstelle von Wert an Ref. Das übergeben als Wert führt zu einer Struktur Kopie, und die Zustandsänderungen sind für den Aufrufer nicht sichtbar. Dies unterscheidet sich von `Newtonsoft.Json`, da die `Newtonsoft.Json` `JsonTextReader` eine-Klasse ist. Weitere Informationen zum Verwenden von Ref-Strukturen finden Sie unter [Schreiben von sicherem und C# effizienterem Code](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>UTF-8-Text lesen

Lesen Sie die JSON-Nutzlasten, die bereits als UTF-8-Text und nicht als UTF-16-Zeichen folgen codiert sind, um die bestmögliche `Utf8JsonReader`Leistung zu erzielen. Ein Codebeispiel finden Sie unter [Filtern von Daten mithilfe von Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Lesen mit einem Stream oder pipereader

Der `Utf8JsonReader` unterstützt das Lesen aus einer UTF-8-codierten [readonlyspan\<Byte >](xref:System.ReadOnlySpan%601) oder [readonlysequence\<Byte >](xref:System.Buffers.ReadOnlySequence%601) (das Ergebnis des Lesens aus einer <xref:System.IO.Pipelines.PipeReader>).

Beim synchronen lesen können Sie die JSON-Nutzlast bis zum Ende des Streams in ein Bytearray einlesen und an den Reader übergeben. Zum Lesen aus einer Zeichenfolge (die als UTF-16 codiert ist), wenden Sie <xref:System.Text.Encoding.UTF8>an.<xref:System.Text.Encoding.GetBytes%2A> , um die Zeichenfolge zunächst in ein UTF-8-codiertes Bytearray zu transcodieren. Übergeben Sie diese dann an den `Utf8JsonReader`. 

Da der `Utf8JsonReader` die Eingabe als JSON-Text betrachtet, wird eine UTF-8-Byte Reihenfolge-Marke (BOM) als ungültiges JSON-Format angesehen. Der Aufrufer muss diese filtern, bevor die Daten an den Reader übergeben werden.

Codebeispiele finden Sie unter [Verwenden von Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Lesen mit einer Schreib Sequenz mit mehreren Segmenten

Wenn es sich bei der JSON-Eingabe um eine [lesellyspan-\<Byte >](xref:System.ReadOnlySpan%601)handelt, kann auf jedes JSON-Element von der `ValueSpan`-Eigenschaft des Readers zugegriffen werden, während Sie die Lese Schleife durchlaufen. Wenn die Eingabe jedoch eine [readonlysequence-\<Byte >](xref:System.Buffers.ReadOnlySequence%601) ist (was das Ergebnis des Lesens aus einer <xref:System.IO.Pipelines.PipeReader>ist), können einige JSON-Elemente mehrere Segmente des `ReadOnlySequence<byte>` Objekts überschreiten. Auf diese Elemente kann von <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in einem zusammenhängenden Speicherblock nicht zugegriffen werden. Rufen Sie stattdessen die <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A>-Eigenschaft des Readers ab, um zu ermitteln, wie der Zugriff auf das aktuelle JSON-Element erfolgt, wenn Sie über ein `ReadOnlySequence<byte>` als Eingabe verfügen. Dies ist ein empfohlenes Muster:

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>Verwenden von "valuetextequals" für die Suche nach Eigenschaftsnamen

Verwenden Sie <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> nicht, um bytevergleiche durchzuführen, indem Sie <xref:System.MemoryExtensions.SequenceEqual%2A> für Eigenschaftennamen suchen. Stattdessen wird <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> aufgerufen, da diese Methode Escapezeichen aus dem JSON-Code entfernt. Im folgenden finden Sie ein Beispiel, das zeigt, wie Sie nach einer Eigenschaft mit dem Namen "Name" suchen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>NULL-Werte in Werttypen, die NULL zulassen

`Newtonsoft.Json` stellt APIs bereit, die <xref:System.Nullable%601>zurückgeben, wie z. b. `ReadAsBoolean`, das eine `Null` `TokenType` für Sie durch Zurückgeben eines `bool?`verarbeitet. Die integrierten `System.Text.Json`-APIs geben nur nicht auf NULL festleg Bare Werttypen zurück. Beispielsweise gibt <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> einen `bool`zurück. Es wird eine Ausnahme ausgelöst, wenn `Null` in der JSON-Datei gefunden wird. In den folgenden Beispielen werden zwei Möglichkeiten zum Behandeln von NULL-Werten veranschaulicht: eine, indem ein Werte zulässt-Werttyp zurückgegeben wird, und eine, indem der Standardwert

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>Festlegung von Zielversionen

Wenn Sie `Newtonsoft.Json` für bestimmte Ziel-Frameworks weiterhin verwenden müssen, können Sie mehrere Ziele verwenden und zwei Implementierungen verwenden. Dies ist jedoch nicht trivial und erfordert einige `#ifdefs` und die Quell Duplizierung. Eine Möglichkeit, so viel Code wie möglich freizugeben, besteht darin, einen `ref struct` Wrapper um `Utf8JsonReader` und `Newtonsoft.Json` `JsonTextReader`zu erstellen. Mit diesem Wrapper wird die öffentliche Oberfläche vereinheitlicht, während die Verhaltensunterschiede isoliert werden. Auf diese Weise können Sie die Änderungen vor allem an der Erstellung des Typs isolieren und den neuen Typ als Verweis übergeben. Dies ist das Muster, dem die [Microsoft. Extensions. dependencymodel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) -Bibliothek folgt:

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter im Vergleich zu JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine hochleistungsfähige Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32`und `DateTime`. Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann.

In den folgenden Abschnitten werden die empfohlenen Programmier Muster für die Verwendung von `Utf8JsonWriter`erläutert.

### <a name="write-with-utf-8-text"></a>Schreiben mit UTF-8-Text

Um die bestmögliche Leistung bei der Verwendung des `Utf8JsonWriter`zu erzielen, schreiben sie JSON-Nutzlasten, die bereits als UTF-8-Text codiert sind, anstatt als UTF-16-Zeichen folgen Verwenden Sie <xref:System.Text.Json.JsonEncodedText>, um bekannte Zeichen folgen Eigenschaftsnamen und-Werte als Statics zwischenzuspeichern und zu codieren, und übergeben Sie Sie an den Writer, anstatt UTF-16-Zeichen folgen Literale zu verwenden. Dies ist schneller als das Zwischenspeichern und Verwenden von UTF-8-Byte Arrays.

Diese Vorgehensweise funktioniert auch, wenn Sie benutzerdefiniertes Escapezeichen ausführen müssen. mit `System.Text.Json` können Sie das Escapezeichen beim Schreiben einer Zeichenfolge nicht deaktivieren. Sie können jedoch auch Ihre eigene benutzerdefinierte <xref:System.Text.Encodings.Web.JavaScriptEncoder> als Option an den Writer übergeben oder eigene `JsonEncodedText` erstellen, die die `JavascriptEncoder` für das Escapezeichen verwenden, und dann die `JsonEncodedText` anstelle der Zeichenfolge schreiben. Weitere Informationen finden Sie unter [Anpassen der Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Rohwerte schreiben

Die `Newtonsoft.Json` `WriteRawValue`-Methode schreibt unformatierten JSON-Code, wenn ein Wert erwartet wird. <xref:System.Text.Json> hat keine direkte Entsprechung, aber hier ist eine Problem Umgehung, die sicherstellt, dass nur gültige JSON-Code geschrieben werden:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Zeichen Escapezeichen anpassen

Die [stringescapehanding](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) -Einstellung von `JsonTextWriter` bietet Optionen, um alle nicht-ASCII-Zeichen **oder** HTML-Zeichen zu entfernen. Standardmäßig werden `Utf8JsonWriter` alle nicht-ASCII- **und HTML-Zeichen als** Escapezeichen versehen. Diese Escapezeichen werden aus Sicherheitsgründen geschützt. Um eine andere escaperichtlinie anzugeben, erstellen Sie eine <xref:System.Text.Encodings.Web.JavaScriptEncoder>, und legen Sie <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>fest. Weitere Informationen finden Sie unter [Anpassen der Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Anpassen des JSON-Formats

`JsonTextWriter` umfasst die folgenden Einstellungen, für die `Utf8JsonWriter` keine Entsprechung hat:

* [Einzug](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) : gibt an, wie viele Zeichen eingegeben werden sollen. `Utf8JsonWriter` immer zwei Zeichen Einzug.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) : gibt das Zeichen an, das für den Einzug verwendet werden soll.  `Utf8JsonWriter` verwendet immer Leerzeichen.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) : gibt das Zeichen an, das zum Umschließen von Zeichen folgen Werten verwendet wird.  `Utf8JsonWriter` verwendet immer doppelte Anführungszeichen.
* [QUOTENAME](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) : gibt an, ob Eigenschaftsnamen in Anführungszeichen eingeschlossen werden sollen.  `Utf8JsonWriter` werden Sie immer in Anführungszeichen eingeschlossen.

Es gibt keine Problem Umgehungen, mit denen Sie die von `Utf8JsonWriter` erzeugten JSON-Datei auf diese Weise anpassen können.

### <a name="write-null-values"></a>NULL-Werte schreiben

Um NULL-Werte mit `Utf8JsonWriter`zu schreiben, geben Sie Folgendes an:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>, um ein Schlüssel-Wert-Paar mit NULL als Wert zu schreiben.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>, um NULL als Element eines JSON-Arrays zu schreiben.

Wenn die Zeichenfolge für eine Zeichen folgen Eigenschaft NULL ist, entsprechen <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> und <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> `WriteNull` und `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Schreiben von TimeSpan-, Uri-oder Char-Werten

`JsonTextWriter` stellt `WriteValue` Methoden für [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)-, [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)-und [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) -Werte bereit. `Utf8JsonWriter` verfügt nicht über äquivalente-Methoden. Formatieren Sie diese Werte stattdessen als Zeichen folgen (z. b. durch Aufrufen von `ToString()`), und rufen Sie <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>auf.

### <a name="multi-targeting"></a>Festlegung von Zielversionen

Wenn Sie `Newtonsoft.Json` für bestimmte Ziel-Frameworks weiterhin verwenden müssen, können Sie mehrere Ziele verwenden und zwei Implementierungen verwenden. Dies ist jedoch nicht trivial und erfordert einige `#ifdefs` und die Quell Duplizierung. Eine Möglichkeit, so viel Code wie möglich freizugeben, ist die Erstellung eines Wrappers um `Utf8JsonWriter` und `Newtonsoft` `JsonTextWriter`. Mit diesem Wrapper wird die öffentliche Oberfläche vereinheitlicht, während die Verhaltensunterschiede isoliert werden. Auf diese Weise können Sie die Änderungen vor allem an der Erstellung des Typs isolieren. Die Bibliothek [Microsoft. Extensions. dependencymodel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) folgt:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Weitere Ressourcen

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [Übersicht über System. Text. JSON](system-text-json-overview.md)
* [Verwenden von "System. Text. JSON"](system-text-json-how-to.md)
* [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md)
* [DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON](../datetime/system-text-json-support.md)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [System. Text. JSON. Serialization-API-Referenz](xref:System.Text.Json.Serialization)
