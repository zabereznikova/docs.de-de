---
title: Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierungsmodule mit System.Text.Json
description: Erfahren Sie, wie Sie mit dem System.Text.Json-Namespace benutzerdefinierte Serialisierungsmodule und Deserialisierungsmodule für JSON schreiben.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a01d3c8dd18c114ea1c3aabc402bc841a6025ffe
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439805"
---
# <a name="how-to-write-custom-serializers-and-deserializers-with-no-locsystemtextjson"></a>Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierungsmodule mit System.Text.Json

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>` gelesen wird. Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann. Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` verdeckt.

Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben. Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann. Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` verdeckt.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mithilfe von `Utf8JsonReader` ein schreibgeschütztes Dokumentobjektmodell (DOM) zu erstellen. Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden. Der `JsonElement`-Typ stellt Array- und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen bereit. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.

## <a name="use-jsondocument-for-access-to-data"></a>Verwenden von „JsonDocument“ für den Zugriff auf Daten

Das folgende Beispiel zeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades1":::

Der vorangehende Code:

* Setzt voraus, dass sich der zu analysierende JSON-Code in einer Zeichenfolge namens `jsonString` befindet.
* Berechnet eine durchschnittliche Note für Objekte in einem `Students`-Array, die eine `Grade`-Eigenschaft besitzen.
* Weist Kursteilnehmern, die keine Note haben, eine Standardnote von 70 zu.
* Zählt Kursteilnehmer durch Inkrementieren einer `count`-Variablen bei jeder Iteration. Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A> aufzurufen, wie im folgenden Beispiel gezeigt:

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades2":::

Im Folgenden finden Sie ein Beispiel für das JSON, das von diesem Code verarbeitet wird:

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-jsondocument-to-write-json"></a>Verwenden von JsonDocument zum Schreiben von JSON

Das folgende Beispiel veranschaulicht, wie JSON aus einem <xref:System.Text.Json.JsonDocument> geschrieben wird:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs" id="Serialize":::

Der vorangehende Code:

* Liest eine JSON-Datei, lädt die Daten in ein `JsonDocument` und schreibt (übersichtlich) formatierten JSON-Code in eine Datei.
* Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.
* Ruft nach Abschluss <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf. Eine Alternative ist, den Writer automatisch zu leeren, wenn er entsorgt wird.

Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die von dem Beispielcode verarbeitet werden soll:

:::code language="json" source="snippets/system-text-json-how-to/csharp/Grades.json":::

Das Ergebnis ist die folgende, übersichtlich formatierte JSON-Ausgabe:

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-utf8jsonwriter"></a>Verwenden von „Utf8JsonWriter“

Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonWriter>-Klasse veranschaulicht:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs" id="Serialize":::

## <a name="use-utf8jsonreader"></a>Verwenden von „Utf8JsonReader“

Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonReader>-Klasse veranschaulicht:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs" id="Deserialize":::

Der vorangehende Code setzt voraus, dass es sich bei der `jsonUtf8`-Variablen um ein Bytearray handelt, das gültigen, UTF-8-codierten JSON-Code enthält.

### <a name="filter-data-using-utf8jsonreader"></a>Filtern von Daten mithilfe von „Utf8JsonReader“

Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs":::

Eine asynchrone Version dieses Beispiels finden Sie im [.NET-Beispiel-JSON-Projekt](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs).

Der vorangehende Code:

* Setzt voraus, dass der JSON-Code ein Array von Objekten enthält, und dass jedes Objekt eine Eigenschaft „name“ vom Typ „string“ (Zeichenfolge) enthalten kann.
* Zählt Objekte und „name“-Eigenschaftswerte, die auf „University“ enden.
* Setzt voraus, dass die Datei UTF-16-codiert ist und transcodiert sie in UTF-8. Eine UTF-8-codierte Datei kann mithilfe des folgenden Codes direkt in ein `ReadOnlySpan<byte>` gelesen werden:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Wenn die Datei eine UTF-8-Bytereihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader` übergeben, da der Reader Text erwartet. Andernfalls wird die BOM als ungültiges JSON betrachtet, und der Reader löst eine Ausnahme aus.

