---
title: Unterstützung von DateTime und DateTimeOffset in System.Text.Json
description: Eine Übersicht über die Unterstützung von DateTime-und DateTimeOffset-Typen in der System. Text. JSON-Bibliothek.
ms.technology: dotnet-standard
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
ms.openlocfilehash: 8198359e2c54c4ed098703fbcc070f7469b3362a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344655"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Unterstützung von DateTime und DateTimeOffset in System.Text.Json

Die System. Text. JSON-Bibliothek analysiert und schreibt <xref:System.DateTime> und <xref:System.DateTimeOffset> Werte entsprechend dem erweiterten ISO 8601:-2019-Profil.
[Konverter](xref:System.Text.Json.Serialization.JsonConverter%601) bieten benutzerdefinierte Unterstützung für die Serialisierung und Deserialisierung mit <xref:System.Text.Json.JsonSerializer>.
Benutzerdefinierte Unterstützung kann auch implementiert werden, wenn <xref:System.Text.Json.Utf8JsonReader> und <xref:System.Text.Json.Utf8JsonWriter>verwendet werden.

## <a name="support-for-the-iso-8601-12019-format"></a>Unterstützung für das ISO 8601-1:2019-Format

Die <xref:System.Text.Json.JsonSerializer>-, <xref:System.Text.Json.Utf8JsonReader>-, <xref:System.Text.Json.Utf8JsonWriter>-und <xref:System.Text.Json.JsonElement> Typen analysieren und schreiben <xref:System.DateTime> und <xref:System.DateTimeOffset> Textdarstellungen gemäß dem erweiterten Profil des ISO 8601-1:2019-Formats. Beispiel: 2019-07-26t16:59:57-05:00.

<xref:System.DateTime> und <xref:System.DateTimeOffset> Daten können mit <xref:System.Text.Json.JsonSerializer>serialisiert werden:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

Sie können auch mit <xref:System.Text.Json.JsonSerializer>deserialisiert werden:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Mit den Standardoptionen müssen Eingabe <xref:System.DateTime> und <xref:System.DateTimeOffset> Textdarstellungen dem erweiterten ISO 8601-1:2019-Profil entsprechen.
Der Versuch, Darstellungen zu deserialisieren, die nicht dem Profil entsprechen, bewirkt, dass <xref:System.Text.Json.JsonSerializer> eine <xref:System.Text.Json.JsonException>auslöst:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

Der <xref:System.Text.Json.JsonDocument> bietet strukturierten Zugriff auf den Inhalt einer JSON-Nutzlast, einschließlich <xref:System.DateTime> und <xref:System.DateTimeOffset> Darstellungen. Im folgenden Beispiel wird gezeigt, wie bei einer Sammlung von Temperaturen die Durchschnittstemperatur am Montag berechnet werden kann:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Wenn Sie versuchen, die durchschnittliche Temperatur bei einer Nutzlast mit nicht kompatiblen <xref:System.DateTime> Darstellungen zu berechnen, lösen <xref:System.Text.Json.JsonDocument> eine <xref:System.FormatException>aus:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Mit der niedrigeren Ebene <xref:System.Text.Json.Utf8JsonWriter> werden <xref:System.DateTime> und <xref:System.DateTimeOffset> Daten geschrieben:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader> analysiert <xref:System.DateTime> und <xref:System.DateTimeOffset> Daten:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Wenn Sie versuchen, nicht kompatible Formate mit <xref:System.Text.Json.Utf8JsonReader> zu lesen, wird eine <xref:System.FormatException>ausgelöst:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Benutzerdefinierte Unterstützung für <xref:System.DateTime> und <xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Wenn Sie <xref:System.Text.Json.JsonSerializer> verwenden

Wenn Sie möchten, dass das Serialisierungsprogramm eine benutzerdefinierte Formatierung oder Formatierung durchführt, können Sie [benutzerdefinierte Konverter](xref:System.Text.Json.Serialization.JsonConverter%601)implementieren.
Hier finden Sie einige Beispiele:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Verwenden von `DateTime(Offset).Parse` und `DateTime(Offset).ToString`

