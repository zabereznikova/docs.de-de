---
title: Aktivieren des Abgleichs von Eigenschaftsnamen mit System.Text.Json ohne Berücksichtigung der Groß-/Kleinschreibung
description: Erfahren Sie, wie Sie in .NET beim Serialisieren in und Deserialisieren aus JSON den Abgleich von Eigenschaftsnamen ohne Berücksichtigung der Groß-/Kleinschreibung aktivieren.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599075"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a>Aktivieren des Abgleichs von Eigenschaftsnamen mit System.Text.Json ohne Berücksichtigung der Groß-/Kleinschreibung

In diesem Artikel erfahren Sie, wie Sie den Abgleich von Eigenschaftsnamen mit dem `System.Text.Json`-Namespace ohne Berücksichtigung der Groß-/Kleinschreibung aktivieren.

## <a name="case-insensitive-property-matching"></a>Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung

Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht. Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:

> [!NOTE]
> Der [Webstandard](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) ist, dass die Groß-/Kleinschreibung nicht berücksichtigt wird.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise. Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
