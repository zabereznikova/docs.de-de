---
ms.openlocfilehash: 13da0ef6155d65fbc894c5747cc36bb3483ba518
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721603"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a>Änderung der Semantik von `(string)null` in Utf8JsonWriter

In .NET Core 3.0 Vorschau 7 wird die NULL-Zeichenfolge wie eine leere Zeichenfolge in <xref:System.Text.Json.Utf8JsonWriter> behandelt. Ab .NET Core 3.0 Vorschau 8 löst die NULL-Zeichenfolge eine Ausnahme aus, wenn sie als Eigenschaftsname verwendet wird, und gibt das JSON-NULL-Token aus, wenn sie als Wert verwendet wird.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 3.0 Vorschau 7 wurde die `null`-Zeichenfolge sowohl beim Schreiben von Eigenschaftsnamen als auch beim Schreiben von Werten als `""` behandelt.  

Ab .NET Core 3.0 Vorschau 8 löst ein `null`-Eigenschaftsname eine `ArgumentNullException` aus, und ein `null`-Wert wird wie ein Aufruf von <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> oder <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType> behandelt.

Betrachten Sie folgenden Code:

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

Bei Ausführung mit .NET Core 3.0 Vorschau 7 generiert der Writer die folgende Ausgabe:

```js
[{"":"","prop2":""},""]
```

Ab . NET Core 3.0 Vorschau 8 löst der Aufruf von `writer.WriteString(propertyName1, propertyValue1)` eine <xref:System.ArgumentNullException> aus.  Wenn `propertyName1 = null` durch `propertyName1 = string.Empty` ersetzt wird, lautet die Ausgabe nun wie folgt:

```js
[{"":null,"prop2":null},null]
```

Diese Änderung wurde vorgenommen, um die Aufrufererwartungen für `null`-Werte besser zu erfüllen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

Beim Schreiben von Eigenschaftsnamen und -Werten mit der <xref:System.Text.Json.Utf8JsonWriter>-Klasse:

- Stellen Sie sicher, dass Zeichenfolgen ungleich `null` als Eigenschaftsnamen verwendet werden.

- Wenn das vorherige Verhalten gewünscht wird, verwenden Sie einen NULL-Zusammenführungsaufruf, beispielsweise `writer.WriteString(propertyName1 ?? "", propertyValue1)`.

- Wenn das Schreiben eines `null`-Literals für einen `null`-Zeichenfolgenwert nicht wünschenswert ist, verwenden Sie einen NULL-Zusammenführungsaufruf, beispielsweise `writer.WriteString(propertyName2, propertyValue2 ?? "")`.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