Wenn Sie die Formate der Eingabe <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellungen nicht ermitteln können, können Sie die `DateTime(Offset).Parse`-Methode in der konverterleselogik verwenden. Dies ermöglicht Ihnen die Verwendung von. Umfassende Unterstützung für das Auswerten verschiedener <xref:System.DateTime>-und <xref:System.DateTimeOffset> Textformate, einschließlich nicht-ISO 8601-Zeichen folgen und ISO 8601-Formaten, die nicht dem erweiterten ISO 8601-1:2019-Profil entsprechen. Diese Vorgehensweise ist erheblich weniger leistungsfähig als die native Implementierung des Serialisierungsprogramms.

Zum Serialisieren können Sie die `DateTime(Offset).ToString`-Methode in der konverterschreiblogik verwenden. Dies ermöglicht es Ihnen, <xref:System.DateTime> und <xref:System.DateTimeOffset> Werte mit einem beliebigen [Standardformat für Datum und Uhrzeit](../base-types/standard-date-and-time-format-strings.md)sowie den [benutzerdefinierten Datums-und Uhrzeit Formaten](../base-types/custom-date-and-time-format-strings.md)zu schreiben.
Dies ist auch bedeutend weniger leistungsfähiger als die systemeigene Implementierung des Serialisierungsprogramms.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Wenn Sie <xref:System.Text.Json.Serialization.JsonConverter%601>implementieren und `T` <xref:System.DateTime>ist, wird der `typeToConvert` Parameter immer `typeof(DateTime)`.
Der-Parameter ist nützlich für die Behandlung von polymorphen Fällen und bei der Verwendung von Generika, um `typeof(T)` auf leistungsstarke Weise zu erzielen.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Verwenden von <xref:System.Buffers.Text.Utf8Parser> und <xref:System.Buffers.Text.Utf8Formatter>

Sie können schnelle UTF-8-basierte Methoden zum Formatieren und formatieren in der Konverterlogik verwenden, wenn Ihre Eingabe <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellungen mit einer der [standardmäßigen Format](../base-types/standard-date-and-time-format-strings.md)Zeichenfolgen "R", "l", "O" oder "G" kompatibel sind oder Sie gemäß einem dieser Formate schreiben möchten. Dies ist viel schneller als die Verwendung von `DateTime(Offset).Parse` und `DateTime(Offset).ToString`.