Im Folgenden finden Sie ein JSON-Beispiel, das der voranstehende Code lesen kann. Die resultierende Zusammenfassungsmeldung lautet „2 out of 2 have names that end with ‚University‘“ (2 von 4 besitzen Namen, die auf „University“ enden):

:::code language="json" source="snippets/system-text-json-how-to/csharp/Universities.json":::

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Lesen aus einem Stream mithilfe von Utf8JsonReader

Wenn Sie eine große Datei (z. B. ein Gigabyte oder mehr) lesen, möchten Sie die gesamte Datei vielleicht nicht auf einmal in den Arbeitsspeicher laden müssen. In diesem Szenario können Sie einen <xref:System.IO.FileStream> verwenden.

Wenn Sie einen `Utf8JsonReader` zum Lesen aus einem Stream verwenden, gelten die folgenden Regeln:

* Der Puffer, der die partielle JSON-Nutzlast enthält, muss mindestens so groß wie das größte JSON-Token darin sein, damit der Reader vorankommen kann.
* Der Puffer muss mindestens so groß wie die größte Sequenz von Leerraum innerhalb der JSON-Nutzdaten sein.
* Der Reader verfolgt die gelesenen Daten nicht nach, bis er den nächsten <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in der JSON-Nutzlast vollständig gelesen hat. Wenn im Puffer noch Bytes vorhanden sind, müssen Sie sie wieder dem Reader übergeben. Sie können <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> verwenden, um zu bestimmen, wie viele Bytes übrig bleiben.

Im folgenden Code wird veranschaulicht, wie aus einem Stream gelesen wird. Das Beispiel zeigt einen <xref:System.IO.MemoryStream>. Ähnlicher Code funktioniert mit einem <xref:System.IO.FileStream>, es sei denn, der `FileStream` enthält am Anfang eine UTF-8-BOM. In diesem Fall müssen Sie diese drei Bytes aus dem Puffer entfernen, bevor Sie die verbleibenden Bytes an den `Utf8JsonReader` übergeben. Andernfalls würde der Reader eine Ausnahme auslösen, da die BOM nicht als gültiger Teil des JSON-Codes angesehen wird.

Der Beispielcode beginnt mit einem 4 KB großen Puffer und verdoppelt die Puffergröße jedes Mal, wenn festgestellt wird, dass die Größe nicht ausreicht, um ein komplettes JSON-Token aufzunehmen. Dies ist erforderlich, damit der Reader mit den JSON-Nutzdaten vorankommt. Das JSON-Beispiel im Codeausschnitt löst nur dann eine Erhöhung der Puffergröße aus, wenn Sie eine sehr geringe Anfangspuffergröße festlegen, z. B. 10 Bytes. Die `Console.WriteLine`-Anweisungen zeigen Ursache und Auswirkung der Puffergrößenerhöhungen, wenn Sie die Anfangspuffergröße auf 10 festlegen. Bei der Anfangspuffergröße von 4 KB wird das gesamte JSON-Beispiel von jeder `Console.WriteLine` angezeigt, und die Puffergröße muss nie erhöht werden.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs":::

Im vorherigen Beispiel wurde keine Pufferobergrenze festgelegt. Bei übermäßiger Tokengröße kann bei dem Code ein <xref:System.OutOfMemoryException>-Ausnahmefehler auftreten. Dies kann vorkommen, wenn der JSON-Code ein ungefähr 1 GB großes oder größeres Token enthält, da das Token bei Verdoppelung von 1 GB nicht mehr in einen `int32`-Puffer passt.

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Anpassen der Zeichencodierung](system-text-json-character-encoding.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
