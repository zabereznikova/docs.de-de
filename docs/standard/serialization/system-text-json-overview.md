---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: In dieser Übersicht wird die Funktionalität des :::no-loc(System.Text.Json):::-Namespace zum Serialisieren in JSON und Deserialisieren aus JSON in .NET beschrieben.
ms.date: 01/10/2020
no-loc:
- ':::no-loc(System.Text.Json):::'
- ':::no-loc(Newtonsoft.Json):::'
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d8bd5bcf78db534bd722972db01253cbd13a7a06
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282401"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="2a6f2-103">JSON-Serialisierung und -Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) in .NET: Überblick</span><span class="sxs-lookup"><span data-stu-id="2a6f2-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="2a6f2-104">Der `:::no-loc(System.Text.Json):::`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="2a6f2-104">The `:::no-loc(System.Text.Json):::` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="2a6f2-105">Beim Entwerfen der Bibliothek wurde mehr Wert auf eine hohe Leistung und eine geringe Arbeitsspeicherbelegung gelegt als auf eine große Bandbreite von Features.</span><span class="sxs-lookup"><span data-stu-id="2a6f2-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="2a6f2-106">Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die am häufigsten verwendete Codierung für Daten im Web und Dateien auf Datenträgern.</span><span class="sxs-lookup"><span data-stu-id="2a6f2-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="2a6f2-107">Die Bibliothek stellt außerdem Klassen für die Arbeit mit einem In-Memory-Dokumentobjektmodell (DOM) bereit.</span><span class="sxs-lookup"><span data-stu-id="2a6f2-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="2a6f2-108">Diese Funktion ermöglicht einen zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder -Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2a6f2-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="2a6f2-109">Abrufen der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="2a6f2-109">How to get the library</span></span>

* <span data-ttu-id="2a6f2-110">Die Bibliothek ist als Teil des gemeinsamen Frameworks für .NET Core 3.0 und höhere Versionen integriert.</span><span class="sxs-lookup"><span data-stu-id="2a6f2-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="2a6f2-111">Installieren Sie für frühere Framework-Versionen das NuGet-Paket [:::no-loc(System.Text.Json):::](https://www.nuget.org/packages/:::no-loc(System.Text.Json):::).</span><span class="sxs-lookup"><span data-stu-id="2a6f2-111">For earlier framework versions, install the [:::no-loc(System.Text.Json):::](https://www.nuget.org/packages/:::no-loc(System.Text.Json):::) NuGet package.</span></span> <span data-ttu-id="2a6f2-112">Das Paket unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2a6f2-112">The package supports:</span></span>

  * <span data-ttu-id="2a6f2-113">.NET Standard 2.0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="2a6f2-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="2a6f2-114">.NET Framework 4.7.2 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="2a6f2-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="2a6f2-115">.NET Core 2.0, 2.1 und 2.2</span><span class="sxs-lookup"><span data-stu-id="2a6f2-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a6f2-116">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2a6f2-116">Additional resources</span></span>

* [<span data-ttu-id="2a6f2-117">Serialisierung und Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) von JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="2a6f2-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="2a6f2-118">Migration von :::no-loc(Newtonsoft.Json)::: in System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="2a6f2-118">How to migrate from :::no-loc(Newtonsoft.Json):::</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="2a6f2-119">Schreiben von benutzerdefinierten Konvertern für JSON-Serialisierung (Marshalling) in .NET</span><span class="sxs-lookup"><span data-stu-id="2a6f2-119">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="2a6f2-120">[:::no-loc(System.Text.Json):::-Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="2a6f2-120">[:::no-loc(System.Text.Json)::: source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::)</span></span>
* <span data-ttu-id="2a6f2-121">[:::no-loc(System.Text.Json):::-API-Referenz](xref::::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="2a6f2-121">[:::no-loc(System.Text.Json)::: API reference](xref::::no-loc(System.Text.Json):::)</span></span>
* <span data-ttu-id="2a6f2-122">[:::no-loc(System.Text.Json):::-Serialisierungs-API-Referenz](xref::::no-loc(System.Text.Json):::.Serialization)</span><span class="sxs-lookup"><span data-stu-id="2a6f2-122">[:::no-loc(System.Text.Json):::.Serialization API reference](xref::::no-loc(System.Text.Json):::.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::/roadmap/README.md)-->
