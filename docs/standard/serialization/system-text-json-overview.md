---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: In dieser Übersicht wird die Funktionalität des System.Text.Json-Namespace zum Serialisieren in JSON und Deserialisieren aus JSON in .NET beschrieben.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009884"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="5770a-103">JSON-Serialisierung und -Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) in .NET: Überblick</span><span class="sxs-lookup"><span data-stu-id="5770a-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="5770a-104">Der `System.Text.Json`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="5770a-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="5770a-105">Beim Entwerfen der Bibliothek wurde mehr Wert auf eine hohe Leistung und eine geringe Arbeitsspeicherbelegung gelegt als auf eine große Bandbreite von Features.</span><span class="sxs-lookup"><span data-stu-id="5770a-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="5770a-106">Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die am häufigsten verwendete Codierung für Daten im Web und Dateien auf Datenträgern.</span><span class="sxs-lookup"><span data-stu-id="5770a-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="5770a-107">Die Bibliothek stellt außerdem Klassen für die Arbeit mit einem In-Memory-Dokumentobjektmodell (DOM) bereit.</span><span class="sxs-lookup"><span data-stu-id="5770a-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="5770a-108">Diese Funktion ermöglicht einen zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder -Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5770a-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="5770a-109">Abrufen der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="5770a-109">How to get the library</span></span>

* <span data-ttu-id="5770a-110">Die Bibliothek ist als Teil des gemeinsamen Frameworks für .NET Core 3.0 und höhere Versionen integriert.</span><span class="sxs-lookup"><span data-stu-id="5770a-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="5770a-111">Installieren Sie für frühere Framework-Versionen das NuGet-Paket [System.Text.Json](https://www.nuget.org/packages/System.Text.Json).</span><span class="sxs-lookup"><span data-stu-id="5770a-111">For earlier framework versions, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="5770a-112">Das Paket unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5770a-112">The package supports:</span></span>

  * <span data-ttu-id="5770a-113">.NET Standard 2.0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="5770a-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="5770a-114">.NET Framework 4.7.2 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="5770a-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="5770a-115">.NET Core 2.0, 2.1 und 2.2</span><span class="sxs-lookup"><span data-stu-id="5770a-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5770a-116">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5770a-116">Additional resources</span></span>

* [<span data-ttu-id="5770a-117">Serialisierung und Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) von JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="5770a-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="5770a-118">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="5770a-118">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="5770a-119">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="5770a-119">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="5770a-120">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="5770a-120">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="5770a-121">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5770a-121">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="5770a-122">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="5770a-122">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="5770a-123">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="5770a-123">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="5770a-124">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="5770a-124">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="5770a-125">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="5770a-125">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="5770a-126">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5770a-126">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="5770a-127">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="5770a-127">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="5770a-128">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="5770a-128">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="5770a-129">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="5770a-129">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="5770a-130">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5770a-130">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="5770a-131">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5770a-131">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="5770a-132">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="5770a-132">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="5770a-133">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="5770a-133">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
