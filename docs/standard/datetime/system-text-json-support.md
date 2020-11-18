---
title: Unterstützung von DateTime und DateTimeOffset in System.Text.Json
description: Eine Übersicht über die Unterstützung von DateTime-und DateTimeOffset-Typen in der System.Text.Js-Bibliothek.
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 3f8161c40f21428a4a22bef09582754069f3a2b6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817535"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Unterstützung von DateTime und DateTimeOffset in System.Text.Json

Der System.Text.Jsder Bibliothek analysiert und schreibt <xref:System.DateTime> <xref:System.DateTimeOffset> Werte gemäß dem erweiterten ISO 8601:-2019-Profil.
[Konverter](xref:System.Text.Json.Serialization.JsonConverter%601) bieten benutzerdefinierte Unterstützung für das Serialisieren und Deserialisieren mit <xref:System.Text.Json.JsonSerializer> .
Benutzerdefinierte Unterstützung kann auch bei Verwendung von und implementiert werden <xref:System.Text.Json.Utf8JsonReader> <xref:System.Text.Json.Utf8JsonWriter> .

## <a name="support-for-the-iso-8601-12019-format"></a>Unterstützung für das ISO 8601-1:2019-Format

Die <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.Utf8JsonReader> Typen,, <xref:System.Text.Json.Utf8JsonWriter> und <xref:System.Text.Json.JsonElement> analysieren und schreiben <xref:System.DateTime> -und- <xref:System.DateTimeOffset> Textdarstellungen gemäß dem erweiterten Profil des ISO 8601-1:2019-Formats, z. b. 2019-07-26t16:59:57-05:00.

<xref:System.DateTime> -und- <xref:System.DateTimeOffset> Daten können mit serialisiert werden <xref:System.Text.Json.JsonSerializer> :

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

Die Deserialisierung kann auch mit erfolgen <xref:System.Text.Json.JsonSerializer> :

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Mit den Standardoptionen <xref:System.DateTime> müssen Eingabe-und <xref:System.DateTimeOffset> Textdarstellungen dem erweiterten ISO 8601-1:2019-Profil entsprechen.
Der Versuch, Darstellungen zu deserialisieren, die nicht dem Profil entsprechen, bewirkt, dass Folgendes ausgelöst wird <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.JsonException> :

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

<xref:System.Text.Json.JsonDocument>Bietet strukturierten Zugriff auf den Inhalt einer JSON-Nutzlast, einschließlich der <xref:System.DateTime> -und- <xref:System.DateTimeOffset> Darstellungen. Im folgenden Beispiel wird gezeigt, wie bei einer Sammlung von Temperaturen die Durchschnittstemperatur am Montag berechnet werden kann:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Wenn Sie versuchen, die durchschnittliche Temperatur bei einer Nutzlast mit nicht kompatiblen Darstellungen zu berechnen <xref:System.DateTime> <xref:System.Text.Json.JsonDocument> , wird eine ausgelöst <xref:System.FormatException> :

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Die Schreibvorgänge auf niedrigerer Ebene <xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> und <xref:System.DateTimeOffset> Daten:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader> analysiert <xref:System.DateTime> und <xref:System.DateTimeOffset> Daten:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Wenn Sie versuchen, nicht kompatible Formate mit zu lesen <xref:System.Text.Json.Utf8JsonReader> , wird eine ausgelöst <xref:System.FormatException> :

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Benutzerdefinierte Unterstützung für <xref:System.DateTime> und <xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Bei Verwendung von <xref:System.Text.Json.JsonSerializer>

Wenn Sie möchten, dass das Serialisierungsprogramm eine benutzerdefinierte Formatierung oder Formatierung durchführt, können Sie [benutzerdefinierte Konverter](xref:System.Text.Json.Serialization.JsonConverter%601)implementieren.
Hier sind einige Beispiele:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Verwenden von `DateTime(Offset).Parse` und `DateTime(Offset).ToString`

Wenn Sie die Formate der Eingabe- <xref:System.DateTime> oder Textdarstellungen nicht ermitteln können <xref:System.DateTimeOffset> , können Sie die- `DateTime(Offset).Parse` Methode in der konverterleselogik verwenden. Dies ermöglicht Ihnen die Verwendung von. Umfassende Unterstützung für das Auswerten verschiedener <xref:System.DateTime> -und <xref:System.DateTimeOffset> -Textformate, einschließlich nicht-ISO 8601-Zeichen folgen und ISO 8601-Formaten, die nicht dem erweiterten ISO 8601-1:2019-Profil entsprechen. Diese Vorgehensweise ist erheblich weniger leistungsfähig als die native Implementierung des Serialisierungsprogramms.

