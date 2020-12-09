---
title: Beibehalten von Verweisen mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET beim Serialisieren in und Deserialisieren aus JSON Verweise beibehalten und Zirkelbezüge behandeln.
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
ms.openlocfilehash: 9254ca261c7d748c04c311fa56359014f752ff31
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439789"
---
# <a name="how-to-handle-circular-references-with-no-locsystemtextjson"></a>Behandeln von Zirkelbezügen mit System.Text.Json

In diesem Artikel erfahren Sie, wie Zirkelbezüge mit dem `System.Text.Json`-Namespace behandelt werden.

## <a name="preserve-references-and-handle-circular-references"></a>Beibehalten von Verweisen und Behandeln von Zirkelbezügen

::: zone pivot="dotnet-5-0"

Um Verweise beizubehalten und Zirkelbezüge zu behandeln, legen Sie <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> auf <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> fest. Diese Einstellung bewirkt folgendes Verhalten:

* Beim Serialisieren:

  Beim Schreiben komplexer Typen schreibt das Serialisierungsmodul auch Metadateneigenschaften (`$id`, `$values` und `$ref`).

* Beim Deserialisieren:

  Metadaten werden erwartet (obwohl nicht zwingend erforderlich), und der Deserialisierer versucht, sie zu verstehen.

Der folgende Code veranschaulicht die Verwendung der Einstellung `Preserve`.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

Dieses Feature kann nicht verwendet werden, um Wert- oder unveränderliche Typen beizubehalten. Bei der Deserialisierung wird die Instanz eines unveränderlichen Typs erstellt, nachdem die gesamten Nutzdaten gelesen wurden. Daher wäre es unmöglich, dieselbe Instanz zu deserialisieren, wenn ein Verweis darauf in den JSON-Nutzdaten vorhanden ist.

Für Werttypen, unveränderliche Typen und Arrays werden keine Verweismetadaten serialisiert. Bei der Deserialisierung wird eine Ausnahme ausgelöst, wenn `$ref` oder `$id` gefunden wird. Werttypen ignorieren jedoch `$id` (und `$values` im Falle von Sammlungen), um die Deserialisierung von Nutzdaten zu ermöglichen, die mit Newtonsoft.Json serialisiert wurden.  Newtonsoft.Json serialisiert die Metadaten für solche Typen.

Um festzustellen, ob Objekte gleich sind, wird <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> von System.Text.Json verwendet. Dabei wird beim Vergleich zweier Objektinstanzen die Verweisgleichheit (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) anstelle der Wertgleichheit (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) verwendet.

Weitere Informationen zur Serialisierung und Deserialisierung von Verweisen finden Sie unter <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.

Die <xref:System.Text.Json.Serialization.ReferenceResolver>-Klasse definiert das Verhalten bei Beibehaltung von Verweisen für Serialisierung und Deserialisierung. Erstellen Sie eine abgeleitete Klasse, um benutzerdefiniertes Verhalten anzugeben. Ein Beispiel finden Sie unter [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json in .NET Core 3.1 unterstützt nur die Serialisierung nach Wert und löst bei Zirkelbezügen eine Ausnahme aus.
::: zone-end

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
