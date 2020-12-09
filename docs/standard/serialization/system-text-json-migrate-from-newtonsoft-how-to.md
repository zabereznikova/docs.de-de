---
title: Migrieren von Newtonsoft.Json zu System.Text.Json – .NET
description: Erfahren Sie mehr zur Migration von Newtonsoft.Json zu System.Text.Json. Enthält Beispielcode.
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 11/30/2020
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: bc256c5129cd4a7306e632685474b159a43ce76c
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438052"
---
# <a name="how-to-migrate-from-no-locnewtonsoftjson-to-no-locsystemtextjson"></a>Migration von Newtonsoft.Json zu System.Text.Json

In diesem Artikel wird erläutert, wie Sie von [Newtonsoft.Json](https://www.newtonsoft.com/json) zu <xref:System.Text.Json> migrieren.

Der `System.Text.Json`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation). Die Bibliothek `System.Text.Json` ist ab [.NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) in der Runtime enthalten. Installieren Sie für andere Zielframeworks das NuGet-Paket [System.Text.Json](https://www.nuget.org/packages/System.Text.Json). Das Paket unterstützt:

* .NET Standard 2.0 und höhere Versionen
* .NET Framework 4.7.2 und höhere Versionen
* .NET Core 2.0, 2.1 und 2.2

`System.Text.Json` konzentriert sich hauptsächlich auf Leistung, Sicherheit und Einhaltung von Standards. Es weist einige wesentliche Unterschiede beim Standardverhalten auf und zielt nicht auf Featureparität mit `Newtonsoft.Json` ab. In einigen Szenarien verfügt `System.Text.Json` über keine integrierte Funktionalität, doch gibt es dafür empfohlene Problemumgehungen. In anderen Szenarien sind Problemumgehungen nicht praktikabel. Wenn Ihre Anwendung von einer fehlenden Funktion abhängig ist, sollten Sie erwägen, [ein Issue zu registrieren](https://github.com/dotnet/runtime/issues/new), um herauszufinden, ob Unterstützung für Ihr Szenario hinzugefügt werden kann.

Der Großteil dieses Artikels behandelt die Verwendungsweise der <xref:System.Text.Json.JsonSerializer>-API, aber er enthält auch Anleitungen zur Verwendung der Typen <xref:System.Text.Json.JsonDocument> (der das Dokumentobjektmodell (DOM) darstellt), <xref:System.Text.Json.Utf8JsonReader> und <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="table-of-differences-between-no-locnewtonsoftjson-and-no-locsystemtextjson"></a>Tabelle mit Unterschieden zwischen Newtonsoft.Json und System.Text.Json

In der folgenden Tabelle sind die `Newtonsoft.Json`-Funktionen mit ihren Entsprechungen in `System.Text.Json` aufgeführt. Die Entsprechungen lassen sich in die folgenden Kategorien einteilen:

* Unterstützt durch integrierte Funktionalität. Um ein ähnliches Verhalten von `System.Text.Json` zu erzielen, ist möglicherweise die Verwendung eines Attributs oder einer globalen Option erforderlich.
* Nicht unterstützt, Problemumgehung ist möglich. Die Problemumgehungen sind [benutzerdefinierte Konverter](system-text-json-converters-how-to.md), die möglicherweise keine vollständige Parität mit der `Newtonsoft.Json`-Funktionalität bereitstellen. Für einige davon wird Beispielcode als Beispiele bereitgestellt. Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, erfordert die Migration Änderungen an Ihren .NET-Objektmodellen oder andere Codeänderungen.
* Nicht unterstützt, Problemumgehung ist nicht praktikabel oder nicht möglich. Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, ist die Migration nicht ohne wesentliche Änderungen möglich.

::: zone pivot="dotnet-5-0"
| Feature in Newtonsoft.Json                               | Äquivalent in System.Text.Json |
|-------------------------------------------------------|-----------------------------|
| Standardmäßige Deserialisierung ohne Berücksichtigung von Groß-/Kleinschreibung           | ✔️ [Globale Einstellung „PropertyNameCaseInsensitive“](#case-insensitive-deserialization) |
| Eigenschaftsnamen mit Camel-Case-Schreibweise                             | ✔️ [Globale Einstellung „PropertyNamingPolicy“](system-text-json-customize-properties.md#use-camel-case-for-all-json-property-names) |
| Minimales Escapen von Zeichen                            | ✔️ [Strenges Escapen von Zeichen, konfigurierbar](#minimal-character-escaping) |
| Globale Einstellung `NullValueHandling.Ignore`             | ✔️ [DefaultIgnoreCondition (globale Option)](system-text-json-ignore-properties.md#ignore-all-null-value-properties) |[Bedingtes Ignorieren einer Eigenschaft](#conditionally-ignore-a-property)
| Kommentare zulassen                                        | ✔️ [Globale Einstellung „ReadCommentHandling“](#comments) |
| Nachfolgende Kommas zulassen                                 | ✔️ [Globale Einstellung „AllowTrailingCommas“](#trailing-commas) |
| Registrierung benutzerdefinierter Konverter                         | ✔️ [Rangordnung weicht ab](#converter-registration-precedence) |
| Keine standardmäßige maximale Tiefe                           | ✔️ [Standardmäßige maximale Tiefe von  64, konfigurierbar](#maximum-depth) |
| Globale Einstellung `PreserveReferencesHandling`           | ✔️ [ReferenceHandling (globale Einstellung)](#preserve-object-references-and-handle-loops) |
| Serialisieren oder Deserialisieren von Zahlen in Anführungszeichen            | ✔️ [NumberHandling (globale Einstellung), [JsonNumberHandling] (Attribut)](#allow-or-write-numbers-in-quotes) |
| Deserialisieren in unveränderliche Klassen und Strukturen          | ✔️ [JsonConstructor, C# 9-Datensätze](#deserialize-to-immutable-classes-and-structs) |
| Unterstützung für Felder                                    | ✔️ [IncludeFields (globale Einstellung), [JsonInclude] (Attribut)](#public-and-non-public-fields) |
| Globale Einstellung `DefaultValueHandling`                 | ✔️ [DefaultIgnoreCondition (globale Einstellung)](#conditionally-ignore-a-property) |
| Einstellung `NullValueHandling` für `[JsonProperty]`       | ✔️ [JsonIgnore (Attribut)](#conditionally-ignore-a-property)  |
| Einstellung `DefaultValueHandling` für `[JsonProperty]`    | ✔️ [JsonIgnore (Attribut)](#conditionally-ignore-a-property)  |
| Deserialisieren von `Dictionary` mit Nicht-Zeichenfolgen-Schlüssel          | ✔️ [Unterstützt](#dictionary-with-non-string-key) |
| Unterstützung für nicht öffentliche Setter und Getter von Eigenschaften   | ✔️ [JsonInclude (Attribut)](#non-public-property-setters-and-getters) |
| `[JsonConstructor]`-Attribut                         | ✔️ [[JsonConstructor] (Attribut)](#specify-constructor-to-use-when-deserializing) |
| Unterstützung für ein breites Spektrum von Typen                    | ⚠️ [Einige Typen erfordern benutzerdefinierte Konverter](#types-without-built-in-support) |
| Polymorphe Serialisierung                             | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#polymorphic-serialization) |
| Polymorphe Deserialisierung                           | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#polymorphic-deserialization) |
| Deserialisieren eines abgeleiteten Typs in `object`-Eigenschaften      | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#deserialization-of-object-properties) |
| Deserialisieren des JSON-Literals `null` in Non-Nullable-Werttypen | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#deserialize-null-to-non-nullable-type) |
| `Required`-Einstellung für `[JsonProperty]`-Attribut        | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#required-properties) |
| `DefaultContractResolver` zum Ignorieren von Eigenschaften       | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property) |
| Einstellungen `DateTimeZoneHandling` und `DateFormatString`   | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#specify-date-format) |
| Rückrufe                                             | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#callbacks) |
| `JsonConvert.PopulateObject`-Methode                   | ⚠️ [Nicht unterstützt, Problemumgehung](#populate-existing-objects) |
| Globale Einstellung `ObjectCreationHandling`               | ⚠️ [Nicht unterstützt, Problemumgehung](#reuse-rather-than-replace-properties) |
| Zu Sammlungen hinzufügen ohne Setter                    | ⚠️ [Nicht unterstützt, Problemumgehung](#add-to-collections-without-setters) |
| Globale Einstellung `ReferenceLoopHandling`                | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) |
| Unterstützung für `System.Runtime.Serialization`-Attribute | ❌ [Nicht unterstützt](#systemruntimeserialization-attributes) |
| Globale Einstellung `MissingMemberHandling`                | ❌ [Nicht unterstützt](#missingmemberhandling) |
| Eigenschaftsnamen ohne Anführungszeichen zulassen                   | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) |
| Einschließen von Zeichenfolgenwerten in einfache Anführungszeichen zulassen              | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) |
| JSON-Werte, die keine Zeichenfolgen sind, für Zeichenfolgeneigenschaften zulassen    | ❌ [Nicht unterstützt](#non-string-values-for-string-properties) |
::: zone-end

::: zone pivot="dotnet-core-3-1"
| Feature in Newtonsoft.Json                               | Äquivalent in System.Text.Json |
|-------------------------------------------------------|-----------------------------|
| Standardmäßige Deserialisierung ohne Berücksichtigung von Groß-/Kleinschreibung           | ✔️ [Globale Einstellung „PropertyNameCaseInsensitive“](#case-insensitive-deserialization) |
| Eigenschaftsnamen mit Camel-Case-Schreibweise                             | ✔️ [Globale Einstellung „PropertyNamingPolicy“](system-text-json-customize-properties.md#use-camel-case-for-all-json-property-names) |
| Minimales Escapen von Zeichen                            | ✔️ [Strenges Escapen von Zeichen, konfigurierbar](#minimal-character-escaping) |
| Globale Einstellung `NullValueHandling.Ignore`             | ✔️ [Globale Option „IgnoreNullValues“](system-text-json-ignore-properties.md#ignore-all-null-value-properties) |
| Kommentare zulassen                                        | ✔️ [Globale Einstellung „ReadCommentHandling“](#comments) |
| Nachfolgende Kommas zulassen                                 | ✔️ [Globale Einstellung „AllowTrailingCommas“](#trailing-commas) |
| Registrierung benutzerdefinierter Konverter                         | ✔️ [Rangordnung weicht ab](#converter-registration-precedence) |
| Keine standardmäßige maximale Tiefe                           | ✔️ [Standardmäßige maximale Tiefe von  64, konfigurierbar](#maximum-depth) |
| Unterstützung für ein breites Spektrum von Typen                    | ⚠️ [Einige Typen erfordern benutzerdefinierte Konverter](#types-without-built-in-support) |
| Deserialisieren von Zeichenfolgen als Zahlen                        | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#allow-or-write-numbers-in-quotes) |
| Deserialisieren von `Dictionary` mit Nicht-Zeichenfolgen-Schlüssel          | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#dictionary-with-non-string-key) |
| Polymorphe Serialisierung                             | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#polymorphic-serialization) |
| Polymorphe Deserialisierung                           | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#polymorphic-deserialization) |
| Deserialisieren eines abgeleiteten Typs in `object`-Eigenschaften      | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#deserialization-of-object-properties) |
| Deserialisieren des JSON-Literals `null` in Non-Nullable-Werttypen | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#deserialize-null-to-non-nullable-type) |
| Deserialisieren in unveränderliche Klassen und Strukturen          | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#deserialize-to-immutable-classes-and-structs) |
| `[JsonConstructor]`-Attribut                         | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#specify-constructor-to-use-when-deserializing) |
| `Required`-Einstellung für `[JsonProperty]`-Attribut        | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#required-properties) |
| `NullValueHandling`-Einstellung für `[JsonProperty]`-Attribut | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`-Einstellung für `[JsonProperty]`-Attribut | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property)  |
| Globale Einstellung `DefaultValueHandling`                 | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property) |
| `DefaultContractResolver` zum Ignorieren von Eigenschaften       | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#conditionally-ignore-a-property) |
| Einstellungen `DateTimeZoneHandling` und `DateFormatString`   | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#specify-date-format) |
| Rückrufe                                             | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#callbacks) |
| Unterstützung für öffentliche und nicht öffentliche Felder              | ⚠️ [Nicht unterstützt, Problemumgehung, Beispiel](#public-and-non-public-fields) |
| Unterstützung für nicht öffentliche Setter und Getter von Eigenschaften   | ⚠️ [Nicht unterstützt, Problemumgehung](#non-public-property-setters-and-getters) |
| `JsonConvert.PopulateObject`-Methode                   | ⚠️ [Nicht unterstützt, Problemumgehung](#populate-existing-objects) |
| Globale Einstellung `ObjectCreationHandling`               | ⚠️ [Nicht unterstützt, Problemumgehung](#reuse-rather-than-replace-properties) |
| Zu Sammlungen hinzufügen ohne Setter                    | ⚠️ [Nicht unterstützt, Problemumgehung](#add-to-collections-without-setters) |
| Globale Einstellung `PreserveReferencesHandling`           | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) |
| Globale Einstellung `ReferenceLoopHandling`                | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) |
| Unterstützung für `System.Runtime.Serialization`-Attribute | ❌ [Nicht unterstützt](#systemruntimeserialization-attributes) |
| Globale Einstellung `MissingMemberHandling`                | ❌ [Nicht unterstützt](#missingmemberhandling) |
| Eigenschaftsnamen ohne Anführungszeichen zulassen                   | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) |
| Einschließen von Zeichenfolgenwerten in einfache Anführungszeichen zulassen              | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) |
| JSON-Werte, die keine Zeichenfolgen sind, für Zeichenfolgeneigenschaften zulassen    | ❌ [Nicht unterstützt](#non-string-values-for-string-properties) |
::: zone-end

Dies ist keine vollständige Liste der `Newtonsoft.Json`-Funktionen. Die Liste enthält viele der Szenarien, die in [GitHub-Issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) oder [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json)-Beiträgen angefordert wurden. Wenn Sie eine Problemumgehung für eins der hier aufgelisteten Szenarien implementieren, für das derzeit kein Beispielcode vorhanden ist, und wenn Sie Ihre Lösung teilen möchten, wählen Sie **Diese Seite** im Abschnitt **Feedback** unten auf dieser Seite aus. Dadurch wird ein Issue im GitHub-Repository dieser Dokumentation erstellt und dieses ebenfalls im Abschnitt **Feedback** auf dieser Seite aufgeführt.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-no-locnewtonsoftjson"></a>Unterschiede beim Standardverhalten von JsonSerializer im Vergleich zu Newtonsoft.Json

<xref:System.Text.Json> ist standardmäßig strikt und vermeidet jegliche Vermutung oder Interpretation im Namen des Aufrufers, womit deterministisches Verhalten betont wird. Die Bibliothek ist absichtlich auf diese Weise für Leistung und Sicherheit konzipiert. `Newtonsoft.Json` ist standardmäßig flexibel. Dieser grundlegende Unterschied beim Design steht hinter vielen der folgenden spezifischen Unterschiede im Standardverhalten.

### <a name="case-insensitive-deserialization"></a>Deserialisierung ohne Berücksichtigung von Groß-/Kleinschreibung

Während der Deserialisierung führt `Newtonsoft.Json` standardmäßig einen Abgleich der Eigenschaftsnamen ohne Berücksichtigung von Groß-/Kleinschreibung durch. Das Standardverhalten von <xref:System.Text.Json> berücksichtigt die Groß-/Kleinschreibung, was eine bessere Leistung liefert, weil ein exakter Abgleich erfolgt. Informationen, wie Sie einen Abgleich ohne Berücksichtigung von Groß-/Kleinschreibung durchführen, finden Sie unter [Eigenschaftenabgleich ohne Berücksichtigung von Groß-/Kleinschreibung](system-text-json-character-casing.md).

Wenn Sie `System.Text.Json` indirekt durch Verwendung von ASP.NET Core verwenden, müssen Sie nichts tun, um ein Verhalten wie `Newtonsoft.Json` zu erhalten. ASP.NET Core gibt die Einstellungen für die Verwendung von [Eigenschaftsnamen mit Camel-Case-Schreibweise](system-text-json-customize-properties.md#use-camel-case-for-all-json-property-names) an sowie für den Abgleich ohne Berücksichtigung von Groß-/Kleinschreibung, wenn `System.Text.Json` verwendet wird.

::: zone pivot="dotnet-5-0"
ASP.NET Core ermöglicht auch standardmäßig das Deserialisieren von [Zahlen in Anführungszeichen](#allow-or-write-numbers-in-quotes).
::: zone-end

### <a name="minimal-character-escaping"></a>Minimales Escapen von Zeichen

Während der Serialisierung ist `Newtonsoft.Json` relativ nachsichtig, wenn es um das Durchlassen von Zeichen geht, ohne sie zu escapen. Dies bedeutet, dass sie nicht durch `\uxxxx` ersetzt werden, wobei `xxxx` der Codepunkt des Zeichens ist. Wenn sie escapet werden, geschieht dies durch Ausgabe eines umgekehrten Schrägstrichs (`\`) vor dem Zeichen (z. B. wird `"` zu `\"`). <xref:System.Text.Json> escapet standardmäßig mehr Zeichen, um eine tief greifenden Abwehr als Schutz vor Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffen (Veröffentlichung von Informationen) zu bieten, wobei dies durch Verwendung der Abfolge von sechs Zeichen erzielt wird. `System.Text.Json` escapet standardmäßig alle Nicht-ASCII-Zeichen, sodass Sie nichts machen müssen, wenn Sie `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json` verwenden. `System.Text.Json` escapet außerdem standardmäßig HTML-abhängige Zeichen. Informationen, wie Sie das Standardverhalten von `System.Text.Json` außer Kraft setzen können, finden Sie unter [Anpassen der Zeichencodierung](system-text-json-character-encoding.md).

### <a name="comments"></a>Kommentare

Während der Deserialisierung ignoriert `Newtonsoft.Json` standardmäßig Kommentare in der JSON-Datei. Das Standardverhalten von <xref:System.Text.Json> besteht im Auslösen von Ausnahmen für Kommentare, weil die Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) diese nicht umfasst. Informationen, wie Sie Kommentare zulassen können, finden Sie unter [Zulassen von Kommentaren und nachfolgenden Kommas](system-text-json-invalid-json.md).

### <a name="trailing-commas"></a>Nachfolgende Kommas

Während der Deserialisierung ignoriert `Newtonsoft.Json` standardmäßig nachfolgende Kommas. Es ignoriert ferner mehrere nachfolgende Kommas (z. B. `[{"Color":"Red"},{"Color":"Green"},,]`). Das Standardverhalten von <xref:System.Text.Json> besteht im Auslösen von Ausnahmen für nachfolgende Kommas, weil die Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) diese nicht zulässt. Informationen, wie Sie `System.Text.Json` dazu bringen, diese zu akzeptieren, finden Sie unter [Zulassen von Kommentaren und nachfolgenden Kommas](system-text-json-invalid-json.md). Es gibt keine Möglichkeit, mehrere nachfolgende Kommas zuzulassen.

### <a name="converter-registration-precedence"></a>Rangfolge für die Registrierung von Konvertern

Die Rangfolge der Registrierung von benutzerdefinierten Konvertern in `Newtonsoft.Json` ist wie folgt:

* Attribut auf Eigenschaftsebene
* Attribut auf Typebene
* [Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)-Sammlung

Diese Reihenfolge bedeutet, dass ein benutzerdefinierter Konverter in der `Converters`-Sammlung von einem Konverter außer Kraft gesetzt wird, der durch Anwenden eines Attributs auf Typebene registriert wird. Beide dieser Registrierungen werden von einem Attribut auf Eigenschaftsebene außer Kraft gesetzt.

Die Rangfolge der Registrierung von benutzerdefinierten Konvertern in <xref:System.Text.Json> weicht hiervon ab:

* Attribut auf Eigenschaftsebene
* <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung
* Attribut auf Typebene

Der Unterschied besteht hierbei darin, dass ein benutzerdefinierter Konverter in der `Converters`-Sammlung ein Attribut auf Typebene außer Kraft setzt. Die Absicht hinter dieser Rangfolge ist es, dass Änderungen zur Laufzeit eine zur Entwurfszeit getroffene Auswahl außer Kraft setzen sollen. Diese Rangfolge lässt sich nicht ändern.

Weitere Informationen zur Registrierung benutzerdefinierter Konverter finden Sie unter [Registrieren eines benutzerdefinierten Konverters](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Maximale Tiefe

`Newtonsoft.Json` besitzt kein standardmäßiges Limit für die maximale Tiefe. Für <xref:System.Text.Json> gibt es ein Standardlimit von 64, das sich durch Festlegen von <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType> konfigurieren lässt.

Wenn Sie `System.Text.Json` indirekt durch ASP.NET Core verwenden, beträgt die Obergrenze für die maximale Tiefe standardmäßig 32. Der Standardwert ist der gleiche wie bei Modellbindung und wird in der [JsonOptions-Klasse](https://github.com/dotnet/aspnetcore/blob/1f56888ea03f6a113587a6c4ac4d8b2ded326ffa/src/Mvc/Mvc.Core/src/JsonOptions.cs#L17-L20) festgelegt.

### <a name="json-strings-property-names-and-string-values"></a>JSON-Zeichenfolgen (Eigenschaftsnamen und Zeichenfolgenwerte)

Während der Deserialisierung akzeptiert `Newtonsoft.Json` Eigenschaftsnamen, die in doppelten oder einfachen Anführungszeichen stehen oder gar keine Anführungszeichen aufweisen. Es akzeptiert Zeichenfolgenwerte, die in doppelten oder einfachen Anführungszeichen stehen. `Newtonsoft.Json` akzeptiert beispielsweise folgendes JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json` akzeptiert nur Eigenschaftsnamen und Zeichenfolgenwerte, die in doppelten Anführungszeichen stehen, weil dieses Format von der Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) gefordert wird und das einzige Format ist, das als gültiges JSON-Format gilt.

Ein in einfache Anführungszeichen eingeschlossener Wert führt zu einer [JsonException](xref:System.Text.Json.JsonException) mit folgender Meldung:

```output
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Werte, die keine Zeichenfolgen sind, für Zeichenfolgeneigenschaften

`Newtonsoft.Json` akzeptiert Werte, die keine Zeichenfolgen sind, z. B. eine Zahl oder die Literale `true` und `false`, für die Deserialisierung von Eigenschaften vom Typ „String“ (Zeichenfolge). Im Folgenden finden Sie ein JSON-Beispiel, das `Newtonsoft.Json` erfolgreich in die folgende Klasse deserialisiert:

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

`System.Text.Json` deserialisiert Werte, die keine Zeichenfolgen sind, nicht in Zeichenfolgeneigenschaften. Ein für ein Zeichenfolgenfeld empfangener Wert, der keine Zeichenfolge ist, führt zu einer [JsonException](xref:System.Text.Json.JsonException) mit folgender Meldung:

```output
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer"></a>Szenarien mit JsonSerializer

Einige der folgenden Szenarien werden von der integrierten Funktionalität nicht unterstützt, aber Problemumgehungen sind möglich. Die Problemumgehungen sind [benutzerdefinierte Konverter](system-text-json-converters-how-to.md), die möglicherweise keine vollständige Parität mit der `Newtonsoft.Json`-Funktionalität bereitstellen. Für einige davon wird Beispielcode als Beispiele bereitgestellt. Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, erfordert die Migration Änderungen an Ihren .NET-Objektmodellen oder andere Codeänderungen.

Für einige der folgenden Szenarien sind Problemumgehungen nicht praktikabel oder möglich. Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, ist die Migration nicht ohne wesentliche Änderungen möglich.

### <a name="allow-or-write-numbers-in-quotes"></a>Zulassen oder Schreiben von Zahlen in Anführungszeichen

::: zone pivot="dotnet-5-0"
`Newtonsoft.Json` kann Zahlen serialisieren oder deserialisieren, die von JSON-Zeichenfolgen (in Anführungszeichen) dargestellt werden. Beispielsweise kann es `{"DegreesCelsius":"23"}` akzeptieren, anstelle von `{"DegreesCelsius":23}`. Um dieses Verhalten in <xref:System.Text.Json> zu aktivieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> auf <xref:System.Text.Json.Serialization.JsonNumberHandling.WriteAsString> oder <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString> fest, oder verwenden Sie das Attribut [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).

Wenn Sie `System.Text.Json` indirekt durch Verwendung von ASP.NET Core verwenden, müssen Sie nichts tun, um ein Verhalten wie `Newtonsoft.Json` zu erhalten. ASP.NET Core gibt [Webstandardwerte](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) an, wenn es `System.Text.Json` verwendet, und Webstandardwerte erlauben Zahlen in Anführungszeichen.

Weitere Informationen finden Sie unter [Zulassen oder Schreiben von Zahlen in Anführungszeichen](system-text-json-invalid-json.md).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`Newtonsoft.Json` kann Zahlen serialisieren oder deserialisieren, die von JSON-Zeichenfolgen (in Anführungszeichen) dargestellt werden. Beispielsweise kann es `{"DegreesCelsius":"23"}` akzeptieren, anstelle von `{"DegreesCelsius":23}`. Um dieses Verhalten in .NET Core 3.1 in <xref:System.Text.Json> zu aktivieren, implementieren Sie einen benutzerdefinierten Konverter, wie im folgenden Beispiel gezeigt. Der Konverter verarbeitet als `long` definierte Eigenschaften:

* Er serialisiert sie als JSON-Zeichenfolgen.
* Er akzeptiert während der Deserialisierung JSON-Zahlen und Zahlen in Anführungszeichen.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/LongToStringConverter.cs":::

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) für einzelne `long`-Eigenschaften oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.
::: zone-end

### <a name="specify-constructor-to-use-when-deserializing"></a>Angeben des bei der Deserialisierung zu verwendenden Konstruktors

Mit dem `[JsonConstructor]`-Attribut von `Newtonsoft.Json` können Sie angeben, welcher Konstruktor beim Deserialisieren in ein POCO aufgerufen werden soll.

::: zone pivot="dotnet-5-0"
`System.Text.Json` verfügt auch über das Attribut [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute). Weitere Informationen finden Sie unter [Unveränderliche Typen und Datensätze](system-text-json-immutability.md).
::: zone-end

::: zone pivot="dotnet-core-3-1"
In .NET Core 3.1 unterstützt <xref:System.Text.Json> nur parameterlose Konstruktoren. Als Problemumgehung können Sie einen beliebigen aufrufen, den Sie in einem benutzerdefinierten Konverter benötigen. Siehe das Beispiel für das [Deserialisieren in unveränderliche Klassen und Strukturen](#deserialize-to-immutable-classes-and-structs).
::: zone-end

### <a name="conditionally-ignore-a-property"></a>Bedingtes Ignorieren einer Eigenschaft

`Newtonsoft.Json` bietet mehrere Möglichkeiten, um eine Eigenschaft bei der Serialisierung oder Deserialisierung bedingt zu ignorieren:

* `DefaultContractResolver` ermöglicht das Auswählen von Eigenschaften, die basierend auf beliebigen Kriterien eingeschlossen oder ignoriert werden sollen.
* Mit den Einstellungen `NullValueHandling` und `DefaultValueHandling` von `JsonSerializerSettings` können Sie angeben, dass alle Eigenschaften mit Nullwert oder Standardwert ignoriert werden sollen.
* Mit den Einstellungen `NullValueHandling` und `DefaultValueHandling` des `[JsonProperty]`-Attributs können Sie einzelne Eigenschaften angeben, die ignoriert werden sollen, wenn Sie auf Null oder den Standardwert festgelegt sind.

::: zone pivot="dotnet-5-0"

<xref:System.Text.Json> bietet die folgenden Möglichkeiten, Eigenschaften oder Felder bei der Serialisierung zu ignorieren:

* Das [[JsonIgnore]](system-text-json-ignore-properties.md#ignore-individual-properties)-Attribut einer Eigenschaft bewirkt, dass die Eigenschaft während der Serialisierung im JSON-Code ausgelassen wird.
* Mit der globalen Option [IgnoreReadOnlyProperties](system-text-json-ignore-properties.md#ignore-all-read-only-properties) können Sie alle schreibgeschützten Eigenschaften ignorieren.
* Wenn Sie [Felder einschließen](system-text-json-how-to.md#include-fields), können Sie mit der globalen Option <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> alle schreibgeschützten Felder ignorieren.
* Mit der globalen Option `DefaultIgnoreCondition` können Sie [alle Wertetypeigenschaften mit Standardwerten ignorieren](system-text-json-ignore-properties.md#ignore-all-default-value-properties) oder [alle Verweistypeigenschaften mit dem Wert NULL ignorieren](system-text-json-ignore-properties.md#ignore-all-null-value-properties).

::: zone-end

::: zone pivot="dotnet-core-3-1"

<xref:System.Text.Json> in .NET Core 3.1 bietet die folgenden Möglichkeiten, Eigenschaften bei der Serialisierung zu ignorieren:

* Das [[JsonIgnore]](system-text-json-ignore-properties.md#ignore-individual-properties)-Attribut einer Eigenschaft bewirkt, dass die Eigenschaft während der Serialisierung im JSON-Code ausgelassen wird.
* Mit der globalen Option [IgnoreNullValues](system-text-json-ignore-properties.md#ignore-all-null-value-properties) können Sie alle Eigenschaften mit dem Wert NULL ignorieren.
* Mit der globalen Option [IgnoreReadOnlyProperties](system-text-json-ignore-properties.md#ignore-all-read-only-properties) können Sie alle schreibgeschützten Eigenschaften ignorieren.
::: zone-end

Diese Optionen gestatten Ihnen Folgendes **nicht**:

::: zone pivot="dotnet-5-0"

* Ignorieren ausgewählter Eigenschaften auf Grundlage beliebiger Kriterien, die zur Laufzeit ausgewertet werden.

::: zone-end

::: zone pivot="dotnet-core-3-1"

* Ignorieren aller Eigenschaften, die den Standardwert für den Typ aufweisen.
* Ignorieren ausgewählter Eigenschaften, die den Standardwert für den Typ aufweisen.
* Ignorieren ausgewählter Eigenschaften, wenn deren Wert Null ist.
* Ignorieren ausgewählter Eigenschaften auf Grundlage beliebiger Kriterien, die zur Laufzeit ausgewertet werden.

::: zone-end

Für diese Funktionalität können Sie einen benutzerdefinierten Konverter schreiben. Im Folgenden finden Sie ein Beispiel-POCO und einen benutzerdefinierten Konverter dafür, um diesen Ansatz zu veranschaulichen:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs":::

Der Konverter bewirkt, dass die `Summary`-Eigenschaft bei der Serialisierung ausgelassen wird, wenn ihr Wert Null, eine leere Zeichenfolge oder „N/V“ ist.

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.

Für diesen Ansatz ist zusätzliche Logik erforderlich, wenn:

* Das POCO komplexe Eigenschaften enthält.
* Sie Attribute wie `[JsonIgnore]` oder Optionen wie benutzerdefinierte Encoder verarbeiten müssen.

### <a name="public-and-non-public-fields"></a>Öffentliche und nicht öffentliche Felder

`Newtonsoft.Json` kann Felder ebenso wie Eigenschaften serialisieren und deserialisieren.

::: zone pivot="dotnet-5-0"
Verwenden Sie in <xref:System.Text.Json> die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> oder das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), um öffentliche Felder bei der Serialisierung oder Deserialisierung einzuschließen. Ein Beispiel finden Sie unter [Einschließen von Feldern](system-text-json-how-to.md#include-fields).
::: zone-end

::: zone pivot="dotnet-core-3-1"
<xref:System.Text.Json> in .NET Core 3.1 funktioniert nur mit öffentlichen Eigenschaften. Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.
::: zone-end

### <a name="preserve-object-references-and-handle-loops"></a>Erhalten von Objektverweise und Behandeln von Schleifen

Standardmäßig serialisiert `Newtonsoft.Json` als Wert. Wenn ein Objekt beispielsweise zwei Eigenschaften enthält, die einen Verweis auf dasselbe `Person`-Objekt enthalten, werden die Werte der Eigenschaften dieses `Person`-Objekts in JSON dupliziert.

`Newtonsoft.Json` verfügt über eine `PreserveReferencesHandling`-Einstellung für `JsonSerializerSettings`, mit der Sie als Verweis serialisieren können:

* Dem für das erste `Person`-Objekt erstellten JSON-Code werden Bezeichnermetadaten hinzugefügt.
* Der für das zweite `Person`-Objekt erstellte JSON-Code enthält einen Verweis auf diesen Bezeichner anstelle der Eigenschaftswerte.

`Newtonsoft.Json` verfügt außerdem über eine `ReferenceLoopHandling`-Einstellung, mit der Sie Zirkelbezüge ignorieren können, anstatt eine Ausnahme auszulösen.

::: zone pivot="dotnet-5-0"
Um Verweise beizubehalten und Zirkelbezüge zu behandeln, legen Sie <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A?displayProperty=nameWithType> in <xref:System.Text.Json> auf <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> fest. Die Einstellung `ReferenceHandler.Preserve` entspricht `PreserveReferencesHandling` = `PreserveReferencesHandling.All` in `Newtonsoft.Json`.

Wie bei [ReferenceResolver](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializer_ReferenceResolver.htm) von Newtonsoft.Json definiert die <xref:System.Text.Json.Serialization.ReferenceResolver?displayProperty=fullName>-Klasse das Verhalten bei Beibehaltung von Verweisen für Serialisierung und Deserialisierung. Erstellen Sie eine abgeleitete Klasse, um benutzerdefiniertes Verhalten anzugeben. Ein Beispiel finden Sie unter [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

Einige verwandte `Newtonsoft.Json`-Features werden nicht unterstützt:

* [JsonPropertyAttribute.IsReference](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonPropertyAttribute_IsReference.htm)
* [JsonPropertyAttribute.ReferenceLoopHandling](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonPropertyAttribute_ReferenceLoopHandling.htm)
* [JsonSerializerSettings.ReferenceLoopHandling](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_ReferenceLoopHandling.htm)

Weitere Informationen finden Sie unter [Beibehalten von Verweisen und Behandeln von Zirkelbezügen](system-text-json-preserve-references.md).
::: zone-end

::: zone pivot="dotnet-core-3-1"
<xref:System.Text.Json> in .NET Core 3.1 unterstützt nur die Serialisierung nach Wert und löst bei Zirkelbezügen eine Ausnahme aus.
::: zone-end

### <a name="dictionary-with-non-string-key"></a>Wörterbuch mit Schlüssel, der keine Zeichenfolgen ist

::: zone pivot="dotnet-5-0"
`Newtonsoft.Json` und `System.Text.Json` unterstützen Sammlungen des Typs `Dictionary<TKey, TValue>`.
::: zone-end

::: zone pivot="dotnet-core-3-1"
`Newtonsoft.Json` unterstützt Sammlungen des Typs `Dictionary<TKey, TValue>`. Die integrierte Unterstützung für Wörterbuchsammlungen in <xref:System.Text.Json> ist in .NET Core 3.1 auf `Dictionary<string, TValue>` beschränkt. Das heißt, der Schlüssel muss eine Zeichenfolge sein.

Um in .NET Core 3.1 ein Wörterbuch mit einem Schlüssel des Typs „integer“ (ganze Zahl) oder eines anderen Typs zu unterstützen, erstellen Sie einen Konverter wie im Beispiel in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).
::: zone-end

### <a name="types-without-built-in-support"></a>Typen ohne integrierte Unterstützung

<xref:System.Text.Json> bietet für die folgenden Typen keine integrierte Unterstützung:

* <xref:System.Data.DataTable> und verwandte Typen
* F#-Typen, z. B. [Diskriminierte Unions](../../fsharp/language-reference/discriminated-unions.md), [Datensatztypen](../../fsharp/language-reference/records.md) und [anonyme Datensatztypen](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> und seine zugehörigen generischen Typen

Benutzerdefinierte Konverter können für Typen implementiert werden, für die keine integrierte Unterstützung vorhanden ist.

### <a name="polymorphic-serialization"></a>Polymorphe Serialisierung

`Newtonsoft.Json` führt automatisch eine polymorphe Serialisierung durch. Informationen zu den eingeschränkten polymorphen Serialisierungsfunktionen von <xref:System.Text.Json> finden Sie unter [Serialisieren von Eigenschaften abgeleiteter Klassen](system-text-json-polymorphism.md).

Die dort beschriebene Problemumgehung besteht darin, Eigenschaften zu definieren, die abgeleitete Klassen als `object`-Typ enthalten können. Wenn dies nicht möglich ist, besteht eine weitere Möglichkeit darin, einen Konverter mit einer `Write`-Methode für die gesamte Vererbungstyphierarchie zu erstellen, wie im Beispiel in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-polymorphic-deserialization) gezeigt.

### <a name="polymorphic-deserialization"></a>Polymorphe Deserialisierung

`Newtonsoft.Json` verfügt über eine `TypeNameHandling`-Einstellung, mit der dem JSON-Code beim Serialisieren Typnamen-Metadaten hinzugefügt werden. Sie verwendet die Metadaten während der Deserialisierung, um die polymorphe Deserialisierung durchzuführen. <xref:System.Text.Json> kann in einem begrenzten Bereich [polymorphe Serialisierung](system-text-json-polymorphism.md) durchführen, aber keine polymorphe Deserialisierung.

Um polymorphe Deserialisierung zu unterstützen, erstellen Sie einen Konverter wie das Beispiel in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserialisierung von Objekteigenschaften

Wenn `Newtonsoft.Json` in <xref:System.Object> deserialisieren, wird Folgendes ausgeführt:

* Es leitet den Typ primitiver Werte in der JSON-Nutzlast (außer `null`) ab und gibt die gespeicherten Typen `string`, `long`, `double`, `boolean` oder `DateTime` als geschachteltes Objekt zurück. *Primitive Werte* sind einzelne JSON-Werte, wie eine JSON-Zahl, -Zeichenfolge, `true`, `false` oder `null`.
* Gibt ein `JObject` oder `JArray` für komplexe Werte in der JSON-Nutzlast zurück. *Komplexe Werte* sind Sammlungen von JSON-Schlüssel-Wert-Paaren in geschweiften Klammern (`{}`) oder Listen mit Werten in eckigen Klammern (`[]`). Die Eigenschaften und Werte in geschweiften oder eckigen Klammern können zusätzliche Eigenschaften oder Werte besitzen.
* Gibt einen Nullverweis zurück, wenn die Nutzlast das JSON-Literal `null` enthält.

<xref:System.Text.Json> speichert bei der Deserialisierung in <xref:System.Object> ein geschachteltes `JsonElement` sowohl für primitive als auch für komplexe Werte, z. B.:

* Eine `object`-Eigenschaft.
* Ein `object`-Wörterbuchwert.
* Ein `object`-Arraywert.
* Ein Stamm-`object`.

`System.Text.Json` behandelt `null` jedoch genau wie `Newtonsoft.Json` und gibt einen Nullverweis zurück, wenn die Nutzlast das JSON-Literal `null` enthält.

Um Typrückschlüsse für `object`-Eigenschaften zu implementieren, erstellen Sie einen Konverter wie in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserialisieren eines Null-Typs in einen Non-Nullable-Typ

`Newtonsoft.Json` löst im folgenden Szenario keine Ausnahme aus:

* `NullValueHandling` ist auf `Ignore` festgelegt, und
* Während der Deserialisierung enthält JSON einen Nullwert für einen Non-Nullable-Werttyp.

Im selben Szenario löst <xref:System.Text.Json> eine Ausnahme aus. (Die entsprechende Einstellung in `System.Text.Json` für die Behandlung von NULL ist <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> = `true`.)

Wenn Sie den Zieltyp besitzen, besteht die beste Problemumgehung darin, die betreffende Eigenschaft „nullable“ zu machen (z. B. `int` in `int?` ändern).

Eine weitere Problemumgehung besteht darin, einen Konverter für den Typ zu erstellen, wie im folgenden Beispiel, das Nullwerte für `DateTimeOffset`-Typen behandelt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs":::

Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Eigenschaft](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.

**Hinweis**: Der vorherige Konverter **behandelt Nullwerte anders**, als dies `Newtonsoft.Json` für POCOS tut, die Standardwerte angeben. Angenommen, der folgende Code stellt Ihr Zielobjekt dar:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithDefault":::

Und nehmen wir weiterhin an, der folgende JSON-Code wird mithilfe des vorherigen Konverters deserialisiert:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Nach der Deserialisierung hat die `Date`-Eigenschaft den Wert „1/1/0001“ (`default(DateTimeOffset)`), d. h., der im Konstruktor festgelegte Wert wird überschrieben. Beim selben POCO und JSON-Code würde die Deserialisierung mit `Newtonsoft.Json` den Wert „1/1/2001“ in der `Date`-Eigenschaft belassen.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserialisieren in unveränderliche Klassen und Strukturen

`Newtonsoft.Json` kann in unveränderliche Klassen und Strukturen deserialisieren, weil es Konstruktoren verwenden kann, die Parameter besitzen.

::: zone pivot="dotnet-5-0"
Geben Sie in <xref:System.Text.Json> das Attribut [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute) an, um die Verwendung eines parametrisierten Konstruktors festzulegen. Datensätze in C# 9 sind ebenfalls unveränderlich und werden als Deserialisierungsziele unterstützt. Weitere Informationen finden Sie unter [Unveränderliche Typen und Datensätze](system-text-json-immutability.md).
::: zone-end

::: zone pivot="dotnet-core-3-1"
In .NET Core 3.1 unterstützt <xref:System.Text.Json> nur öffentliche parameterlose Konstruktoren. Als Problemumgehung können Sie einen Konstruktor mit Parametern in einem benutzerdefinierten Konverter aufrufen.

Im Folgenden finden Sie eine unveränderliche Struktur mit mehreren Konstruktorparametern:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ImmutablePoint.cs" id="ImmutablePoint":::

Und hier sehen Sie einen Konverter, der diese Struktur serialisiert und deserialisiert:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs":::

Registrieren Sie diesen benutzerdefinierten Konverter durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.

Ein Beispiel für einen ähnlichen Konverter, der offene generische Eigenschaften behandelt, finden Sie unter der [Integrierter Konverter für Schlüssel-Wert-Paare](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).
::: zone-end

### <a name="required-properties"></a>Erforderliche Eigenschaften

In `Newtonsoft.Json` geben Sie an, dass eine Eigenschaft erforderlich ist, indem Sie `Required` für das `[JsonProperty]`-Attribut festlegen. `Newtonsoft.Json` löst eine Ausnahme aus, wenn im JSON für eine als erforderlich markierte Eigenschaft kein Wert empfangen wird.

<xref:System.Text.Json> löst keine Ausnahme aus, wenn kein Wert für eine der Eigenschaften des Zieltyps empfangen wird. Wenn Sie z. B. eine `WeatherForecast`-Klasse haben:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

Der folgende JSON-Code wird ohne Fehler deserialisiert:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Damit die Deserialisierung fehlschlägt, wenn der JSON-Code keine `Date`-Eigenschaft enthält, implementieren Sie einen benutzerdefinierten Konverter. Der folgende Beispielcode für einen Konverter löst nach Abschluss der Deserialisierung eine Ausnahme aus, wenn die `Date`-Eigenschaft nicht festgelegt ist:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs":::

Registrieren Sie diesen benutzerdefinierten Konverter durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>-Sammlung.

Für dieses Muster rekursiver Aufrufe des Konverters ist erforderlich, dass Sie den Konverter mit <xref:System.Text.Json.JsonSerializerOptions> registrieren, anstatt mithilfe eines Attributs. Wenn Sie den Konverter mithilfe eines Attributs registrieren, ruft der benutzerdefinierte Konverter sich rekursiv selbst auf. Dies resultiert in einer Endlosschleife, die mit einer Stapelüberlaufausnahme endet.

Wenn Sie den Konverter mithilfe des Optionsobjekts registrieren, vermeiden Sie eine Endlosschleife, indem Sie nicht das Options-Objekt übergeben, wenn <xref:System.Text.Json.JsonSerializer.Serialize%2A> oder <xref:System.Text.Json.JsonSerializer.Deserialize%2A> rekursiv aufgerufen wird. Das options-Objekt enthält die <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>-Sammlung. Wenn Sie es an `Serialize` oder `Deserialize` übergeben, ruft sich der benutzerdefinierte Konverter selbst auf, wodurch eine Endlosschleife entsteht, die zu einer Stapelüberlaufausnahme führt. Wenn die Standardoptionen nicht praktikabel sind, erstellen Sie eine neue Instanz der Optionen mit den Einstellungen, die Sie benötigen. Diese Vorgehensweise ist langsam, da jede neue Instanz unabhängig zwischengespeichert wird.

Es gibt ein alternatives Muster, dass die `JsonConverterAttribute`-Registrierung für die zu konvertierende Klasse verwenden kann. Bei diesem Ansatz ruft der Code des Konverters `Serialize` oder `Deserialize` für eine Klasse auf, die von der zu konvertierenden Klasse abgeleitet wird. `JsonConverterAttribute` wird nicht auf die abgeleitete Klasse angewendet. Im folgenden Beispiel dieser Alternative:

* ist `WeatherForecastWithRequiredPropertyConverterAttribute` die zu deserialisierende Klasse, und `JsonConverterAttribute` wurde auf diese angewendet.
* ist `WeatherForecastWithoutRequiredPropertyConverterAttribute` die abgeleitete Klasse, die das Konverterattribut nicht aufweist.
* Der Code im Konverter ruft `Serialize` und `Deserialize` für `WeatherForecastWithoutRequiredPropertyConverterAttribute` auf, um eine Endlosschleife zu vermeiden. Bei diesem Serialisierungsansatz kommt es zu Leistungseinbußen, da eine zusätzliche Objektinstanziierung und Kopien von Eigenschaftswerten vorgenommen werden.

Im Folgenden werden die `WeatherForecast*`-Typen veranschaulicht:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithReqPptyConverterAttr":::

So sieht der Konverter aus:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverterForAttributeRegistration.cs":::

Der erforderliche Eigenschaftenkonverter würde zusätzliche Logik erfordern, wenn Sie Attribute wie [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) oder verschiedene Optionen wie benutzerdefinierte Encoder verarbeiten müssten. Der Beispielcode verarbeitet außerdem keine Eigenschaften, für die im Konstruktor ein Standardwert festgelegt ist. Und dieser Ansatz unterscheidet nicht zwischen den folgenden Szenarien:

* Im JSON fehlt eine Eigenschaft.
* Im JSON ist eine Eigenschaft für einen Non-Nullable-Typ vorhanden, aber der Wert ist der Standardwert für den Typ, z. B. Null für einen `int`.
* Im JSON ist eine Eigenschaft für einen Nullable-Werttyp vorhanden, aber der Wert ist Null.

### <a name="specify-date-format"></a>Angeben des Datumsformats

`Newtonsoft.Json` bietet verschiedene Möglichkeiten, um zu kontrollieren, wie Eigenschaften des Typs `DateTime` und `DateTimeOffset` serialisiert und deserialisiert werden:

* Die `DateTimeZoneHandling`-Einstellung kann verwendet werden, um alle `DateTime`-Werte als UTC-Datumsangaben zu serialisieren.
* Die `DateFormatString`-Einstellung und `DateTime`-Konverter können verwendet werden, um das Format von Datumszeichenfolgen anzupassen.

In <xref:System.Text.Json> ist das einzige Format, das über integrierte Unterstützung verfügt, ISO 8601-1:2019, da es weit verbreitet und eindeutig ist und Roundtrips exakt gestaltet. Um ein beliebiges anderes Format zu verwenden, erstellen Sie einen benutzerdefinierten Konverter. Weitere Informationen finden Sie unter [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Rückrufe

`Newtonsoft.Json` ermöglicht das Ausführen von benutzerdefiniertem Code an mehreren Stellen im Serialisierungs- oder Deserialisierungsprozess:

* OnDeserializing (bei Beginn der Deserialisierung eines Objekts)
* OnDeserialized (nach Abschluss der Deserialisierung eines Objekts)
* OnSerializing (bei Beginn der Serialisierung eines Objekts)
* OnSerialized (nach Abschluss der Serialisierung eines Objekts)

In <xref:System.Text.Json> können Sie Rückrufe simulieren, indem Sie einen benutzerdefinierten Konverter schreiben. Im folgenden Beispiel wird ein benutzerdefinierter Konverter für ein POCO gezeigt. Der Konverter enthält Code, der an jeder Stelle eine Meldung anzeigt, die einem `Newtonsoft.Json`-Rückruf entspricht.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs":::

Registrieren Sie diesen benutzerdefinierten Konverter durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.

Wenn Sie einen benutzerdefinierten Konverter verwenden, der sich am vorangehenden Beispiel orientiert:

* Der `OnDeserializing`-Code hat keinen Zugriff auf die neue POCO-Instanz. Um die neue POCO-Instanz zu Beginn der Deserialisierung zu bearbeiten, fügen Sie diesen Code in den POCO-Konstruktor ein.
* Vermeiden Sie eine Endlosschleife, indem Sie den Konverter im Options-Objekt registrieren und dieses nicht übergeben, wenn `Serialize` oder `Deserialize` rekursiv aufgerufen wird.

Weitere Informationen zu benutzerdefinierten Konvertern, die`Serialize` oder `Deserialize` rekursiv aufrufen, finden Sie unter [Erforderliche Eigenschaften](#required-properties) weiter oben in diesem Artikel.

### <a name="non-public-property-setters-and-getters"></a>Nicht öffentliche Setter und Getter von Eigenschaften

`Newtonsoft.Json` kann private und interne Eigenschaften-Setter und -Getter über das `JsonProperty`-Attribut verwenden.

::: zone pivot="dotnet-5-0"
<xref:System.Text.Json> unterstützt private und interne Setter und Getter von Eigenschaften über das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute). Beispielcode finden Sie unter [Nicht öffentliche Eigenschaftenaccessoren](system-text-json-immutability.md).
::: zone-end

::: zone pivot="dotnet-core-3-1"
<xref:System.Text.Json> in .NET Core 3.1 unterstützt nur öffentliche Setter. Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.
::: zone-end

### <a name="populate-existing-objects"></a>Auffüllen vorhandener Objekte

Die `JsonConvert.PopulateObject`-Methode in `Newtonsoft.Json` deserialisiert ein JSON-Dokument in eine vorhandene Instanz einer Klasse, anstatt eine neue Instanz zu erstellen. <xref:System.Text.Json> erstellt immer eine neue Instanz des Zieltyps unter Verwendung des standardmäßigen öffentlichen parameterlosen Konstruktors. Benutzerdefinierte Konverter können in eine vorhandene Instanz deserialisieren.

### <a name="reuse-rather-than-replace-properties"></a>Wiederverwenden statt Ersetzen von Eigenschaften

Mit der Einstellung `Newtonsoft.Json` `ObjectCreationHandling` können Sie angeben, dass Objekte in Eigenschaften wiederverwendet werden sollen, anstatt während der Deserialisierung ersetzt zu werden. <xref:System.Text.Json> ersetzt Objekte in Eigenschaften immer.  Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.

### <a name="add-to-collections-without-setters"></a>Hinzufügen zu Sammlungen ohne Setter

Während der Deserialisierung fügt `Newtonsoft.Json` einer Sammlung Objekte hinzu, auch wenn die Eigenschaft über keinen Setter verfügt. <xref:System.Text.Json> ignoriert Eigenschaften, die keinen Setter besitzen. Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.

### <a name="systemruntimeserialization-attributes"></a>System.Runtime.Serialization-Attribute

<xref:System.Text.Json> unterstützt keine Attribute aus dem `System.Runtime.Serialization`-Namespace, z. B. `DataMemberAttribute` und `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Oktalzahlen

`Newtonsoft.Json` behandelt Zahlen mit einer führenden Null als Oktalzahlen. <xref:System.Text.Json> lässt keine führenden Nullen zu, da sie von der Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) nicht zugelassen werden.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json` kann so konfiguriert werden, dass während der Deserialisierung Ausnahmen ausgelöst werden, wenn JSON Eigenschaften enthält, die im Zieltyp fehlen. <xref:System.Text.Json> ignoriert zusätzliche Eigenschaften im JSON-Code, außer wenn Sie das Attribut [[JsonExtensionData]](system-text-json-handle-overflow.md) verwenden. Für die fehlende Member-Funktion gibt es keine Problemumgehung.

### <a name="tracewriter"></a>TraceWriter

Mit `Newtonsoft.Json` können Sie Debuggen, indem Sie einen `TraceWriter` verwenden, um Protokolle anzuzeigen, die von der Serialisierung oder Deserialisierung generiert werden. <xref:System.Text.Json> führt keine Protokollierung aus.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>„JsonDocument“ und „JsonElement“ im Vergleich zu „JToken“ (wie „JObject“, „JArray“)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, ein **schreibgeschütztes** Dokumentobjektmodell (DOM) aus vorhandenen JSON-Nutzlasten zu analysieren und zu erstellen. Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden. Der `JsonElement`-Typ stellt APIs zum Konvertieren von JSON-Text in allgemeine .NET-Typen bereit. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

### <a name="jsondocument-is-idisposable"></a>„JsonDocument“ ist „IDisposable“

`JsonDocument` erstellt eine In-Memory-Ansicht der Daten in einem gepoolten Puffer. Daher implementiert der `JsonDocument`-Typ `IDisposable`, im Gegensatz zu `JObject` oder `JArray` von `Newtonsoft.Json`,  und muss innerhalb eines using-Blocks verwendet werden.

Gibt nur ein `JsonDocument` von ihrer API zurück, wenn Sie den Besitz der Lebensdauer und die Verantwortung für die Entsorgung an den Aufrufer übertragen möchten. In den meisten Szenarien ist dies nicht erforderlich. Wenn der Aufrufer mit dem gesamten JSON-Dokument arbeiten muss, geben Sie den <xref:System.Text.Json.JsonElement.Clone%2A> des <xref:System.Text.Json.JsonDocument.RootElement%2A> zurück, bei dem es sich um ein <xref:System.Text.Json.JsonElement> handelt. Wenn der Aufrufer mit einem bestimmten Element innerhalb des JSON-Dokuments arbeiten muss, geben Sie den <xref:System.Text.Json.JsonElement.Clone%2A> dieses <xref:System.Text.Json.JsonElement> zurück. Wenn Sie das `RootElement` oder ein Unterelement direkt zurückgeben, ohne einen `Clone` zu erstellen, kann der Aufrufer nicht auf das zurückgegebene `JsonElement` zugreifen, nachdem das `JsonDocument`, das dessen Besitzer ist, entsorgt wurde.

Hier sehen Sie ein Beispiel, in dem Sie einen `Clone` erstellen müssen:

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

Der vorangehende Code erwartet ein `JsonElement`, das eine `fileName`-Eigenschaft enthält. Er öffnet die JSON-Datei und erstellt ein `JsonDocument`. Die Methode setzt voraus, dass der Aufrufer mit dem gesamten Dokument arbeiten möchte, weshalb sie den `Clone` des `RootElement` zurückgibt.

Wenn Sie ein `JsonElement` erhalten und ein Unterelement zurückgeben, ist es nicht notwendig, einen `Clone` des Unterelements zurückzugeben. Der Aufrufer ist dafür verantwortlich, das `JsonDocument` zu erhalten, zu dem das übergebene `JsonElement` gehört. Zum Beispiel:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>Das „JsonDocument“ ist schreibgeschützt.

Das <xref:System.Text.Json>-DOM kann keine JSON-Elemente hinzufügen, entfernen oder ändern. Es ist auf diese Weise konzipiert, um Leistung zu gewährleisten und Zuordnungen für die Analyse gängiger JSON-Nutzlastgrößen (d. h. <1 MB) zu verringern. Wenn Ihr Szenario derzeit ein änderbares DOM verwendet, könnte eine der folgenden Problemumgehungen praktikabel sein:

* Um ein `JsonDocument` von Grund auf neu zu erstellen (d. h. ohne eine vorhandene JSON-Nutzlast an die `Parse`-Methode zu übergeben), schreiben Sie den JSON-Text unter Verwendung von `Utf8JsonWriter`, und analysieren Sie dessen Ausgabe, um ein neues `JsonDocument` zu erstellen.
* Um ein vorhandenes `JsonDocument` zu ändern, verwenden Sie es, um JSON-Text zu schreiben, wobei Sie währenddessen Änderungen daran vornehmen, und analysieren seine Ausgabe, um daraus ein neues `JsonDocument` zu erstellen.
* Informationen zum Zusammenführen vorhandener JSON-Dokumente, entsprechend den APIs `JObject.Merge` oder `JContainer.Merge` aus `Newtonsoft.Json`, finden Sie unter [diesem GitHub-Issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>„JsonElement“ ist eine union-Struktur

`JsonDocument` macht das `RootElement` als Eigenschaft des Typs <xref:System.Text.Json.JsonElement> verfügbar, wobei es sich um einen union-Strukturtyp handelt, der jedes JSON-Element umfasst. `Newtonsoft.Json` verwendet dedizierte hierarchische Typen wie `JObject`, `JArray`, `JToken` usw. `JsonElement` ist das, was Sie durchsuchen und worüber Sie aufzählen können, und Sie können `JsonElement` verwenden, um JSON-Elemente in .NET-Typen zu materialisieren.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Durchsuchen eines „JSonDocument“ und „JsonElement“ nach Unterelementen

Suchen nach JSON-Token mithilfe von `JObject` oder `JArray` von `Newtonsoft.Json` sind in der Regel relativ schnell, da es sich dabei um Nachschlagevorgänge in einem Wörterbuch handelt. Im Vergleich dazu erfordern Suchen im `JsonElement` eine sequenzielle Suche der Eigenschaften, sodass sie deswegen relativ langsam sind (z. B. bei Verwendung von `TryGetProperty`). <xref:System.Text.Json> ist darauf ausgelegt, die anfängliche Analysezeit zu minimieren anstatt die Nachschlagezeit. Verwenden Sie deshalb die folgenden Ansätze, um die Leistung beim Durchsuchen eines `JsonDocument`-Objekts zu optimieren:

* Verwenden Sie die integrierten Enumeratoren (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> und <xref:System.Text.Json.JsonElement.EnumerateObject%2A>), anstatt ihre eigene Indizierung oder eigene Schleifen zu verwenden.
* Führen Sie keine sequenzielle Suche im gesamten `JsonDocument` durch alle Eigenschaften durch, indem Sie `RootElement` verwenden. Suchen Sie stattdessen in geschachtelten JSON-Objekten, basierend auf der bekannten Struktur der JSON-Daten. Wenn Sie z. B. nach einer `Grade`-Eigenschaft in `Student`-Objekten suchen, durchlaufen Sie die `Student`-Objekte per Schleife, und rufen Sie den Wert von `Grade` für jedes ab, anstatt auf der Suche nach `Grade`-Eigenschaften alle `JsonElement`-Objekte zu durchsuchen. Die letztgenannte Vorgehensweise führt zu unnötigen Durchläufen sämtlicher Daten.

Ein Codebeispiel finden Sie unter [Verwenden von „JsonDocument“ für den Zugriff auf Daten](write-custom-serializer-deserializer.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>„Utf8JsonReader“ im Vergleich zu „JsonTextReader“

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-codierten JSON-Text, der aus [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) oder [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) gelesen wird. Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann.

In den folgenden Abschnitten werden empfohlene Programmiermuster für die Verwendung von `Utf8JsonReader` erläutert.

### <a name="utf8jsonreader-is-a-ref-struct"></a>„Utf8JsonReader“ ist eine ref-Struktur.

Da der `Utf8JsonReader`-Typ eine *ref-Struktur* ist, unterliegt er [bestimmten Einschränkungen](../../csharp/language-reference/builtin-types/struct.md#ref-struct). Beispielsweise kann er nicht als Feld in einer anderen Klasse oder Struktur als einer ref-Struktur gespeichert werden. Um eine hohe Leistung zu erzielen, muss dieser Typ eine `ref struct` sein, da er die Eingabe [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), die wiederum eine ref-Struktur ist, zwischenspeichern muss. Darüber hinaus ist dieser Typ änderbar, da er den Zustand enthält. Daher **übergeben Sie ihn als Verweis** anstatt als Wert. Die Übergabe als Wert würde zu einer Strukturkopie führen, und die Zustandsänderungen wären für den Aufrufer nicht sichtbar. Dies unterscheidet sich von `Newtonsoft.Json`, da der `Newtonsoft.Json` `JsonTextReader` eine Klasse ist. Weitere Informationen zum Verwenden von ref-Strukturen finden Sie unter [Schreiben von sicherem und effizientem C#-Code](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Lesen von UTF-8-Text

Um die bestmögliche Leistung bei Verwendung des `Utf8JsonReader` zu erzielen, lesen Sie JSON-Nutzlasten bereits als UTF-8-codierten Text und nicht als UTF-16-Zeichenfolgen. Ein Codebeispiel finden Sie unter [Filtern von Daten mithilfe von Utf8JsonReader](write-custom-serializer-deserializer.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Lesen mit einem Stream oder PipeReader

Der `Utf8JsonReader` unterstützt das Lesen aus einem UTF-8-codierten [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) oder [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (wobei es sich um das Ergebnis des Lesens aus einem <xref:System.IO.Pipelines.PipeReader> handelt).

Beim synchronen Lesen können Sie die JSON-Nutzlast bis zum Ende des Streams in ein Bytearray einlesen und dieses dann an den Reader übergeben. Zum Lesen aus einer Zeichenfolge (die UTF-16-codiert ist), rufen Sie <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> auf, um die Zeichenfolge zuerst in ein UTF-8-codiertes Bytearray zu transcodieren. Übergeben Sie diese dann an den `Utf8JsonReader`.

Da der `Utf8JsonReader` die Eingabe als JSON-Text betrachtet, wird eine UTF-8-Bytereihenfolgen-Marke (BOM) als ungültiges JSON-Format angesehen. Der Aufrufer muss dies ausfiltern, bevor die Daten an den Reader übergeben werden.

Codebeispiele finden Sie unter [Verwenden von Utf8JsonReader](write-custom-serializer-deserializer.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Lesen mit „ReadOnlySequence“ mit mehreren Segmenten

Wenn es sich bei Ihrer JSON-Eingabe um ein [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) handelt, kann auf jedes JSON-Element über die `ValueSpan`-Eigenschaft des Readers zugegriffen werden, während Sie die Leseschleife durchlaufen. Wenn Ihre Eingabe jedoch ein [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) ist (was das Ergebnis des Lesens aus einem <xref:System.IO.Pipelines.PipeReader> ist), können einige JSON-Elemente mehrere Segmente des `ReadOnlySequence<byte>`-Objekts umspannen. Auf diese Elemente könnte nicht über <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in einem zusammenhängenden Speicherblock zugegriffen werden. Rufen Sie stattdessen, immer wenn Sie ein aus mehreren Segmenten bestehendes `ReadOnlySequence<byte>` als Eingabe haben, die <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A>-Eigenschaft des Readers ab, um zu ermitteln, wie der Zugriff auf das aktuelle JSON-Element erfolgen kann. Ein empfohlenes Muster finden Sie hier:

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

### <a name="use-valuetextequals-for-property-name-lookups"></a>Verwenden von „ValueTextEquals“ für das Nachschlagen von Eigenschaftsnamen

Verwenden Sie nicht <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>, um byteweise Vergleiche durchzuführen, indem Sie <xref:System.MemoryExtensions.SequenceEqual%2A> für das Nachschlagen von Eigenschaftennamen aufrufen. Rufen Sie stattdessen <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> auf, da diese Methode die Escapezeichen von allen in JSON escapeten Zeichen entfernt. Hier finden Sie ein Beispiel, das zeigt, wie Sie nach einer Eigenschaft suchen, die „name“ heißt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs" id="DefineUtf8Var":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs" id="UseUtf8Var" highlight="9":::

### <a name="read-null-values-into-nullable-value-types"></a>Lesen von Nullwerten in Nullable-Werttypen

`Newtonsoft.Json` bietet APIs, die <xref:System.Nullable%601> zurückgeben, z. B. `ReadAsBoolean`, das einen `Null` `TokenType` für Sie verarbeitet, indem es einen `bool?` zurückgibt. Die integrierten `System.Text.Json`-APIs geben nur Non-Nullable-Werttypen zurück. <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> gibt beispielsweise einen `bool` zurück. Wenn es `Null` in JSON findet, löst es eine Ausnahme aus. In den folgenden Beispielen werden zwei Möglichkeiten zum Behandeln von Nullwerten veranschaulicht, eine, bei der ein Nullable-Werttyp zurückgegeben wird, und eine andere, bei der der Standardwert zurückgegeben wird:

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

Wenn Sie weiterhin `Newtonsoft.Json` für bestimmte Zielframeworks verwenden müssen, können Sie mehrere Zielversionen verwenden und zwei Implementierungen verwenden. Dies ist jedoch nicht trivial und erfordert einige `#ifdefs` sowie Quellduplizierung. Eine Möglichkeit, so viel Code wie möglich gemeinsam zu verwenden, besteht darin, `Utf8JsonReader` und `Newtonsoft.Json` `JsonTextReader` in einen `ref struct`-Wrapper einzuschließen. Mit diesem Wrapper wird der öffentliche Oberflächenbereich vereinheitlicht, während die Verhaltensunterschiede isoliert werden. Auf diese Weise können Sie die Änderungen hauptsächlich auf die Konstruktion des Typs beschränken und den neuen Typ gleichzeitig als Verweis übergeben. Dies ist das Muster, an dem sich die [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)-Bibliothek orientiert:

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>„Utf8JsonWriter“ im Vergleich zu „JsonTextWriter“

Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben. Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann.

In den folgenden Abschnitten werden empfohlene Programmiermuster für die Verwendung von `Utf8JsonWriter` erläutert.

### <a name="write-with-utf-8-text"></a>Schreiben mit UTF-8-Text

Um die bestmögliche Leistung bei Verwendung des `Utf8JsonWriter` zu erzielen, schreiben Sie JSON-Nutzlasten bereits als UTF-8-codierten Text und nicht als UTF-16-Zeichenfolgen. Verwenden Sie <xref:System.Text.Json.JsonEncodedText>, um bekannte Zeichenfolgen-Eigenschaftsnamen sowie -werte als statische Elemente zwischenzuspeichern und vorzucodieren, und übergeben Sie diese dann an den Writer, anstatt UTF-16-Zeichenfolgenliterale zu verwenden. Dies ist schneller als das Zwischenspeichern und Verwenden von UTF-8-Bytearrays.

Diese Vorgehensweise funktioniert auch, wenn Sie benutzerdefiniert escapen müssen. `System.Text.Json` gestattet Ihnen nicht, während des Schreibens einer Zeichenfolge das Escapen zu deaktivieren. Sie können jedoch Ihren eigenen benutzerdefinierten <xref:System.Text.Encodings.Web.JavaScriptEncoder> als Option an den Writer übergeben oder Ihren eigenen `JsonEncodedText` erstellen, der Ihren `JavascriptEncoder` für das Escapen verwendet, und dann den `JsonEncodedText` anstelle der Zeichenfolge schreiben. Weitere Informationen finden Sie unter [Anpassen der Zeichencodierung](system-text-json-character-encoding.md).

### <a name="write-raw-values"></a>Schreiben von Rohwerten

Die `Newtonsoft.Json` `WriteRawValue`-Methode schreibt JSON-Rohcode, wenn ein Wert erwartet wird. <xref:System.Text.Json> besitzt keine direkte Entsprechung, aber hier finden Sie eine Problemumgehung, die sicherstellt, dass nur gültiger JSON-Code geschrieben wird:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Anpassen des Escapens von Zeichen

Die [StringEscapeHandling-](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)-Einstellung von `JsonTextWriter` bietet Optionen, um alle Nicht-ASCII-Zeichen **oder** HTML-Zeichen zu escapen. Standardmäßig escapet `Utf8JsonWriter` alle Nicht-ASCII- **und** HTML-Zeichen. Dieses Escapen erfolgt als tief greifende Abwehr aus Gründen des Schutzes. Um eine andere Escaperichtlinie anzugeben, erstellen Sie einen <xref:System.Text.Encodings.Web.JavaScriptEncoder>, und legen Sie <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType> fest. Weitere Informationen finden Sie unter [Anpassen der Zeichencodierung](system-text-json-character-encoding.md).

### <a name="customize-json-format"></a>Anpassen des JSON-Formats

`JsonTextWriter` umfasst die folgenden Einstellungen, für die es bei `Utf8JsonWriter` keine Entsprechung gibt:

* [Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm): Gibt an, um wie viele Zeichen ein Einzug erfolgen soll. `Utf8JsonWriter` führt Einzüge immer um 2 Zeichen aus.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm): Gibt das für Einzüge zu verwendende Zeichen an.  `Utf8JsonWriter` verwendet immer Leerzeichen.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm): Gibt das Zeichen an, das zum Umschließen von Zeichenfolgenwerten verwendet werden soll.  `Utf8JsonWriter` verwendet immer doppelte Anführungszeichen.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm): Gibt an, ob Eigenschaftsnamen in Anführungszeichen gesetzt werden sollen oder nicht.  `Utf8JsonWriter` umschließt sie immer mit Anführungszeichen.

Es gibt keine Problemumgehungen, mit denen Sie den von `Utf8JsonWriter` auf diese Weisen erzeugten JSON-Code anpassen können.

### <a name="write-null-values"></a>Schreiben von Nullwerten

Um Nullwerte mithilfe von `Utf8JsonWriter` zu schreiben, rufen Sie Folgendes auf:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>, um ein Schlüssel-Wert-Paar mit Null als Wert zu schreiben.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>, um Null als Element eines JSON-Arrays zu schreiben.

Wenn eine Zeichenfolge Null ist, entsprechen bei einer Zeichenfolgeneigenschaft <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> und <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> den Elementen `WriteNull` und `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Schreiben von TimeSpan-, Uri- oder char-Werten

`JsonTextWriter` stellt `WriteValue`-Methoden für [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)-, [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)- und [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm)-Werte bereit. `Utf8JsonWriter` verfügt über keine entsprechenden Methoden. Formatieren Sie diese Werte stattdessen als Zeichenfolgen (z. B. durch Aufrufen von `ToString()`), und rufen Sie <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> auf.

### <a name="multi-targeting"></a>Festlegung von Zielversionen

Wenn Sie weiterhin `Newtonsoft.Json` für bestimmte Zielframeworks verwenden müssen, können Sie mehrere Zielversionen verwenden und zwei Implementierungen verwenden. Dies ist jedoch nicht trivial und erfordert einige `#ifdefs` sowie Quellduplizierung. Eine Möglichkeit, so viel Code wie möglich gemeinsam zu verwenden, besteht darin, `Utf8JsonWriter` und `Newtonsoft` `JsonTextWriter` in einen Wrapper einzuschließen. Mit diesem Wrapper wird der öffentliche Oberflächenbereich vereinheitlicht, während die Verhaltensunterschiede isoliert werden. Auf diese Weise können Sie die Änderungen hauptsächlich auf die Konstruktion des Typs beschränken. Die [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)-Bibliothek orientiert sich an:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Zusätzliche Ressourcen

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Verwenden von System.Text.Json](system-text-json-how-to.md)
* [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md)
* [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
