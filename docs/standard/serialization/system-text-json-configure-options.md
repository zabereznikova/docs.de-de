---
title: Instanziieren von JsonSerializerOptions mit System.Text.Json
description: Hier erfahren Sie, wie Sie Leistungsprobleme vermeiden und vorhandene Konstruktoren für JsonSerializerOptions-Instanzen verwenden.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009832"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>Instanziieren von JsonSerializerOptions-Instanzen mit System.Text.Json

In diesem Artikel wird erläutert, wie Sie Leistungsprobleme vermeiden, die bei der Verwendung von <xref:System.Text.Json.JsonSerializerOptions> auftreten können. Zudem wird die Verwendung der vorhandenen parametrisierten Konstruktoren veranschaulicht.

## <a name="reuse-jsonserializeroptions-instances"></a>Wiederverwenden von JsonSerializerOptions-Instanzen

Wenn Sie `JsonSerializerOptions` wiederholt mit den gleichen Optionen verwenden, sollten Sie nicht bei jeder Verwendung eine neue `JsonSerializerOptions`-Instanz erstellen. Verwenden Sie für jeden Aufruf dieselbe Instanz. Dieser Leitfaden gilt für Code, den Sie für benutzerdefinierte Konverter und Aufrufe von <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> oder <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> schreiben.

Der folgende Code veranschaulicht die Leistungseinbußen bei der Verwendung neuer JsonSerializerOptions-Instanzen.

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

Der vorangehende Code serialisiert ein kleines Objekt 100.000-mal mit derselben JsonSerializerOptions-Instanz. Anschließend wird dasselbe Objekt noch einmal genauso oft serialisiert, doch jedes Mal wird eine neue JsonSerializerOptions-Instanz erstellt. Der Laufzeitunterschied liegt bei 190 Millisekunden im Vergleich zu 40.140 Millisekunden. Wenn Sie mehr Iterationen durchführen, wird der Unterschied sogar noch größer.

Das Serialisierungsmodul durchläuft während der ersten Serialisierung jedes Typs im Objektgraph eine Aufwärmphase, wenn eine neue JsonSerializerOptions-Instanz übergeben wird. Diese Aufwärmphase beinhaltet eine Zwischenspeicherung der Metadaten, die für die Serialisierung benötigt werden. Diese Metadaten enthalten beispielsweise Delegaten für Eigenschaftengetter und -setter, Konstruktorargumente oder angegebene Attribute. Dieser Metadatencache wird in der JsonSerializerOptions-Instanz gespeichert. Die Aufwärmphase und die Cacheerstellung erfolgen auch bei der Deserialisierung.

Die Größe des Metadatencaches in einer `JsonSerializerOptions`-Instanz hängt von der Anzahl der zu serialisierenden Typen ab. Wenn Sie viele verschiedene Typen (z. B. dynamisch generierte Typen) an das Serialisierungsmodul übergeben, nimmt die Cachegröße weiter zu, und eine `OutOfMemoryException`-Ausnahme kann auftreten.

## <a name="copy-jsonserializeroptions"></a>Kopieren von JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)), mit dem Sie eine neue Instanz mit den Optionen einer vorhandenen Instanz erstellen können, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Ein Konstruktor des Typs `JsonSerializerOptions`, der eine vorhandene Instanz verwendet, steht in .NET Core 3.1 nicht zur Verfügung.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>Webstandardwerte für JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), mit dem Sie eine neue Instanz mit den Standardoptionen erstellen können, die ASP.NET Core für Web-Apps verwendet (siehe folgendes Beispiel):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

Ein Konstruktor des Typs `JsonSerializerOptions`, der eine Gruppe von Standardwerten angibt, steht in .NET Core 3.1 nicht zur Verfügung.
::: zone-end

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten](system-text-json-how-to.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten von Verweisen](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Anpassen der Zeichencodierung](system-text-json-character-encoding.md)
* [Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer](write-custom-serializer-deserializer.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [Unterstützung von DateTime und DateTimeOffset](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
