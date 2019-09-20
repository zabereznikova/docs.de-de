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
ms.openlocfilehash: 83b1b3a7db63154dccc07325b1a1948a2db3953a
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151826"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Unterstützung von DateTime und DateTimeOffset in System.Text.Json

Die System. Text. JSON-Bibliothek analysiert und schreibt <xref:System.DateTime> <xref:System.DateTimeOffset> Werte gemäß dem erweiterten ISO 8601:-2019-Profil.
[Konverter](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) bieten benutzerdefinierte Unterstützung für das Serialisieren und Deserialisieren mit <xref:System.Text.Json.JsonSerializer>.
Benutzerdefinierte Unterstützung kann auch bei Verwendung <xref:System.Text.Json.Utf8JsonReader> von <xref:System.Text.Json.Utf8JsonWriter>und implementiert werden.

## <a name="support-for-the-iso-8601-12019-format"></a>Unterstützung für das ISO 8601-1:2019-Format

Die <xref:System.Text.Json.JsonSerializer>Typen <xref:System.Text.Json.Utf8JsonReader>, ,<xref:System.Text.Json.Utf8JsonWriter>und <xref:System.DateTimeOffset> analysieren und schreiben<xref:System.DateTime> -und-Textdarstellungen gemäß dem erweiterten Profil des ISO 8601-1:2019-Formats, z. b. 2019-07-26t16. <xref:System.Text.Json.JsonElement> : 59:57-05:00.

<xref:System.DateTime>- <xref:System.DateTimeOffset> und-Daten können mit <xref:System.Text.Json.JsonSerializer>serialisiert werden:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

Die Deserialisierung kann auch mit <xref:System.Text.Json.JsonSerializer>erfolgen:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Mit den Standardoptionen müssen <xref:System.DateTime> Eingabe <xref:System.DateTimeOffset> -und Textdarstellungen dem erweiterten ISO 8601-1:2019-Profil entsprechen.
Der Versuch, Darstellungen zu deserialisieren, die nicht dem Profil entsprechen <xref:System.Text.Json.JsonSerializer> , bewirkt, <xref:System.Text.Json.JsonException>dass Folgendes ausgelöst wird:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

Bietet strukturierten Zugriff auf den Inhalt einer JSON-Nutzlast, einschließlich <xref:System.DateTime> der- <xref:System.DateTimeOffset> und-Darstellungen. <xref:System.Text.Json.JsonDocument> Im folgenden Beispiel wird gezeigt, wie bei einer Sammlung von Temperaturen die Durchschnittstemperatur am Montag berechnet werden kann:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Wenn Sie versuchen, die durchschnittliche Temperatur bei einer Nutzlast mit nicht kompatiblen <xref:System.DateTime> Darstellungen zu berechnen <xref:System.Text.Json.JsonDocument> , wird eine <xref:System.FormatException>ausgelöst:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Die Schreibvorgänge <xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> auf niedrigerer Ebene und <xref:System.DateTimeOffset> Daten:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader><xref:System.DateTime> analysiert und<xref:System.DateTimeOffset> Daten:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Wenn Sie versuchen, nicht kompatible Formate mit <xref:System.Text.Json.Utf8JsonReader> zu lesen, wird eine <xref:System.FormatException>ausgelöst:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Benutzerdefinierte unter <xref:System.DateTime> Stützung für und<xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Bei Verwendung von<xref:System.Text.Json.JsonSerializer>

Wenn Sie möchten, dass das Serialisierungsprogramm eine benutzerdefinierte Formatierung oder Formatierung durchführt, können Sie [benutzerdefinierte Konverter](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)implementieren.
Hier sind einige Beispiele:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Verwenden `DateTime(Offset).Parse` von und`DateTime(Offset).ToString`