Zum Serialisieren können Sie die- `DateTime(Offset).ToString` Methode in der konverterschreiblogik verwenden. Dies ermöglicht es Ihnen, <xref:System.DateTime> <xref:System.DateTimeOffset> mit einem beliebigen [Standardformat für Datum und Uhrzeit](../base-types/standard-date-and-time-format-strings.md)und den [benutzerdefinierten Datums-und Uhrzeit Formaten](../base-types/custom-date-and-time-format-strings.md)zu schreiben und Werte zu verwenden.
Dies ist auch bedeutend weniger leistungsfähiger als die systemeigene Implementierung des Serialisierungsprogramms.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Beim Implementieren von <xref:System.Text.Json.Serialization.JsonConverter%601> , und `T` ist der- <xref:System.DateTime> `typeToConvert` Parameter immer `typeof(DateTime)` .
Der-Parameter ist nützlich für die Behandlung von polymorphen Fällen und bei der Verwendung von Generika, um die Leistung zu erzielen `typeof(T)` .

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Verwenden von <xref:System.Buffers.Text.Utf8Parser> und <xref:System.Buffers.Text.Utf8Formatter>

Sie können schnelle UTF-8-basierte Methoden zum Formatieren und formatieren in der Konverterlogik verwenden, wenn Ihre Eingabe <xref:System.DateTime> <xref:System.DateTimeOffset> -oder Textdarstellungen mit einer der [Standardformat](../base-types/standard-date-and-time-format-strings.md)Zeichenfolgen "R", "l", "O" oder "G" kompatibel sind, oder wenn Sie gemäß einem dieser Formate schreiben möchten. Dies ist viel schneller als die Verwendung von `DateTime(Offset).Parse` und `DateTime(Offset).ToString` .

Dieses Beispiel zeigt einen benutzerdefinierten Konverter, <xref:System.DateTime> der Werte gemäß [dem Standardformat "R"](../base-types/standard-date-and-time-format-strings.md#the-rfc1123-r-r-format-specifier)serialisiert und deserialisiert:

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Das Standardformat "R" ist immer 29 Zeichen lang.
>
> Das Format "l" (Kleinbuchstaben "l") ist nicht mit den anderen [standardmäßigen Format](../base-types/standard-date-and-time-format-strings.md) Zeichenfolgen für Datum und Uhrzeit dokumentiert, da es nur von den Typen und unterstützt wird `Utf8Parser` `Utf8Formatter` . Das Format ist der klein geschriebene RFC 1123 (eine klein geschriebene Version des "R"-Formats), z. b.: "Do, 25 Jul 2019 06:36:07 GMT".

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Verwenden `DateTime(Offset).Parse` von als Fall Back für die native Analyse des Serialisierungsprogramms

Wenn Sie in der Regel davon ausgehen, dass <xref:System.DateTime> die Eingabe oder <xref:System.DateTimeOffset> die Daten dem erweiterten ISO 8601-1:2019-Profil entsprechen, können Sie die systemeigene Logik des Serialisierungsprogramms verwenden. Sie können auch nur dann einen Fall Back Mechanismus implementieren.
Dieses Beispiel zeigt, dass <xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)> der Konverter die Daten mithilfe von erfolgreich analysiert, nachdem eine Textdarstellung mit nicht analysiert wurde <xref:System.DateTime.Parse(System.String)> .

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Beim Schreiben mit <xref:System.Text.Json.Utf8JsonWriter>

Wenn Sie eine benutzerdefinierte <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellung mit schreiben möchten <xref:System.Text.Json.Utf8JsonWriter> , können Sie die benutzerdefinierte Darstellung in <xref:System.String> , `ReadOnlySpan<Byte>` , oder formatieren `ReadOnlySpan<Char>` <xref:System.Text.Json.JsonEncodedText> und dann an die entsprechende- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A?displayProperty=nameWithType> oder- <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A?displayProperty=nameWithType> Methode übergeben.

Im folgenden Beispiel wird gezeigt, wie ein benutzerdefiniertes <xref:System.DateTime> Format mit erstellt <xref:System.DateTime.ToString(System.String,System.IFormatProvider)> und dann mit der-Methode geschrieben werden kann <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> :

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Beim Lesen mit <xref:System.Text.Json.Utf8JsonReader>

Wenn Sie eine benutzerdefinierte <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellung mit lesen möchten <xref:System.Text.Json.Utf8JsonReader> , können Sie den Wert des aktuellen JSON-Tokens als <xref:System.String> verwenden <xref:System.Text.Json.Utf8JsonReader.GetString> und dann den Wert mithilfe der benutzerdefinierten Logik analysieren.

Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.DateTimeOffset> Textdarstellung mithilfe von abgerufen werden kann. <xref:System.Text.Json.Utf8JsonReader.GetString> anschließend wird Sie mit analysiert <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)> :

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Das erweiterte ISO 8601-1:2019-Profil in System.Text.Js

