---
title: Zulassen einiger Arten von ungültigem JSON-Code mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Kommentare, nachfolgende Kommas und Zahlen in Anführungszeichen beim Serialisieren in und Deserialisieren aus JSON zulassen.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 60cbb98bb65ee5c1ffdd3043e42a04004530a115
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439766"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a>Zulassen einiger Arten von ungültigem JSON-Code mit System.Text.Json

In diesem Artikel erfahren Sie, wie Sie Kommentare, nachfolgende Kommas und Zahlen in Anführungszeichen in JSON zulassen, und wie Sie Zahlen als Zeichenfolgen schreiben.

## <a name="allow-comments-and-trailing-commas"></a>Zulassen von Kommentaren und nachfolgenden Kommas

Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig. Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.
Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest. Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a>Zulassen oder Schreiben von Zahlen in Anführungszeichen

::: zone pivot="dotnet-5-0"

Einige Serialisierungsmodule codieren Zahlen als (in Anführungszeichen eingeschlossene) JSON-Zeichenfolgen.

Beispiel:

```json
{
    "DegreesCelsius": "23"
}
```

Verwenden Sie anstelle von

```json
{
    "DegreesCelsius": 23
}
```

Um Zahlen in Anführungszeichen zu serialisieren oder Zahlen in Anführungszeichen im gesamten Graphen des Eingabeobjekts zu akzeptieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> wie im folgenden Beispiel gezeigt fest:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

Wenn Sie `System.Text.Json` indirekt über ASP.NET Core verwenden, sind beim Deserialisieren Zahlen in Anführungszeichen erlaubt, da ASP.NET Core [Webstandardoptionen](xref:System.Text.Json.JsonSerializerDefaults.Web) angibt.

Um Zahlen in Anführungszeichen für bestimmte Eigenschaften, Felder oder Typen zuzulassen oder zu schreiben, verwenden Sie das Attribut [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`System.Text.Json` in .NET Core 3.1 unterstützt keine Serialisierung oder Deserialisierung von Zahlen in Anführungszeichen. Weitere Informationen finden Sie unter [Zulassen oder Schreiben von Zahlen in Anführungszeichen](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).
::: zone-end

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