Wenn Sie die Formate der Eingabe <xref:System.DateTime> -oder <xref:System.DateTimeOffset> Textdarstellungen nicht ermitteln können, können Sie die `DateTime(Offset).Parse` -Methode in der konverterleselogik verwenden. Dies ermöglicht Ihnen die Verwendung von. Umfassende Unterstützung für das Auswerten verschiedener <xref:System.DateTime> -und <xref:System.DateTimeOffset> -Textformate, einschließlich nicht-ISO 8601-Zeichen folgen und ISO 8601-Formaten, die nicht dem erweiterten ISO 8601-1:2019-Profil entsprechen. Diese Vorgehensweise ist erheblich weniger leistungsfähig als die native Implementierung des Serialisierungsprogramms.

Zum Serialisieren können Sie die-Methode `DateTime(Offset).ToString` in der konverterschreiblogik verwenden. Dies ermöglicht es Ihnen, <xref:System.DateTime> mit <xref:System.DateTimeOffset> einem beliebigen [Standardformat für Datum und Uhrzeit](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)und den [benutzerdefinierten Datums-und Uhrzeit Formaten](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)zu schreiben und Werte zu verwenden.
Dies ist auch bedeutend weniger leistungsfähiger als die systemeigene Implementierung des Serialisierungsprogramms.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Beim Implementieren <xref:System.Text.Json.Serialization.JsonConverter%601>von, `T` und <xref:System.DateTime>ist der `typeToConvert` -Parameter immer `typeof(DateTime)`.
Der-Parameter ist nützlich für die Behandlung von polymorphen Fällen und bei der Verwendung `typeof(T)` von Generika, um die Leistung zu erzielen.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Verwenden <xref:System.Buffers.Text.Utf8Parser> von und<xref:System.Buffers.Text.Utf8Formatter>

Sie können schnelle UTF-8-basierte Methoden zum Formatieren und formatieren in der Konverterlogik verwenden <xref:System.DateTime> , <xref:System.DateTimeOffset> Wenn Ihre Eingabe-oder Textdarstellungen mit einer der [standardmäßigen Format](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)Zeichenfolgen "R", "l", "O" oder "G" kompatibel sind, oder Sie möchten Schreiben Sie gemäß einem dieser Formate. Dies ist viel schneller als die `DateTime(Offset).Parse` Verwendung `DateTime(Offset).ToString`von und.

Dieses Beispiel zeigt einen benutzerdefinierten Konverter, der Werte gemäß <xref:System.DateTime> [dem Standardformat "R"](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)serialisiert und deserialisiert:

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Das Standardformat "R" ist immer 29 Zeichen lang.

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Verwenden `DateTime(Offset).Parse` von als Fall Back für die native Analyse des Serialisierungsprogramms

Wenn Sie in der Regel davon <xref:System.DateTime> ausgehen <xref:System.DateTimeOffset> , dass die Eingabe oder die Daten dem erweiterten ISO 8601-1:2019-Profil entsprechen, können Sie die systemeigene Logik des Serialisierungsprogramms verwenden. Sie können auch nur dann einen Fall Back Mechanismus implementieren.
Dieses Beispiel zeigt, dass der Konverter die Daten mithilfe <xref:System.DateTime> <xref:System.DateTime.Parse(System.String)>von erfolgreich analysiert, <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>nachdem eine Textdarstellung mit nicht analysiert wurde.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Beim Schreiben mit<xref:System.Text.Json.Utf8JsonWriter>