### <a name="date-and-time-components"></a>Datums-und Uhrzeit Komponenten

Das in implementierte erweiterte ISO 8601-1:2019 <xref:System.Text.Json> -Profil definiert die folgenden Komponenten für Datums-und Uhrzeit Darstellungen. Diese Komponenten werden verwendet, um verschiedene Granularitätsebene zu definieren, die bei der Verarbeitung und Formatierung und Darstellungen unterstützt werden <xref:System.DateTime> <xref:System.DateTimeOffset> .

| Komponente       | Format                      | BESCHREIBUNG                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Jahr            | "yyyy"                      | 0001-9999                                                                       |
| Month (Monat)           | "MM"                        | 01-12                                                                           |
| Tag             | "dd"                        | 01-28, 01-29, 01-30, 01-31 basierend auf Monat/Jahr                                  |
| Stunde            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Second          | "ss"                        | 00-59                                                                           |
| Zweiter Bruchteil | "FFFFFFF"                   | Mindestens eine Ziffer, maximal 16 Ziffern                                      |
| Zeit Offset     | "K"                         | Entweder "Z" oder "(' + '/'-') HH ': ' mm"                                                |
| Partielle Zeit    | "HH ': ' mm ': ' SS [fffffff]"     | Zeit ohne UTC-Offset-Informationen                                             |
| Vollständiges Datum       | "yyyy'-' mm '-' dd"            | Kalenderdatum                                                                   |
| Vollzeit       | "Partielle Zeit ' K"           | UTC der Tages-oder Ortszeit des Tages mit dem Zeit Offset zwischen Ortszeit und UTC |
| Datum und Uhrzeit       | "' Vollständiges Datum ' nicht ' ' voll Zeit '" | Datum und Uhrzeit des Kalenders, z. b. 2019-07-26t16:59:57-05:00                   |

### <a name="support-for-parsing"></a>Unterstützung für die-Verarbeitung

Die folgenden Granularitätsebene sind für die-Verarbeitung definiert:

1. "Full Date"
    1. "yyyy'-' mm '-' dd"

2. "' Full Date ' 't ' ' Hour ' ': ' ' Minute '"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm '

3. "' Vollständiges Datum ' ' ' partielle Zeit '"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss ' ([der sortierbare Format Bezeichner" s "](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))
    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." FFFFFFF

4. "' Full Date ' 't ' ' Time Hour ' ': ' ' Minute ' ' Zeit Offset '"
    1. "yyyy'-' mm'-' dd ' HH ': ' MMZ '
    2. "yyyy'-' mm'-' dd ' HH ': ' mm (' + '/'-') HH ': ' mm"

