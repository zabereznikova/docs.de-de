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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008824"
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
* [Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten](system-text-json-how-to.md)
* [Instanziieren von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten von Verweisen](system-text-json-preserve-references.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Anpassen der Zeichencodierung](system-text-json-character-encoding.md)
* [Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer](write-custom-serializer-deserializer.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [Unterstützung von DateTime und DateTimeOffset](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