Dieses Beispiel zeigt einen benutzerdefinierten Konverter, der <xref:System.DateTime> Werte gemäß [dem Standardformat "R"](../base-types/standard-date-and-time-format-strings.md#the-rfc1123-r-r-format-specifier)serialisiert und deserialisiert:

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Das Standardformat "R" ist immer 29 Zeichen lang.

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Verwenden von `DateTime(Offset).Parse` als Fall Back für die native Analyse des Serialisierungsprogramms

Wenn Sie in der Regel davon ausgehen, dass Ihre Eingabe <xref:System.DateTime> oder <xref:System.DateTimeOffset> Daten dem erweiterten ISO 8601-1:2019-Profil entsprechen, können Sie die systemeigene Logik des Serialisierungsprogramms verwenden. Sie können auch nur dann einen Fall Back Mechanismus implementieren.
Dieses Beispiel zeigt, dass der Konverter die Daten nach dem Fehlschlagen einer <xref:System.DateTime> Textdarstellung mit <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>erfolgreich mithilfe von <xref:System.DateTime.Parse(System.String)>analysiert.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Beim Schreiben mit <xref:System.Text.Json.Utf8JsonWriter>

Wenn Sie ein benutzerdefiniertes <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellung mit <xref:System.Text.Json.Utf8JsonWriter>schreiben möchten, können Sie die benutzerdefinierte Darstellung in einer <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`oder <xref:System.Text.Json.JsonEncodedText>formatieren und dann an die entsprechende <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A?displayProperty=nameWithType>-oder <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A?displayProperty=nameWithType>-Methode übergeben.

Im folgenden Beispiel wird gezeigt, wie ein benutzerdefiniertes <xref:System.DateTime> Format mit <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>erstellt und dann mit der <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)>-Methode geschrieben werden kann:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Beim Lesen mit <xref:System.Text.Json.Utf8JsonReader>

Wenn Sie eine benutzerdefinierte <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellung mit <xref:System.Text.Json.Utf8JsonReader>lesen möchten, können Sie den Wert des aktuellen JSON-Tokens als <xref:System.String> mithilfe von <xref:System.Text.Json.Utf8JsonReader.GetString>erhalten und den Wert dann mithilfe der benutzerdefinierten Logik analysieren.

Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.DateTimeOffset> Textdarstellung mit <xref:System.Text.Json.Utf8JsonReader.GetString>abgerufen und dann mit <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>analysiert werden kann:

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Das erweiterte ISO 8601-1:2019-Profil in "System. Text. JSON"

### <a name="date-and-time-components"></a>Datums-und Uhrzeit Komponenten

Das in <xref:System.Text.Json> implementierte erweiterte ISO 8601-1:2019-Profil definiert die folgenden Komponenten für Datums-und Uhrzeit Darstellungen. Diese Komponenten werden verwendet, um verschiedene Ebenen der Granularität zu definieren, die beim <xref:System.DateTime> und <xref:System.DateTimeOffset> Darstellungen unterstützt werden.

| Komponente       | Format                      | Beschreibung                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Jahr            | "yyyy"                      | 0001-9999                                                                       |
| Monat           | "MM"                        | 01-12                                                                           |
| Tag             | "dd"                        | 01-28, 01-29, 01-30, 01-31 basierend auf Monat/Jahr                                  |
| Stunde            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Second          | "ss"                        | 00-59                                                                           |
| Zweiter Bruchteil | "FFFFFFF"                   | Mindestens eine Ziffer, maximal 16 Ziffern                                      |
| Zeit Offset     | "K"                         | Entweder "Z" oder "(' + '/'-') HH ': ' mm"                                                |
| Partielle Zeit    | "HH ': ' mm ': ' SS [fffffff]"     | Zeit ohne UTC-Offset-Informationen                                             |
| Vollständiges Datum       | "yyyy'-' mm '-' dd"            | Kalenderdatum                                                                   |
| Vollzeit       | "Partielle Zeit ' K"           | UTC der Tages-oder Ortszeit des Tages mit dem Zeit Offset zwischen Ortszeit und UTC |
| Datum/Uhrzeit       | "' Vollständiges Datum ' nicht ' ' voll Zeit '" | Datum und Uhrzeit des Kalenders, z. b. 2019-07-26t16:59:57-05:00                   |

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

Wenn Dezimaltrennzeichen für Sekunden vorhanden sind, muss mindestens eine Ziffer vorhanden sein. `2019-07-26T00:00:00.` ist nicht zulässig.
Bis zu 16 Dezimalstellen sind zulässig, es werden jedoch nur die ersten sieben analysiert. Alle über diese hinaus werden als null betrachtet.
`2019-07-26T00:00:00.1234567890` werden z. b. so analysiert, als ob es `2019-07-26T00:00:00.1234567`ist.
Dies soll mit der <xref:System.DateTime>-Implementierung kompatibel bleiben, die auf diese Lösung beschränkt ist.

Schaltsekunden werden nicht unterstützt.

### <a name="support-for-formatting"></a>Unterstützung für Formatierung

Die folgenden Ebenen der Granularität sind für die Formatierung definiert:

1. "' Vollständiges Datum ' ' ' partielle Zeit '"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss ' ([der sortierbare Format Bezeichner" s "](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))

        Wird verwendet, um eine <xref:System.DateTime> ohne Sekundenbruchteile und ohne Offset Informationen zu formatieren.

    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." FFFFFFF

        Wird verwendet, um eine <xref:System.DateTime> mit Sekundenbruchteilen, aber ohne Offset Informationen zu formatieren.

2. "Datum/Uhrzeit"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SSZ '

        Wird verwendet, um eine <xref:System.DateTime> ohne Sekundenbruchteile zu formatieren, jedoch mit einem UTC-Offset.

    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffffz "

        Wird verwendet, um eine <xref:System.DateTime> mit Sekundenbruchteilen und einem UTC-Offset zu formatieren.

    3. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm"

        Wird verwendet, um eine <xref:System.DateTime> oder <xref:System.DateTimeOffset> ohne Sekundenbruchteile zu formatieren, jedoch mit einem lokalen Offset.

    4. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffff (' + '/'-') HH ': ' mm '

        Wird verwendet, um eine <xref:System.DateTime> oder <xref:System.DateTimeOffset> mit Sekundenbruchteilen und einem lokalen Offset zu formatieren.

Falls vorhanden, werden maximal 7 Dezimalstellen geschrieben. Dies richtet sich nach der <xref:System.DateTime>-Implementierung, die auf diese Lösung beschränkt ist.