Wenn Sie <xref:System.DateTime> eine benutzerdefinierte oder <xref:System.DateTimeOffset> Textdarstellung mit <xref:System.Text.Json.Utf8JsonWriter>schreiben möchten, können <xref:System.String>Sie die benutzerdefinierte Darstellung in, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`oder <xref:System.Text.Json.JsonEncodedText>formatieren und dann an die entsprechende [Utf8JsonWriter. Beschreib testringvalue](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0) -Methode oder [Utf8JsonWriter. Write-String](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0) -Methode.

Im folgenden Beispiel wird gezeigt, wie <xref:System.DateTime> ein benutzerdefiniertes Format <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>mit erstellt und dann mit <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> der-Methode geschrieben werden kann:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Beim Lesen mit<xref:System.Text.Json.Utf8JsonReader>

Wenn Sie eine benutzerdefinierte <xref:System.DateTime> oder <xref:System.DateTimeOffset> Textdarstellung mit <xref:System.Text.Json.Utf8JsonReader>lesen möchten, können Sie den Wert <xref:System.String> des aktuellen JSON-Tokens als verwenden <xref:System.Text.Json.Utf8JsonReader.GetString>und dann den Wert mithilfe der benutzerdefinierten Logik analysieren.

Im folgenden Beispiel wird gezeigt, wie <xref:System.DateTimeOffset> eine benutzerdefinierte Textdarstellung mithilfe <xref:System.Text.Json.Utf8JsonReader.GetString>von abgerufen werden kann. <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>anschließend wird Sie mit analysiert:

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Das erweiterte ISO 8601-1:2019-Profil in "System. Text. JSON"

### <a name="date-and-time-components"></a>Datums-und Uhrzeit Komponenten

Das in <xref:System.Text.Json> implementierte erweiterte ISO 8601-1:2019-Profil definiert die folgenden Komponenten für Datums-und Uhrzeit Darstellungen. Diese Komponenten werden verwendet, um verschiedene Granularitätsebene zu definieren, die <xref:System.DateTime> bei <xref:System.DateTimeOffset> der Verarbeitung und Formatierung und Darstellungen unterstützt werden.

| Komponente       | Format                      | Beschreibung                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Jahr            | "yyyy"                      | 0001-9999                                                                       |
| Monat           | "MM"                        | 01-12                                                                           |
| Day             | "dd"                        | 01-28, 01-29, 01-30, 01-31 basierend auf Monat/Jahr                                  |
| Hour            | "HH"                        | 00-23                                                                           |
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
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss ' ([der sortierbare Format Bezeichner" s "](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))
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
Beispielsweise wird `2019-07-26T00:00:00.1234567890` so analysiert, als wäre `2019-07-26T00:00:00.1234567`es.
Dies soll mit der <xref:System.DateTime> Implementierung kompatibel bleiben, die auf diese Lösung beschränkt ist.

Schaltsekunden werden nicht unterstützt.

### <a name="support-for-formatting"></a>Unterstützung für Formatierung

Die folgenden Ebenen der Granularität sind für die Formatierung definiert:

1. "' Vollständiges Datum ' ' ' partielle Zeit '"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss ' ([der sortierbare Format Bezeichner" s "](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))

        Wird verwendet, um <xref:System.DateTime> einen ohne Sekundenbruchteile und ohne Offset Informationen zu formatieren.

    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." FFFFFFF

        Wird verwendet, um <xref:System.DateTime> eine mit Sekundenbruchteilen, aber ohne Offset Informationen zu formatieren.

2. "Datum/Uhrzeit"
    1. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SSZ '

        Wird verwendet, um <xref:System.DateTime> eine <xref:System.DateTimeOffset> oder ohne Sekundenbruchteile zu formatieren, jedoch mit einem UTC-Offset.

    2. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffffz "

        Wird zum Formatieren <xref:System.DateTime> von <xref:System.DateTimeOffset> oder mit Sekundenbruchteilen und einem UTC-Offset verwendet.

    3. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm"

        Wird verwendet, um <xref:System.DateTime> eine <xref:System.DateTimeOffset> oder ohne Sekundenbruchteile zu formatieren, jedoch mit einem lokalen Offset.

    4. "yyyy'-' mm'-' dd ' HH ': ' mm ': ' ss '." Fffffff (' + '/'-') HH ': ' mm '

        Wird zum Formatieren <xref:System.DateTime> von <xref:System.DateTimeOffset> oder mit Sekundenbruchteilen und mit einem lokalen Offset verwendet.

Falls vorhanden, werden maximal 7 Dezimalstellen geschrieben. Dies richtet sich nach der <xref:System.DateTime> Implementierung, die auf diese Lösung beschränkt ist.
