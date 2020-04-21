---
title: Migrieren von Newtonsoft.Json - System.Text.Json .NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 0828a5654171df39230055215903d3a49690155d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739239"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Migrieren aus Newtonsoft.Json zu System.Text.Json

Dieser Artikel zeigt, wie Sie von <xref:System.Text.Json> [Newtonsoft.Json](https://www.newtonsoft.com/json) nach migrieren.

Der `System.Text.Json` Namespace bietet Funktionen zum Serialisieren und Deserialisieren von JavaScript Object Notation (JSON). Die `System.Text.Json` Bibliothek ist im freigegebenen [.NET Core 3.0-Framework](https://aka.ms/netcore3download) enthalten. Installieren Sie für andere Zielframeworks das [Paket System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet. Das Paket unterstützt:

* .NET Standard 2.0 und neuere Versionen
* .NET Framework 4.7.2 und neuere Versionen
* .NET Core 2.0, 2.1 und 2.2

`System.Text.Json`konzentriert sich in erster Linie auf Leistung, Sicherheit und Einhaltung von Standards. Es hat einige wichtige Unterschiede im Standardverhalten und hat nicht `Newtonsoft.Json`das Ziel, Feature-Parität mit zu haben. Für einige `System.Text.Json` Szenarien, hat keine integrierte Funktionalität, aber es gibt empfohlene Problemumgehungen. Für andere Szenarien sind Problemumgehungen nicht praktikabel. Wenn Ihre Anwendung von einer fehlenden Funktion abhängt, sollten Sie [ein Problem einreichen,](https://github.com/dotnet/runtime/issues/new) um herauszufinden, ob Unterstützung für Ihr Szenario hinzugefügt werden kann.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

Der größte Teil dieses Artikels <xref:System.Text.Json.JsonSerializer> behandelt die Verwendung der API, enthält <xref:System.Text.Json.JsonDocument> jedoch auch Anleitungen zur <xref:System.Text.Json.Utf8JsonReader>Verwendung <xref:System.Text.Json.Utf8JsonWriter> des Dokumentobjektmodells oder DOM s. und der Typen.

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>Tabelle der Unterschiede zwischen Newtonsoft.Json und System.Text.Json

In der `Newtonsoft.Json` folgenden `System.Text.Json` Tabelle sind Features und Entsprechungen aufgeführt. Die Äquivalente fallen in die folgenden Kategorien:

* Unterstützt durch integrierte Funktionalität. Für ähnliches `System.Text.Json` Verhalten kann die Verwendung eines Attributs oder einer globalen Option erforderlich sein.
* Nicht unterstützt, Eine Problemumgehung ist möglich. Bei den Problemumgehungen handelt es sich [um benutzerdefinierte Konverter](system-text-json-converters-how-to.md), die möglicherweise keine vollständige Parität mit `Newtonsoft.Json` der Funktionalität bieten. Für einige dieser Beispiele wird Beispielcode bereitgestellt. Wenn Sie sich `Newtonsoft.Json` auf diese Features verlassen, sind bei der Migration Änderungen an Ihren .NET-Objektmodellen oder andere Codeänderungen erforderlich.
* Nicht unterstützt, Problemumgehung ist nicht praktisch oder möglich. Wenn Sie sich `Newtonsoft.Json` auf diese Funktionen verlassen, ist eine Migration ohne wesentliche Änderungen nicht möglich.

| Newtonsoft.Json-Funktion                               | System.Text.Json-Äquivalent |
|-------------------------------------------------------|-----------------------------|
| Standardmäßig bei Nichtbeschriftenurn           | ✔️ [PropertyNameCaseInsensitive globale Einstellung](#case-insensitive-deserialization) |
| Camel-Case-Eigenschaftsnamen                             | ✔️ [globales PropertyNamingPolicy-Setting](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| Minimale Seisfigur entweicht                            | ✔️ [Strenges Zeichen entweichen, konfigurierbar](#minimal-character-escaping) |
| `NullValueHandling.Ignore`Globale Einstellung             | ✔️ [Die globale Option IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Kommentare zulassen                                        | ✔️ [globale ReadCommentHandling-Einstellung](#comments) |
| Nachfolgende Kommas zulassen                                 | ✔️ [AllowTrailingCommas globale Einstellung](#trailing-commas) |
| Benutzerdefinierte Konverterregistrierung                         | ✔️ [Rangfolge unterscheidet sich](#converter-registration-precedence) |
| Standardmäßig keine maximale Tiefe                           | ✔️ [Standard-Maximaltiefe 64, konfigurierbar](#maximum-depth) |
| Unterstützung für eine breite Palette von Typen                    | ⚠️[Einige Typen erfordern benutzerdefinierte Konverter](#types-without-built-in-support) |
| Deserialisieren von Zeichenfolgen als Zahlen                        | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#quoted-numbers) |
| Deserialisieren `Dictionary` mit Nicht-Zeichenfolgenschlüssel          | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#dictionary-with-non-string-key) |
| Polymorphe Serialisierung                             | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#polymorphic-serialization) |
| Polymorphe Deserialisierung                           | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#polymorphic-deserialization) |
| Deserialisieren des abgeleiteten `object` Typs zu Eigenschaften      | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#deserialization-of-object-properties) |
| Deserialisieren von `null` JSON-Literal ennicht-nullablen Werttypen | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#deserialize-null-to-non-nullable-type) |
| Deserialisieren auf unveränderliche Klassen und Strukturen          | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#deserialize-to-immutable-classes-and-structs) |
| `[JsonConstructor]`-Attribut                         | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#specify-constructor-to-use) |
| `Required`Einstellung `[JsonProperty]` für Attribut        | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#required-properties) |
| `NullValueHandling`Einstellung `[JsonProperty]` für Attribut | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`Einstellung `[JsonProperty]` für Attribut | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`Globale Einstellung                 | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property) |
| `DefaultContractResolver`Zum Ausschließen von Eigenschaften       | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` Einstellungen   | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#specify-date-format) |
| Rückrufe                                             | ⚠️[Nicht unterstützt, Problemumgehung, Beispiel](#callbacks) |
| Unterstützung öffentlicher und nichtöffentlicher Bereiche              | ⚠️[Nicht unterstützt, Problemumgehung](#public-and-non-public-fields) |
| Unterstützung für interne und private Immobiliensetzer und Getter | ⚠️[Nicht unterstützt, Problemumgehung](#internal-and-private-property-setters-and-getters) |
| `JsonConvert.PopulateObject`-Methode                   | ⚠️[Nicht unterstützt, Problemumgehung](#populate-existing-objects) |
| `ObjectCreationHandling`Globale Einstellung               | ⚠️[Nicht unterstützt, Problemumgehung](#reuse-rather-than-replace-properties) |
| Hinzufügen zu Sammlungen ohne Setter                    | ⚠️[Nicht unterstützt, Problemumgehung](#add-to-collections-without-setters) |
| `PreserveReferencesHandling`Globale Einstellung           | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling`Globale Einstellung                | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) |
| Unterstützung `System.Runtime.Serialization` für Attribute | ❌ [Nicht unterstützt](#systemruntimeserialization-attributes) |
| `MissingMemberHandling`Globale Einstellung                | ❌ [Nicht unterstützt](#missingmemberhandling) |
| Zulassen von Eigenschaftsnamen ohne Anführungszeichen                   | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) |
| Einfache Anführungszeichen um Zeichenfolgenwerte zulassen              | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) |
| Zulassen von JSON-Werten ohne Zeichenfolgen für Zeichenfolgeneigenschaften    | ❌ [Nicht unterstützt](#non-string-values-for-string-properties) |

Dies ist keine `Newtonsoft.Json` erschöpfende Liste von Funktionen. Die Liste enthält viele der Szenarien, die in [GitHub-Problemen](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) oder [StackOverflow-Beiträgen](https://stackoverflow.com/questions/tagged/system.text.json) angefordert wurden. Wenn Sie eine Problemumgehung für eines der hier aufgeführten Szenarien implementieren, das derzeit keinen Beispielcode enthält, und wenn Sie Ihre Projektmappe freigeben möchten, wählen Sie **Diese Seite** im Abschnitt **Feedback** unten auf dieser Seite aus. Dadurch wird ein Problem im GitHub-Repository dieser Dokumentation erstellt und im Abschnitt **Feedback** auf dieser Seite aufgelistet.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Unterschiede im standardmäßigen JsonSerializer-Verhalten im Vergleich zu Newtonsoft.Json

<xref:System.Text.Json>ist standardmäßig streng und vermeidet jegliches Raten oder Interpretieren im Namen des Aufrufers, wobei deterministisches Verhalten hervorgehoben wird. Die Bibliothek wurde absichtlich auf diese Weise für Leistung und Sicherheit konzipiert. `Newtonsoft.Json`ist standardmäßig flexibel. Dieser grundlegende Unterschied im Design steht hinter vielen der folgenden spezifischen Unterschiede im Standardverhalten.

### <a name="case-insensitive-deserialization"></a>Deserialisierung bei Fall-unempfindlichen Fällen

Während der Deserialisierung `Newtonsoft.Json` wird standardmäßig der Wert für den Ungültigsprechcharakter von Eigenschaftenunterstützten verwendet. Der <xref:System.Text.Json> Standardwert ist groß, da die Groß-/Kleinschreibung berücksichtigt wird, was eine bessere Leistung bietet, da sie eine exakte Übereinstimmung vornimmt. Informationen zum Anpassen von Groß-/Kleinschreibung finden Sie unter [Groß-/Kleinschreibungsübereinstimmung](system-text-json-how-to.md#case-insensitive-property-matching).

Wenn Sie indirekt ASP.NET Core verwenden, `System.Text.Json` müssen Sie nichts tun, um `Newtonsoft.Json`Verhalten wie zu erhalten. ASP.NET Core gibt die Einstellungen für [Camel-Casing-Eigenschaftsnamen](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) und `System.Text.Json`die Nichtübereinstimmung von Groß-/Kleinschreibung an, wenn sie verwendet.

### <a name="minimal-character-escaping"></a>Minimale Seisfigur entweicht

Während der `Newtonsoft.Json` Serialisierung ist relativ freizügig, wenn es darum geht, Charaktere durchzulassen, ohne ihnen zu entkommen. Das heißt, es ersetzt sie `\uxxxx` `xxxx` nicht mit dem Codepunkt des Zeichens. Wo es ihnen entkommt, tut es `\` dies, indem es `"` `\"`ein vor dem Zeichen aussendet (z. B. wird es ). <xref:System.Text.Json>Entgeht standardmäßig mehr Zeichen, um einen tiefen Verteidigungsschutz gegen Cross-Site Scripting (XSS) oder Information-Disclosure-Angriffe bereitzustellen, und zwar mithilfe der sechsstelligen Sequenz. `System.Text.Json`entgeht standardmäßig allen Nicht-ASCII-Zeichen, sodass Sie nichts tun müssen, `Newtonsoft.Json`wenn Sie in verwenden. `StringEscapeHandling.EscapeNonAscii` `System.Text.Json`Entgeht standardmäßig auch HTML-sensitiven Zeichen. Informationen zum Überschreiben des `System.Text.Json` Standardverhaltens finden Sie unter Anpassen der [Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Kommentare

`Newtonsoft.Json` Ignoriert während der Deserialisierung standardmäßig Kommentare in JSON. Standardmäßig <xref:System.Text.Json> werden Ausnahmen für Kommentare ausgelöst, da diese in der [RFC 8259-Spezifikation](https://tools.ietf.org/html/rfc8259) nicht enthalten sind. Informationen zum Zulassen von Kommentaren finden Sie unter Zulassen von [Kommentaren und nachgestellten Kommas](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Nachfolgende Kommas

`Newtonsoft.Json` Ignoriert während der Deserialisierung standardmäßig nachgestellte Kommas. Außerdem werden mehrere nachfolgende Kommas ignoriert `[{"Color":"Red"},{"Color":"Green"},,]`(z. B. ). Standardmäßig <xref:System.Text.Json> werden Ausnahmen für nachfolgende Kommas ausgelöst, da die [RFC 8259-Spezifikation](https://tools.ietf.org/html/rfc8259) sie nicht zulässt. Informationen zum `System.Text.Json` Akzeptieren dieser Informationen finden Sie unter Zulassen von [Kommentaren und nachgestellten Kommas](system-text-json-how-to.md#allow-comments-and-trailing-commas). Es gibt keine Möglichkeit, mehrere nachfolgende Kommas zuzulassen.

### <a name="converter-registration-precedence"></a>Konverterregistrierungspriorität

Die `Newtonsoft.Json` Registrierungspriorität für benutzerdefinierte Konverter ist wie folgt:

* Attribut auf Eigenschaft
* Attribut für Typ
* [Converter-Sammlung](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Diese Reihenfolge bedeutet, dass `Converters` ein benutzerdefinierter Konverter in der Auflistung von einem Konverter überschrieben wird, der durch Anwenden eines Attributs auf Typebene registriert wird. Beide Registrierungen werden durch ein Attribut auf Eigenschaftsebene überschrieben.

Die <xref:System.Text.Json> Registrierungspriorität für benutzerdefinierte Konverter ist anders:

* Attribut auf Eigenschaft
* <xref:System.Text.Json.JsonSerializerOptions.Converters>Auflistung
* Attribut für Typ

Der Unterschied besteht darin, dass `Converters` ein benutzerdefinierter Konverter in der Auflistung ein Attribut auf Typebene überschreibt. Die Absicht hinter dieser Rangfolge besteht darin, Laufzeitänderungen über Entwurfszeitentscheidungen hinwegzuschreiben. Es gibt keine Möglichkeit, die Rangfolge zu ändern.

Weitere Informationen zur benutzerdefinierten Konverterregistrierung finden Sie unter [Registrieren eines benutzerdefinierten Konverters](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Maximale Tiefe

`Newtonsoft.Json`hat standardmäßig keine maximale Tiefenbegrenzung. Denn <xref:System.Text.Json> es gibt ein Standardlimit von 64, und es <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>ist durch Festlegen von konfigurierbar.

### <a name="json-strings-property-names-and-string-values"></a>JSON-Zeichenfolgen (Eigenschaftsnamen und Zeichenfolgenwerte)

Akzeptiert während der `Newtonsoft.Json` Deserialisierung Eigenschaftsnamen, die von doppelten Anführungszeichen, einmaligen Anführungszeichen oder ohne Anführungszeichen umgeben sind. Es akzeptiert Zeichenfolgenwerte, die von doppelten oder einzelnen Anführungszeichen umgeben sind. `Newtonsoft.Json` Akzeptiert z. B. die folgende JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`akzeptiert eigenschaftsnamen und Zeichenfolgenwerte nur in doppelten Anführungszeichen, da dieses Format von der [RFC 8259-Spezifikation](https://tools.ietf.org/html/rfc8259) benötigt wird und das einzige Format ist, das als gültiges JSON betrachtet wird.

Ein in einfache Anführungszeichen eingeschlossener Wert führt zu einer [JsonException](xref:System.Text.Json.JsonException) mit der folgenden Meldung:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Nicht-Zeichenfolgenwerte für Zeichenfolgeneigenschaften

`Newtonsoft.Json`akzeptiert Nicht-Zeichenfolgenwerte, z. B. `true` `false`eine Zahl oder die Literale und , für die Deserialisierung in Eigenschaften des Typs string. Hier ist ein Beispiel für `Newtonsoft.Json` JSON, das erfolgreich auf die folgende Klasse deserialisiert:

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

`System.Text.Json`deserialisiert nicht zeichenfolgenWerte nicht in Zeichenfolgeneigenschaften. Ein nicht zeichenfolgen Wert, der für ein Zeichenfolgenfeld empfangen wird, führt zu einer [JsonException](xref:System.Text.Json.JsonException) mit der folgenden Meldung:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Szenarien mit JsonSerializer, die Problemumgehungen erfordern

Die folgenden Szenarien werden von der integrierten Funktionalität nicht unterstützt, aber Problemumgehungen sind möglich. Bei den Problemumgehungen handelt es sich [um benutzerdefinierte Konverter](system-text-json-converters-how-to.md), die möglicherweise keine vollständige Parität mit `Newtonsoft.Json` der Funktionalität bieten. Für einige dieser Beispiele wird Beispielcode bereitgestellt. Wenn Sie sich `Newtonsoft.Json` auf diese Features verlassen, sind bei der Migration Änderungen an Ihren .NET-Objektmodellen oder andere Codeänderungen erforderlich.

### <a name="types-without-built-in-support"></a>Typen ohne integrierte Unterstützung

<xref:System.Text.Json>bietet keine integrierte Unterstützung für die folgenden Typen:

* <xref:System.Data.DataTable>und verwandte Typen
* F-Typen, z. B. [diskriminierte Unions](../../fsharp/language-reference/discriminated-unions.md), [Datensatztypen](../../fsharp/language-reference/records.md)und [anonyme Datensatztypen](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple>und die zugehörigen generischen Typen

Benutzerdefinierte Konverter können für Typen implementiert werden, die nicht über integrierte Unterstützung verfügen.

### <a name="quoted-numbers"></a>Zitierte Zahlen

`Newtonsoft.Json`können Zahlen serialisieren oder deserialisieren, die durch JSON-Zeichenfolgen (von Anführungszeichen umgeben) dargestellt werden. Sie kann z. `{"DegreesCelsius":"23"}` B. `{"DegreesCelsius":23}`akzeptieren: anstelle von . Um dieses Verhalten <xref:System.Text.Json>in zu aktivieren, implementieren Sie einen benutzerdefinierten Konverter wie im folgenden Beispiel. Der Konverter verarbeitet Eigenschaften, die definiert sind wie: `long`

* Es serialisiert sie als JSON-Zeichenfolgen.
* Es akzeptiert JSON-Nummern und -Nummern innerhalb von Anführungszeichen während der Deserialisierung.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Registrieren Sie diesen benutzerdefinierten [Konverter,](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) indem Sie ein <xref:System.Text.Json.JsonSerializerOptions.Converters> Attribut für einzelne `long` Eigenschaften verwenden oder den Konverter zur Auflistung [hinzufügen.](system-text-json-converters-how-to.md#registration-sample---converters-collection)

### <a name="dictionary-with-non-string-key"></a>Wörterbuch mit Nicht-Zeichenfolgenschlüssel

`Newtonsoft.Json`unterstützt Sammlungen `Dictionary<TKey, TValue>`vom Typ . Die integrierte Unterstützung für Wörterbuchsammlungen <xref:System.Text.Json> in `Dictionary<string, TValue>`ist auf beschränkt. Das heißt, der Schlüssel muss eine Zeichenfolge sein.

Um ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel zu unterstützen, erstellen Sie einen Konverter wie das Beispiel unter [Schreiben benutzerdefinierter Konverter](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Polymorphe Serialisierung

`Newtonsoft.Json`automatisch polymorphe Serialisierung. Informationen zu den eingeschränkten polymorphen <xref:System.Text.Json>Serialisierungsfunktionen von finden Sie unter [Serialisieren von Eigenschaften abgeleiteter Klassen](system-text-json-how-to.md#serialize-properties-of-derived-classes).

Die dort beschriebene Problemumgehung besteht darin, Eigenschaften `object`zu definieren, die abgeleitete Klassen als Typ enthalten können. Wenn dies nicht möglich ist, besteht eine andere `Write` Option darin, einen Konverter mit einer Methode für die gesamte Vererbungstyphierarchie zu erstellen, wie das Beispiel unter [Schreiben benutzerdefinierter Konverter](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Polymorphe Deserialisierung

`Newtonsoft.Json`hat `TypeNameHandling` eine Einstellung, die dem JSON beim Serialisieren Typnamenmetadaten hinzufügt. Es verwendet die Metadaten während der Deserialisierung, um polymorphe Deserialisierung zu tun. <xref:System.Text.Json>kann einen begrenzten Bereich der [polymorphen Serialisierung,](system-text-json-how-to.md#serialize-properties-of-derived-classes) aber nicht die polymorphe Deserialisierung.

Um die polymorphe Deserialisierung zu unterstützen, erstellen Sie einen Konverter wie das Beispiel unter [Schreiben benutzerdefinierter Konverter](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserialisierung von Objekteigenschaften

Wenn `Newtonsoft.Json` deserialisiert <xref:System.Object>an, es:

* Leitet den Typ der primitiven Werte in der `null`JSON-Nutzlast (außer `string`) ab und gibt das gespeicherte , `long` `double`, `boolean`, oder `DateTime` als geschachteltes Objekt zurück. *Primitive Werte* sind einzelne JSON-Werte wie eine `true` `false`JSON-Zahl, Zeichenfolge, , oder `null`.
* Gibt `JObject` einen `JArray` oder für komplexe Werte in der JSON-Nutzlast zurück. *Komplexe Werte* sind Auflistungen von JSON-Schlüssel-Wert-Paaren innerhalb geschweifter Klammern (`{}`) oder Listen von Werten innerhalb von Klammern (`[]`). Die Eigenschaften und Werte innerhalb der geschweiften Klammern oder Klammern können zusätzliche Eigenschaften oder Werte aufweisen.
* Gibt einen Nullverweis zurück, `null` wenn die Nutzlast über das JSON-Literal verfügt.

<xref:System.Text.Json>speichert eine `JsonElement` Box für primitive und komplexe Werte, wenn die Deserialisierung an <xref:System.Object>z. B.

* Eine `object`-Eigenschaft.
* Ein `object` Wörterbuchwert.
* Ein `object` Arraywert.
* Eine `object`Wurzel .

`System.Text.Json` Behandelt jedoch `null` dasselbe `Newtonsoft.Json` wie und gibt einen Nullverweis `null` zurück, wenn die Nutzlast das JSON-Literal enthält.

Um Typrückschlüsse für `object` Eigenschaften zu implementieren, erstellen Sie einen Konverter wie das Beispiel unter [Schreiben benutzerdefinierter Konverter](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserialisieren von NULL in nicht NULL-typ

`Newtonsoft.Json`löst im folgenden Szenario keine Ausnahme aus:

* `NullValueHandling`ist auf `Ignore`gesetzt, und
* Während der Deserialisierung enthält der JSON einen NULL-Wert für einen nicht nullierbaren Werttyp.

Löst im gleichen <xref:System.Text.Json> Szenario eine Ausnahme aus. (Die entsprechende Null-Handling-Einstellung ist <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)

Wenn Sie den Zieltyp besitzen, besteht die beste Problemumgehung darin, die `int` `int?`betreffende Eigenschaft nullierbar zu machen (z. B. ändern Sie in ).

Eine weitere Problemumgehung besteht darin, einen Konverter für den Typ zu `DateTimeOffset` erstellen, z. B. das folgende Beispiel, das NULL-Werte für Typen verarbeitet:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registrieren Sie diesen benutzerdefinierten [Konverter,](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) indem Sie ein <xref:System.Text.Json.JsonSerializerOptions.Converters> Attribut für die Eigenschaft verwenden oder den Konverter zur Auflistung [hinzufügen.](system-text-json-converters-how-to.md#registration-sample---converters-collection)

**Hinweis:** Der vorherige Konverter **behandelt NULL-Werte anders** als `Newtonsoft.Json` bei POCOs, die Standardwerte angeben. Angenommen, der folgende Code stellt ihr Zielobjekt dar:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Angenommen, das folgende JSON wird mithilfe des vorherigen Konverters deserialisiert:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Nach der Deserialisierung hat die `Date` Eigenschaft 1/1/0001 (`default(DateTimeOffset)`), d. h., der im Konstruktor festgelegte Wert wird überschrieben. Bei gleichen POCO und `Newtonsoft.Json` JSON würde die Deserialisierung 1/1/2001 in der `Date` Eigenschaft belassen.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserialisieren auf unveränderliche Klassen und Strukturen

`Newtonsoft.Json`kann zu unveränderlichen Klassen und Strukturen deserialisiert werden, da Konstruktoren mit Parametern verwendet werden können. <xref:System.Text.Json>unterstützt nur öffentliche parameterlose Konstruktoren. Als Problemumgehung können Sie einen Konstruktor mit Parametern in einem benutzerdefinierten Konverter aufrufen.

Hier ist eine unveränderliche Struktur mit mehreren Konstruktorparametern:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

Und hier ist ein Konverter, der diese Struktur serialisiert und deserialisiert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter, indem Sie den Konverter zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung [hinzufügen.](system-text-json-converters-how-to.md#registration-sample---converters-collection)

Ein Beispiel für einen ähnlichen Konverter, der offene generische Eigenschaften verarbeitet, finden Sie im [integrierten Konverter für Schlüssel-Wert-Paare](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Angeben des zu verwendenden Konstruktors

Mit `Newtonsoft.Json` `[JsonConstructor]` dem Attribut können Sie angeben, welcher Konstruktor beim Deserialisieren in eine POCO aufzurufen ist. <xref:System.Text.Json>unterstützt nur parameterlose Konstruktoren. Als Problemumgehung können Sie den Konstruktor aufrufen, den Sie in einem benutzerdefinierten Konverter benötigen. Siehe Beispiel für [Deserialisieren auf unveränderliche Klassen und Strukturen](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Erforderliche Eigenschaften

In `Newtonsoft.Json`geben Sie an, dass `Required` eine `[JsonProperty]` Eigenschaft erforderlich ist, indem Sie das Attribut festlegen. `Newtonsoft.Json`löst eine Ausnahme aus, wenn im JSON kein Wert für eine als erforderlich markierte Eigenschaft empfangen wird.

<xref:System.Text.Json>löst keine Ausnahme aus, wenn kein Wert für eine der Eigenschaften des Zieltyps empfangen wird. Wenn Sie z. `WeatherForecast` B. über eine Klasse verfügen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Das folgende JSON wird fehlerfrei deserialisiert:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Um die Deserialisierung `Date` fehlschlagen zu lassen, wenn sich keine Eigenschaft im JSON befindet, implementieren Sie einen benutzerdefinierten Konverter. Der folgende Beispielkonvertercode löst `Date` eine Ausnahme aus, wenn die Eigenschaft nach Abschluss der Deserialisierung nicht festgelegt ist:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registrieren Sie diesen benutzerdefinierten Konverter, indem [Sie ein Attribut für die POCO-Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) verwenden oder den Konverter zur <xref:System.Text.Json.JsonSerializerOptions.Converters> Auflistung [hinzufügen.](system-text-json-converters-how-to.md#registration-sample---converters-collection)

Wenn Sie diesem Muster folgen, übergeben Sie das Optionsobjekt nicht, wenn Sie rekursiv aufrufen <xref:System.Text.Json.JsonSerializer.Serialize%2A> oder <xref:System.Text.Json.JsonSerializer.Deserialize%2A>aufrufen. Das Optionsobjekt <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> enthält die Auflistung. Wenn Sie es `Serialize` an `Deserialize`oder übergeben, ruft der benutzerdefinierte Konverter in sich selbst auf, wodurch eine Endlosschleife entsteht, die zu einer Stack-Overflow-Ausnahme führt. Wenn die Standardoptionen nicht möglich sind, erstellen Sie eine neue Instanz der Optionen mit den gewünschten Einstellungen. Dieser Ansatz ist langsam, da jede neue Instanz unabhängig zwischengespeichert wird.

Der vorangehende Konvertercode ist ein vereinfachtes Beispiel. Zusätzliche Logik wäre erforderlich, wenn Sie Attribute (z. B. [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) oder verschiedene Optionen (z. B. benutzerdefinierte Encoder) verarbeiten müssen. Außerdem behandelt der Beispielcode keine Eigenschaften, für die ein Standardwert im Konstruktor festgelegt ist. Und dieser Ansatz unterscheidet nicht zwischen den folgenden Szenarien:

* Im JSON fehlt eine Eigenschaft.
* Eine Eigenschaft für einen nicht NULL-fähigen Typ ist im JSON vorhanden, aber der Wert `int`ist der Standardwert für den Typ, z. B. Null für eine .
* Eine Eigenschaft für einen nullablen Werttyp ist im JSON vorhanden, aber der Wert ist null.

### <a name="conditionally-ignore-a-property"></a>Bedingtes Ignorieren einer Eigenschaft

`Newtonsoft.Json`hat mehrere Möglichkeiten, eine Eigenschaft bei Serialisierung oder Deserialisierung bedingt zu ignorieren:

* `DefaultContractResolver`können Sie Eigenschaften auswählen, die eingeschlossen oder ausgeschlossen werden sollen, basierend auf beliebigen Kriterien.
* Mit `NullValueHandling` `DefaultValueHandling` den `JsonSerializerSettings` Einstellungen können Sie angeben, dass alle Nullwert- oder Standardwerteigenschaften ignoriert werden sollen.
* Mit `NullValueHandling` `DefaultValueHandling` den Einstellungen `[JsonProperty]` für das Attribut können Sie einzelne Eigenschaften angeben, die ignoriert werden sollen, wenn sie auf null oder den Standardwert festgelegt sind.

<xref:System.Text.Json>bietet die folgenden Möglichkeiten zum Weglassen von Eigenschaften beim Serialisieren:

* Das [[JsonIgnore]-Attribut](system-text-json-how-to.md#exclude-individual-properties) für eine Eigenschaft bewirkt, dass die Eigenschaft während der Serialisierung aus dem JSON weggelassen wird.
* Mit der globalen Option [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) können Sie alle Nullwerteigenschaften ausschließen.
* Mit der globalen Option [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) können Sie alle schreibgeschützten Eigenschaften ausschließen.

Diese Optionen lassen Sie **nicht:**

* Ignorieren Sie alle Eigenschaften, die den Standardwert für den Typ aufweisen.
* Ausgewählte Eigenschaften ignorieren, die den Standardwert für den Typ aufweisen.
* Ausgewählte Eigenschaften ignorieren, wenn ihr Wert null ist.
* Ausgewählte Eigenschaften basierend auf beliebigen Kriterien ignorieren, die zur Laufzeit ausgewertet werden.

Für diese Funktionalität können Sie einen benutzerdefinierten Konverter schreiben. Hier ist ein Beispiel POCO und ein benutzerdefinierter Konverter dafür, der diesen Ansatz veranschaulicht:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Der Konverter `Summary` bewirkt, dass die Eigenschaft bei der Serialisierung weggelassen wird, wenn ihr Wert null, eine leere Zeichenfolge oder "N/A" ist.

Registrieren Sie diesen benutzerdefinierten [Konverter,](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) indem Sie ein <xref:System.Text.Json.JsonSerializerOptions.Converters> Attribut für die Klasse verwenden oder den Konverter zur Auflistung [hinzufügen.](system-text-json-converters-how-to.md#registration-sample---converters-collection)

Dieser Ansatz erfordert zusätzliche Logik, wenn:

* Der POCO umfasst komplexe Eigenschaften.
* Sie müssen Attribute wie `[JsonIgnore]` oder Optionen wie benutzerdefinierte Encoder behandeln.

### <a name="specify-date-format"></a>Datumsformat angeben

`Newtonsoft.Json`bietet mehrere Möglichkeiten, um `DateTime` `DateTimeOffset` zu steuern, wie Eigenschaften und Typen serialisiert und deserialisiert werden:

* Die `DateTimeZoneHandling` Einstellung kann verwendet werden, um alle `DateTime` Werte als UTC-Datum zu serialisieren.
* Die `DateFormatString` Einstellung `DateTime` und die Konverter können verwendet werden, um das Format von Datumszeichenfolgen anzupassen.

In <xref:System.Text.Json>ist das einzige Format, das über integrierte Unterstützung verfügt, ISO 8601-1:2019, da es weit verbreitet, eindeutig ist und Rundreisen präzise macht. Um ein anderes Format zu verwenden, erstellen Sie einen benutzerdefinierten Konverter. Weitere Informationen finden Sie unter [DateTime- und DateTimeOffset-Unterstützung in System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Rückrufe

`Newtonsoft.Json`können Sie benutzerdefinierten Code an mehreren Punkten im Serialisierungs- oder Deserialisierungsprozess ausführen:

* OnDeserializing (wenn mit der Deserialisierung eines Objekts begonnen wird)
* OnDeserialized (wenn die Deserialisierung eines Objekts abgeschlossen ist)
* OnSerializing (wenn sie mit der Serialisierung eines Objekts beginnen)
* OnSerialized (wenn die Serialisierung eines Objekts abgeschlossen ist)

In <xref:System.Text.Json>können Sie Rückrufe simulieren, indem Sie einen benutzerdefinierten Konverter schreiben. Das folgende Beispiel zeigt einen benutzerdefinierten Konverter für einen POCO. Der Konverter enthält Code, der an jedem `Newtonsoft.Json` Punkt eine Meldung anzeigt, die einem Rückruf entspricht.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Registrieren Sie diesen benutzerdefinierten [Konverter,](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) indem Sie ein <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters> Attribut für die Klasse verwenden oder den Konverter zur Auflistung [hinzufügen.](system-text-json-converters-how-to.md#registration-sample---converters-collection)

Wenn Sie einen benutzerdefinierten Konverter verwenden, der auf das vorangegangene Beispiel folgt:

* Der `OnDeserializing` Code hat keinen Zugriff auf die neue POCO-Instanz. Um die neue POCO-Instanz zu Beginn der Deserialisierung zu bearbeiten, legen Sie diesen Code in den POCO-Konstruktor.
* Übergeben Sie das Optionsobjekt nicht, wenn Rekursiv aufgerufen `Serialize` oder `Deserialize`aufgerufen wird. Das Optionsobjekt `Converters` enthält die Auflistung. Wenn Sie es `Serialize` an `Deserialize`oder übergeben, wird der Konverter verwendet, wodurch eine Endlosschleife verwendet wird, die zu einer Stack-Overflow-Ausnahme führt.

### <a name="public-and-non-public-fields"></a>Öffentliche und nicht-öffentliche Bereiche

`Newtonsoft.Json`können Felder sowie Eigenschaften serialisieren und deserialisieren. <xref:System.Text.Json>funktioniert nur mit öffentlichen Liegenschaften. Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.

### <a name="internal-and-private-property-setters-and-getters"></a>Interne und private Immobiliensetzer und Getter

`Newtonsoft.Json`können private und interne Eigenschaftssetter `JsonProperty` und Getter über das Attribut verwenden. <xref:System.Text.Json>unterstützt nur öffentliche Setter. Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.

### <a name="populate-existing-objects"></a>Vorhandene Objekte füllen

Die `JsonConvert.PopulateObject` Methode `Newtonsoft.Json` beim Deserialisieren eines JSON-Dokuments an eine vorhandene Instanz einer Klasse, anstatt eine neue Instanz zu erstellen. <xref:System.Text.Json>erstellt immer eine neue Instanz des Zieltyps mithilfe des standardmäßigen öffentlichen parameterlosen Konstruktors. Benutzerdefinierte Konverter können auf eine vorhandene Instanz deserialisiert werden.

### <a name="reuse-rather-than-replace-properties"></a>Wiederverwenden statt Ersetzen von Eigenschaften

Mit `Newtonsoft.Json` `ObjectCreationHandling` der Einstellung können Sie festlegen, dass Objekte in Eigenschaften während der Deserialisierung wiederverwendet und nicht ersetzt werden sollen. <xref:System.Text.Json>ersetzt immer Objekte in Eigenschaften.  Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.

### <a name="add-to-collections-without-setters"></a>Hinzufügen zu Sammlungen ohne Setter

Fügt während der `Newtonsoft.Json` Deserialisierung Einer Auflistung Objekte hinzu, auch wenn die Eigenschaft keinen Setter hat. <xref:System.Text.Json>ignoriert Eigenschaften, die nicht über Setter verfügen. Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Szenarien, die JsonSerializer derzeit nicht unterstützt

Für die folgenden Szenarien sind Problemumgehungen nicht praktikabel oder möglich. Wenn Sie sich `Newtonsoft.Json` auf diese Funktionen verlassen, ist eine Migration ohne wesentliche Änderungen nicht möglich.

### <a name="preserve-object-references-and-handle-loops"></a>Beibehalten von Objektverweisen und Handleschleifen

Serialisiert `Newtonsoft.Json` standardmäßig nach Wert. Wenn ein Objekt beispielsweise zwei Eigenschaften enthält, die `Person` einen Verweis auf `Person` dasselbe Objekt enthalten, werden die Werte der Eigenschaften dieses Objekts im JSON dupliziert.

`Newtonsoft.Json`hat `PreserveReferencesHandling` eine `JsonSerializerSettings` Einstellung, mit der Sie als Verweis serialisieren können:

* Dem JSON, das für das erste `Person` Objekt erstellt wurde, werden Bezeichnermetadaten hinzugefügt.
* Das JSON, das für `Person` das zweite Objekt erstellt wird, enthält einen Verweis auf diesen Bezeichner anstelle von Eigenschaftswerten.

`Newtonsoft.Json`außerdem verfügt `ReferenceLoopHandling` sie über eine Einstellung, mit der Sie Zirkelverweise ignorieren können, anstatt eine Ausnahme auszulösen.

<xref:System.Text.Json>unterstützt nur die Serialisierung nach Wert und löst eine Ausnahme für Zirkelverweise aus.

### <a name="systemruntimeserialization-attributes"></a>System.Runtime.Serialization-Attribute

<xref:System.Text.Json>unterstützt keine Attribute aus `System.Runtime.Serialization` dem Namespace, `DataMemberAttribute` `IgnoreDataMemberAttribute`z. B. und .

### <a name="octal-numbers"></a>Oktalzahlen

`Newtonsoft.Json`behandelt Zahlen mit einer führenden Null als Oktalzahlen. <xref:System.Text.Json>lässt keine führenden Nullen zu, da die [RFC 8259-Spezifikation](https://tools.ietf.org/html/rfc8259) sie nicht zulässt.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json`kann so konfiguriert werden, dass während der Deserialisierung Ausnahmen ausgelöst werden, wenn jsON Eigenschaften enthält, die im Zieltyp fehlen. <xref:System.Text.Json>ignoriert zusätzliche Eigenschaften im JSON, es sei denn, Sie verwenden das [Attribut [JsonExtensionData].](system-text-json-how-to.md#handle-overflow-json) Es gibt keine Problemumgehung für das fehlende Elementfeature.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json`können Sie debuggen, indem Sie eine `TraceWriter` verwenden, um Protokolle anzuzeigen, die durch Serialisierung oder Deserialisierung generiert werden. <xref:System.Text.Json>Protokollierung.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument und JsonElement im Vergleich zu JToken (wie JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>bietet die Möglichkeit, ein **schreibgeschütztes** Dokumentobjektmodell (DOM) aus vorhandenen JSON-Nutzlasten zu analysieren und zu erstellen. Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich <xref:System.Text.Json.JsonElement> die Nutzlast besteht, kann über den Typ zugegriffen werden. Der `JsonElement` Typ stellt APIs zum Konvertieren von JSON-Text in allgemeine .NET-Typen bereit. `JsonDocument`macht eine <xref:System.Text.Json.JsonDocument.RootElement> Eigenschaft aus.

### <a name="jsondocument-is-idisposable"></a>JsonDocument ist IDisposable

`JsonDocument`erstellt eine Speicheransicht der Daten in einem gepoolten Puffer. Daher wird `JObject` `JArray` der `Newtonsoft.Json` `JsonDocument` Typ im `IDisposable` Gegensatz oder von implementiert und muss innerhalb eines Verwendungsblocks verwendet werden.

Geben Sie `JsonDocument` eine von Ihrer API nur zurück, wenn Sie lebenslanges Eigentum übertragen und die Verantwortung an den Aufrufer übertragen möchten. In den meisten Szenarien ist dies nicht erforderlich. Wenn der Aufrufer mit dem gesamten JSON-Dokument <xref:System.Text.Json.JsonDocument.RootElement%2A>arbeiten muss, <xref:System.Text.Json.JsonElement>geben Sie die <xref:System.Text.Json.JsonElement.Clone%2A> der zurück, die eine ist. Wenn der Aufrufer mit einem bestimmten Element im JSON-Dokument arbeiten muss, geben Sie die <xref:System.Text.Json.JsonElement.Clone%2A> von <xref:System.Text.Json.JsonElement>zurück. Wenn Sie `RootElement` das oder ein Unterelement `Clone`direkt zurückgeben, ohne eine zu erstellen, `JsonElement` kann `JsonDocument` der Aufrufer nicht auf die zurückgegebene zugreifen, nachdem das zurückgegebene Element, das er besitzt, verworfen wurde.

Hier ist ein Beispiel, das `Clone`erfordert, dass Sie eine:

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

Der vorhergehende `JsonElement` Code `fileName` erwartet eine, die eine Eigenschaft enthält. Es öffnet die JSON-Datei und erstellt eine `JsonDocument`. Die Methode geht davon aus, dass der Aufrufer mit `Clone` dem `RootElement`gesamten Dokument arbeiten möchte.

Wenn Sie `JsonElement` ein Unterelement erhalten und ein Unterelement zurückgeben, `Clone` ist es nicht erforderlich, ein Teilelement zurückzugeben. Der Anrufer ist dafür `JsonDocument` verantwortlich, das, `JsonElement` zu dem der Übergebene gehört, am Leben zu erhalten. Beispiel:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument ist schreibgeschützt

Das <xref:System.Text.Json> DOM kann JSON-Elemente nicht hinzufügen, entfernen oder ändern. Es wurde auf diese Weise für die Leistung entwickelt und um Zuweisungen für die Analyse gängiger JSON-Nutzlastgrößen (d. h. < 1 MB) zu reduzieren. Wenn Ihr Szenario derzeit ein veränderbares DOM verwendet, ist eine der folgenden Problemumgehungen möglicherweise möglich:

* Um eine `JsonDocument` von Grund auf neu zu erstellen (d. `Parse` h., ohne eine vorhandene `Utf8JsonWriter` JSON-Nutzlast an die `JsonDocument`Methode zu übergeben), schreiben Sie den JSON-Text, indem Sie die ausgabe verwenden und analysieren, um eine neue zu erstellen.
* Um einen `JsonDocument`vorhandenen zu ändern, verwenden Sie ihn, um JSON-Text zu schreiben, `JsonDocument`während Sie schreiben, Änderungen vorzunehmen und die Ausgabe daraus zu analysieren, um eine neue zu erstellen.
* Informationen zum Zusammenführen vorhandener `JObject.Merge` JSON-Dokumente, die den oder `JContainer.Merge` APIs aus `Newtonsoft.Json`entsprechen, finden Sie in diesem [GitHub-Problem](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>JsonElement ist eine Union-Struktur

`JsonDocument`macht die `RootElement` als Eigenschaft <xref:System.Text.Json.JsonElement>des Typs aus, bei der es sich um einen Union-Strukturtyp handelt, der jedes JSON-Element umfasst. `Newtonsoft.Json`verwendet dedizierte hierarchische `JObject``JArray`Typen `JToken`wie , , usw. `JsonElement`ist das, was Sie suchen und aufzählen `JsonElement` können, und Sie können JSON-Elemente in .NET-Typen materialisieren.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>So suchen Sie ein JsonDocument und JsonElement nach Unterelementen

Sucht nach JSON-Token, `JArray` `Newtonsoft.Json` die JSON-Token verwenden `JObject` oder von in der Regel relativ schnell sind, da es sich um Suchvorgänge in einem Wörterbuch handelt. Im Vergleich dazu `JsonElement` erfordern Suchvorgänge eine sequenzielle Suche der Eigenschaften `TryGetProperty`und sind daher relativ langsam (z. B. bei Verwendung ). <xref:System.Text.Json>wurde entwickelt, um die anfängliche Analysezeit anstelle der Suchzeit zu minimieren. Verwenden Sie daher die folgenden Ansätze, `JsonDocument` um die Leistung beim Durchsuchen eines Objekts zu optimieren:

* Verwenden Sie die integrierten Enumeratoren (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> und <xref:System.Text.Json.JsonElement.EnumerateObject%2A>), anstatt Eigene Indizierungen oder Schleifen zu verwenden.
* Machen Sie keine sequenzielle `JsonDocument` Suche im Ganzen `RootElement`durch jede Eigenschaft, indem Sie . Suchen Sie stattdessen nach verschachtelten JSON-Objekten basierend auf der bekannten Struktur der JSON-Daten. Wenn Sie z. B. `Grade` nach `Student` einer Eigenschaft in `Student` Objekten suchen, `Grade` durchlaufen Sie die Objekte, `JsonElement` und `Grade` erhalten Sie den Wert von für jedes Objekt, anstatt alle Objekte zu durchsuchen, die nach Eigenschaften suchen. Letzteres führt zu unnötigen Weitergaben derselben Daten.

Ein Codebeispiel finden Sie unter [Verwenden von JsonDocument für den Zugriff auf Daten](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader im Vergleich zu JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>ist ein leistungsstarker, nur für den Vorausvernorlegungsleser für UTF-8 codierten JSON-Text, der von einem [ReadOnlySpan-Byte\<>](xref:System.ReadOnlySpan%601) oder [ReadOnlySequence-Byte\<>](xref:System.Buffers.ReadOnlySequence%601)gelesen wird. Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierern verwendet werden kann.

In den folgenden Abschnitten werden `Utf8JsonReader`empfohlene Programmiermuster für die Verwendung von erläutert.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader ist eine

Da `Utf8JsonReader` es sich bei dem Typ um eine *ref-Struktur*handelt, hat er [bestimmte Einschränkungen](../../csharp/language-reference/builtin-types/struct.md#ref-struct). Beispielsweise kann es nicht als Feld für eine andere Klasse oder Struktur als eine Ref-Struktur gespeichert werden. Um eine hohe Leistung zu `ref struct` erzielen, muss dieser Typ ein sein, da er das [Eingabe-ReadOnlySpan-Byte\<>](xref:System.ReadOnlySpan%601)zwischenspeichern muss, das selbst eine Ref-Struktur ist. Darüber hinaus ist dieser Typ veränderbar, da er den Status enthält. Übergeben **Sie es** daher durch ref und nicht nach Wert. Das Übergeben nach Wert würde zu einer Strukturkopie führen, und die Statusänderungen wären für den Aufrufer nicht sichtbar. Dies unterscheidet `Newtonsoft.Json` sich `Newtonsoft.Json` `JsonTextReader` von da, da die eine Klasse ist. Weitere Informationen zur Verwendung von Verweisstrukturen finden Sie unter [Schreiben von sicherem und effizientem C-Code](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>UTF-8-Text lesen

Um die bestmögliche Leistung bei `Utf8JsonReader`der Verwendung der zu erzielen, lesen Sie JSON-Nutzlasten, die bereits als UTF-8-Text und nicht als UTF-16-Zeichenfolgen codiert sind. Ein Codebeispiel finden Sie unter [Filtern von Daten mit Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Lesen mit einem Stream oder PipeReader

Die `Utf8JsonReader` unterstützt das Lesen von einem UTF-8 codierten [ReadOnlySpan-Byte\<>](xref:System.ReadOnlySpan%601) oder [ReadOnlySequence-Byte\<>](xref:System.Buffers.ReadOnlySequence%601) (was das Ergebnis des Lesens aus einem <xref:System.IO.Pipelines.PipeReader>ist).

Zum synchronen Lesen können Sie die JSON-Nutzlast bis zum Ende des Streams in ein Bytearray lesen und diese an den Reader übergeben. Rufen Sie zum Lesen aus einer Zeichenfolge (die als <xref:System.Text.Encoding.UTF8>UTF-16 codiert ist) auf.<xref:System.Text.Encoding.GetBytes%2A> , um die Zeichenfolge zunächst in ein UTF-8-codiertes Byte-Array zu transkodieren. Dann übergeben Sie `Utf8JsonReader`das an die .

Da `Utf8JsonReader` der die Eingabe als JSON-Text betrachtet, wird ein UTF-8-Byte-Auftragszeichen (BOM) als ungültiges JSON betrachtet. Der Aufrufer muss dies herausfiltern, bevor er die Daten an den Leser weitergibt.

Codebeispiele finden Sie unter [Verwenden von Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Lesen mit Multi-Segment ReadOnlySequence

Wenn es sich bei Ihrer JSON-Eingabe um ein [ReadOnlySpan-Byte\<>](xref:System.ReadOnlySpan%601)handelt, kann auf jedes JSON-Element von der `ValueSpan` Eigenschaft auf dem Reader zugegriffen werden, während Sie die Leseschleife durchlaufen. Wenn es sich bei Ihrer Eingabe jedoch um ein [ReadOnlySequence-Byte\<>](xref:System.Buffers.ReadOnlySequence%601) handelt (was das Ergebnis `ReadOnlySequence<byte>` des Lesens aus einem <xref:System.IO.Pipelines.PipeReader>ist), können einige JSON-Elemente mehrere Segmente des Objekts überspannen. Auf diese Elemente kann <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in einem zusammenhängenden Speicherblock nicht zugegriffen werden. Wenn Sie stattdessen ein Multisegment `ReadOnlySequence<byte>` als Eingabe <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> haben, rufen Sie die Eigenschaft auf dem Reader ab, um herauszufinden, wie Sie auf das aktuelle JSON-Element zugreifen. Hier ist ein empfohlenes Muster:

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

### <a name="use-valuetextequals-for-property-name-lookups"></a>Verwenden von ValueTextEquals für Eigenschaftennamensuche

Verwenden Sie <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> nicht, um Byte-für-Byte-Vergleiche zu führen, indem Sie nach Eigenschaftennamensuchen aufrufen. <xref:System.MemoryExtensions.SequenceEqual%2A> Rufen <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> Sie stattdessen auf, da diese Methode alle Zeichen aufweicht, die im JSON mit Escapezeichen versehen werden. Hier ist ein Beispiel, das zeigt, wie nach einer Eigenschaft mit dem Namen "Name" gesucht wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Nullwerte in NULL-Werttypen lesen

`Newtonsoft.Json`stellt APIs <xref:System.Nullable%601>bereit, `ReadAsBoolean`die zurückgeben , `Null` `TokenType` z. B. , die eine für Sie verarbeitet, indem eine `bool?`zurückgegeben wird. Die integrierten `System.Text.Json` APIs geben nur nicht NULL-werttypen zurück. <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> Gibt z. `bool`B. eine zurück. Es löst eine Ausnahme `Null` aus, wenn es in der JSON gefunden wird. Die folgenden Beispiele zeigen zwei Möglichkeiten zum Behandeln von NULL-Werten, eine durch Zurückgeben eines nullablen Werttyps und eine durch Zurückgeben des Standardwerts:

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

Wenn Sie weiterhin für `Newtonsoft.Json` bestimmte Zielframeworks verwenden müssen, können Sie mehrere Ziele verwenden und über zwei Implementierungen verfügen. Dies ist jedoch nicht trivial `#ifdefs` und würde einige und Quellenduplizierung erfordern. Eine Möglichkeit, so viel Code wie `ref struct` möglich zu `Utf8JsonReader` `Newtonsoft.Json` `JsonTextReader`teilen, besteht darin, einen Wrapper um und zu erstellen. Dieser Wrapper würde die öffentliche Fläche vereinigen und gleichzeitig die Verhaltensunterschiede isolieren. Auf diese Weise können Sie die Änderungen hauptsächlich an der Konstruktion des Typs isolieren, zusammen mit dem Übergeben des neuen Typs durch Verweis. Dies ist das Muster, nach dem die [Microsoft.Extensions.DependencyModel-Bibliothek](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) folgt:

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter im Vergleich zu JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>ist eine leistungsstarke Möglichkeit zum Schreiben von UTF-8-codiertem JSON-Text aus allgemeinen .NET-Typen wie `String`, `Int32`und `DateTime`. Der Writer ist ein Low-Level-Typ, der zum Erstellen benutzerdefinierter Serialisierungsmittel verwendet werden kann.

In den folgenden Abschnitten werden `Utf8JsonWriter`empfohlene Programmiermuster für die Verwendung von erläutert.

### <a name="write-with-utf-8-text"></a>Schreiben mit UTF-8 Text

Um die bestmögliche Leistung bei `Utf8JsonWriter`verwendung der zu erzielen, schreiben Sie JSON-Nutzlasten, die bereits als UTF-8-Text und nicht als UTF-16-Zeichenfolgen codiert sind. Verwenden <xref:System.Text.Json.JsonEncodedText> Sie diese, um bekannte Zeichenfolgeneigenschaftsnamen und -werte als Statik zwischenzuspeichern und vorzucodieren, und übergeben Sie diese an den Writer, anstatt UTF-16-Zeichenfolgenliterale zu verwenden. Dies ist schneller als das Zwischenspeichern und verwenden von UTF-8-Byte-Arrays.

Dieser Ansatz funktioniert auch, wenn Sie benutzerdefinierte Flucht zu tun. `System.Text.Json`lässt es Sie nicht, das Entweichen beim Schreiben einer Zeichenfolge zu deaktivieren. Sie können jedoch Ihre eigene <xref:System.Text.Encodings.Web.JavaScriptEncoder> benutzerdefinierte Als Option an den `JsonEncodedText` Writer `JavascriptEncoder` übergeben oder Eine eigene erstellen, `JsonEncodedText` die Ihre verwendet, um die Flucht zu tun, und dann die anstelle der Zeichenfolge schreiben. Weitere Informationen finden Sie unter Anpassen der [Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Rohwerte schreiben

Die `Newtonsoft.Json` `WriteRawValue` Methode schreibt unformatiertes JSON, wobei ein Wert erwartet wird. <xref:System.Text.Json>hat keine direkte Entsprechung, aber hier ist eine Problemumgehung, die sicherstellt, dass nur gültige SJSON geschrieben wird:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Anpassen der Zeichenflucht

Die [StringEscapeHandling-Einstellung](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) bietet `JsonTextWriter` Optionen zum Escapeen aller Nicht-ASCII-Zeichen **oder** HTML-Zeichen. Escapet `Utf8JsonWriter` standardmäßig alle Nicht-ASCII- **und** HTML-Zeichen. Diese Flucht erfolgt aus Gründen der tiefen Verteidigungssicherheit. Um eine andere Fluchtrichtlinie anzugeben, <xref:System.Text.Encodings.Web.JavaScriptEncoder> erstellen <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>Sie eine , und legen Sie fest. Weitere Informationen finden Sie unter Anpassen der [Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Anpassen des JSON-Formats

`JsonTextWriter`enthält die folgenden Einstellungen, für die `Utf8JsonWriter` es keine Entsprechung gibt:

* [Einzug](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Gibt an, wie viele Zeichen einrücken sollen. `Utf8JsonWriter`macht immer einen 2-stelligen Einzug.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Gibt das Zeichen an, das für den Einzug verwendet werden soll.  `Utf8JsonWriter`verwendet immer Leerzeichen.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Gibt das Zeichen an, das zum Umgeben von Zeichenfolgenwerten verwendet werden soll.  `Utf8JsonWriter`verwendet immer doppelte Anführungszeichen.
* [QuotesName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Gibt an, ob Eigenschaftsnamen mit Anführungszeichen umgeben werden sollen.  `Utf8JsonWriter`umgibt sie immer mit Anführungszeichen.

Es gibt keine Problemumgehungen, mit denen Sie `Utf8JsonWriter` die JSON auf diese Weise anpassen können.

### <a name="write-null-values"></a>Nullwerte schreiben

Um NULL-Werte `Utf8JsonWriter`mithilfe von zu schreiben:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>, um ein Schlüssel-Wert-Paar mit null als Wert zu schreiben.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>, um null als Element eines JSON-Arrays zu schreiben.

Wenn die Zeichenfolge für eine Zeichenfolgeneigenschaft null `WriteNull` `WriteNullValue`ist <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> und <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> mit und .

### <a name="write-timespan-uri-or-char-values"></a>Schreiben von Zeitspannen-, Uri- oder Zeichenwerten

`JsonTextWriter`bietet `WriteValue` Methoden für [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)-, [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)- und [char-Werte.](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) `Utf8JsonWriter`hat keine gleichwertigen Methoden. Formatieren Sie diese Werte stattdessen `ToString()`als Zeichenfolgen <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>(z. B. durch Aufrufen) und rufen Sie auf.

### <a name="multi-targeting"></a>Festlegung von Zielversionen

Wenn Sie weiterhin für `Newtonsoft.Json` bestimmte Zielframeworks verwenden müssen, können Sie mehrere Ziele verwenden und über zwei Implementierungen verfügen. Dies ist jedoch nicht trivial `#ifdefs` und würde einige und Quellenduplizierung erfordern. Eine Möglichkeit, so viel Code wie möglich zu `Utf8JsonWriter` `Newtonsoft` `JsonTextWriter`teilen, besteht darin, einen Wrapper um und zu erstellen. Dieser Wrapper würde die öffentliche Fläche vereinigen und gleichzeitig die Verhaltensunterschiede isolieren. Auf diese Weise können Sie die Änderungen hauptsächlich an der Konstruktion des Typs isolieren. [Microsoft.Extensions.DependencyModel-Bibliothek](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) folgt:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Zusätzliche Ressourcen

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.JsonÜbersicht](system-text-json-overview.md)
* [Wie zu verwendenSystem.Text.Json](system-text-json-how-to.md)
* [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md)
* [DateTime- und DateTimeOffset-Unterstützung inSystem.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonAPI-Referenz](xref:System.Text.Json)
* [System.Text.Json. Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
