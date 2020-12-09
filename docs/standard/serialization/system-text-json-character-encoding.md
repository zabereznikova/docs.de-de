---
title: Anpassen der Zeichencodierung mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET die Zeichencodierung beim Serialisieren in und Deserialisieren aus JSON anpassen können.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f6a50a3ca2a5e871294cf7c056cbf197a61cd668
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439806"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a>Anpassen der Zeichencodierung mit System.Text.Json

Standardmäßig escapet der Serialisierer alle Nicht-ASCII-Zeichen. Das heißt, dass sie durch `\uxxxx` ersetzt werden, wobei `xxxx` der Unicode-Code des Zeichens ist. Wenn die `Summary`-Eigenschaft im folgenden JSON-Code beispielsweise auf Kyrillisch `жарко` festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a>Serialisieren von Sprachzeichensätzen

Zum Serialisieren der Zeichensätze von mindestens einer Sprache ohne zu escapen geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) an, wenn Sie eine Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> erstellen, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

Mit diesem Code werden weder kyrillische noch griechische Zeichen escapet. Wenn die `Summary`-Eigenschaft auf Kyrillisch `жарко` festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Um alle Sprachensätze ohne zu escapen zu serialisieren, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

## <a name="serialize-specific-characters"></a>Serialisieren bestimmter Zeichen

Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne dass sie escapet werden. Im folgenden Beispiel werden nur die ersten zwei Zeichen von `жарко` serialisiert:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

Hier sehen Sie eine JSON-Beispiel, das vom vorangehenden Code erzeugt wird:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a>Serialisieren aller Zeichen

Um das Escapen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> Im Vergleich zum Standardencoder ist der `UnsafeRelaxedJsonEscaping`-Encoder weniger streng beim Zulassen von Zeichen, ohne sie zu escapen:
>
> * Er escapet keine HTML-abhängigen Zeichen wie `<`, `>`, `&` und `'`.
> * Er bietet keine zusätzlichen, tief greifenden Abwehrmaßnahmen gegen solche Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffe (Veröffentlichung von Informationen), die von einem Client und Server, die sich nicht auf einen *Zeichensatz* einigen können, verursacht werden können.
>
> Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretieren wird. Beispielsweise können Sie ihn verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet. Gestatten Sie niemals, dass die `UnsafeRelaxedJsonEscaping`-Rohausgabe in eine HTML-Seite oder ein `<script>`-Element ausgegeben wird.

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierungsmodule](write-custom-serializer-deserializer.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
