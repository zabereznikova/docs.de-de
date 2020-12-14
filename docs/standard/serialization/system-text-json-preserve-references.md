---
title: Beibehalten von Verweisen mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET beim Serialisieren in und Deserialisieren aus JSON Verweise beibehalten und Zirkelbezüge behandeln.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d358c953c0979ca097c080fcd750d5ef95b07de0
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008733"
---
# <a name="how-to-preserve-references-and-handle-circular-references-with-no-locsystemtextjson"></a>Beibehalten von Verweisen und Korrigieren von Zirkelbezügen mit System.Text.Json

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
* [Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten](system-text-json-how-to.md)
* [Instanziieren von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Anpassen der Zeichencodierung](system-text-json-character-encoding.md)
* [Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer](write-custom-serializer-deserializer.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [Unterstützung von DateTime und DateTimeOffset](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
