---
title: Instanziieren von JsonSerializerOptions mit System.Text.Json
description: Erfahren Sie, wie Sie JsonSerializerOptions-Instanzen durch Kopieren vorhandener Instanzen oder mit Webstandards instanziieren können.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439810"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>Instanziieren von JsonSerializerOptions-Instanzen mit System.Text.Json

In diesem Artikel erfahren Sie, wie Sie <xref:System.Text.Json.JsonSerializerOptions>-Instanzen durch Kopieren vorhandener Instanzen oder mit Webstandards instanziieren können.

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
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