5. "Datum/Uhrzeit"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SSZ '
    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffffz "
    3. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm"
    4. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffff (' + '/'-') HH ': ' mm '

    Diese Granularitätsebene ist mit [RFC 3339](https://tools.ietf.org/html/rfc3339#section-5.6)kompatibel, einem weithin angenommenen Profil von ISO 8601, das für die Austauschbarkeit von Datums-und Uhrzeit Informationen verwendet wird. Es gibt jedoch einige Einschränkungen im System.Text.Jszur Implementierung.

    - RFC 3339 gibt keine maximale Anzahl von Sekundenbruchteilen an, sondern gibt an, dass mindestens eine Ziffer dem Zeitraum entsprechen muss, wenn ein Abschnitt mit einer Bruchteil-Sekunde vorhanden ist. Die-Implementierung in System.Text.Jsin ermöglicht bis zu 16 Ziffern (zur Unterstützung von Interop mit anderen Programmiersprachen und Frameworks), analysiert jedoch nur die ersten sieben. Eine <xref:System.Text.Json.JsonException> wird ausgelöst, wenn mehr als 16 Sekundenbruchteile beim Lesen von `DateTime` -und- `DateTimeOffset` Instanzen vorhanden sind.
    - In RFC 3339 können die Zeichen "t" und "z" jeweils "t" oder "z" lauten, aber Anwendungen können die Unterstützung nur auf die Großbuchstaben beschränken. Die Implementierung in System.Text.Json erfordert, dass Sie "T" und "Z" lauten. Eine <xref:System.Text.Json.JsonException> wird ausgelöst, wenn Eingabe Nutzlasten beim Lesen von `DateTime` -und-Instanzen "t" oder "z" enthalten `DateTimeOffset` .
    - RFC 3339 gibt an, dass die Datums-und Uhrzeit Abschnitte durch "T" voneinander getrennt sind, es Anwendungen jedoch ermöglicht, Sie stattdessen durch ein Leerzeichen ("") voneinander zu trennen. System.Text.Json erfordert, dass Datums-und Uhrzeit Abschnitte durch "T" getrennt werden. Eine <xref:System.Text.Json.JsonException> wird ausgelöst, wenn Eingabe Nutzlasten beim Lesen von `DateTime` -und-Instanzen ein Leerzeichen ("") enthalten `DateTimeOffset` .

Wenn Dezimaltrennzeichen für Sekunden vorhanden sind, muss mindestens eine Ziffer vorhanden sein. `2019-07-26T00:00:00.` ist nicht zulässig.
Bis zu 16 Dezimalstellen sind zulässig, es werden jedoch nur die ersten sieben analysiert. Alle über diese hinaus werden als null betrachtet.
Beispielsweise `2019-07-26T00:00:00.1234567890` wird so analysiert, als wäre es `2019-07-26T00:00:00.1234567` .
Dies soll mit der Implementierung kompatibel bleiben <xref:System.DateTime> , die auf diese Lösung beschränkt ist.

Schaltsekunden werden nicht unterstützt.

### <a name="support-for-formatting"></a>Unterstützung für Formatierung

Die folgenden Ebenen der Granularität sind für die Formatierung definiert:

1. "' Vollständiges Datum ' ' ' partielle Zeit '"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss ' ([der sortierbare Format Bezeichner" s "](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))

        Wird verwendet, um einen <xref:System.DateTime> ohne Sekundenbruchteile und ohne Offset Informationen zu formatieren.

    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." FFFFFFF

        Wird verwendet, um eine <xref:System.DateTime> mit Sekundenbruchteilen, aber ohne Offset Informationen zu formatieren.

2. "Datum/Uhrzeit"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SSZ '

        Wird verwendet, um einen <xref:System.DateTime> ohne Sekundenbruchteile zu formatieren, jedoch mit einem UTC-Offset.

    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffffz "

        Wird verwendet, um eine <xref:System.DateTime> mit Sekundenbruchteilen und einem UTC-Offset zu formatieren.

    3. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm"

        Wird verwendet, um eine <xref:System.DateTime> oder <xref:System.DateTimeOffset> ohne Sekundenbruchteile zu formatieren, jedoch mit einem lokalen Offset.

    4. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffff (' + '/'-') HH ': ' mm '

        Wird zum Formatieren von <xref:System.DateTime> oder <xref:System.DateTimeOffset> mit Sekundenbruchteilen und mit einem lokalen Offset verwendet.

    Diese Granularitätsebene ist mit [RFC 3339](https://tools.ietf.org/html/rfc3339#section-5.6)kompatibel.

Wenn die [Roundtrip-Format](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) Darstellung einer- <xref:System.DateTime> oder- <xref:System.DateTimeOffset> Instanz nachfolgende Nullen in den Sekundenbruchteilen aufweist <xref:System.Text.Json.JsonSerializer> , <xref:System.Text.Json.Utf8JsonWriter> formatiert und eine Darstellung der-Instanz ohne nachfolgende Nullen.
Beispielsweise wird eine <xref:System.DateTime> -Instanz, deren [Roundtrip-Format](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) Darstellung ist `2019-04-24T14:50:17.1010000Z` , gemäß und formatiert `2019-04-24T14:50:17.101Z` <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.Utf8JsonWriter> .

Wenn die [Roundtrip-Format](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) Darstellung einer- <xref:System.DateTime> oder- <xref:System.DateTimeOffset> Instanz in den Sekundenbruchteilen alle Nullen aufweist, <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.Utf8JsonWriter> formatieren und eine Darstellung der-Instanz ohne Sekundenbruchteile.
Beispielsweise wird eine <xref:System.DateTime> -Instanz, deren [Roundtrip-Format](../base-types/standard-date-and-time-format-strings.md#the-round-trip-o-o-format-specifier) Darstellung ist `2019-04-24T14:50:17.0000000+02:00` , gemäß und formatiert `2019-04-24T14:50:17+02:00` <xref:System.Text.Json.JsonSerializer> <xref:System.Text.Json.Utf8JsonWriter> .

Das Abschneiden von Nullen in Sekundenbruchteilen ermöglicht die kleinste Ausgabe, die zum Speichern von Informationen über einen zu schreibenden Roundtrip erforderlich ist.

Es werden maximal 7 Sekundenbruchteile geschrieben. Dies richtet sich nach der <xref:System.DateTime> Implementierung, die auf diese Lösung beschränkt ist.
