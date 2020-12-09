---
title: Verwenden unveränderlicher Typen und nicht öffentlicher Accessoren mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET unveränderliche Typen und nicht öffentliche Accessoren beim Serialisieren in und Deserialisieren aus JSON verwenden können.
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
ms.openlocfilehash: d3e61d44ce22b7f50838b6d3ba9cf64004bd3725
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439770"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a>Verwenden unveränderlicher Typen und nicht öffentlicher Accessoren mit System.Text.Json

In diesem Artikel erfahren Sie, wie Sie unveränderliche Typen, z. B. Datensätze, mit dem `System.Text.Json`-Namespace verwenden.

## <a name="immutable-types-and-records"></a>Unveränderliche Typen und Datensätze

::: zone pivot="dotnet-5-0"
`System.Text.Json` kann einen parametrisierten Konstruktor verwenden, der es ermöglicht, eine unveränderliche Klasse oder Struktur zu deserialisieren. Wenn für eine Klasse der einzige Konstruktor ein parametrisierter ist, wird dieser Konstruktor verwendet. Geben Sie für eine Struktur oder Klasse mit mehreren Konstruktoren den zu verwendenden Konstruktor an, indem Sie das Attribut [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) anwenden. Wenn das Attribut nicht verwendet wird, wird, sofern vorhanden, stets ein öffentlicher parameterloser Konstruktor verwendet. Das Attribut kann nur mit öffentlichen Konstruktoren verwendet werden. Im folgenden Beispiel wird das Attribut `[JsonConstructor]` hinzugefügt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

Datensätze in C# 9 werden, wie im folgenden Beispiel gezeigt, ebenfalls unterstützt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

Informationen zu Typen, die unveränderlich sind, weil alle ihre Eigenschaftssetter nicht öffentlich sind, finden Sie im folgenden Abschnitt über [nicht öffentliche Eigenschaftenaccessoren](#non-public-property-accessors).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` und C# 9-Datensätze werden in .NET Core 3.1 nicht unterstützt.
::: zone-end

## <a name="non-public-property-accessors"></a>Nicht öffentliche Eigenschaftenaccessoren

::: zone pivot="dotnet-5-0"
Um die Verwendung eines nicht öffentlichen Eigenschaftenaccessors zu aktivieren, verwenden Sie das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Nicht öffentliche Eigenschaftenaccessoren werden in .NET Core 3.1 nicht unterstützt. Weitere Informationen finden Sie im Artikel [Migration von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).
::: zone-end

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten zirkulärer Verweise](system-text-json-preserve-references.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
