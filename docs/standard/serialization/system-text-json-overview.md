---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159545"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="23ee8-102">JSON-Serialisierung und -Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) in .NET: Überblick</span><span class="sxs-lookup"><span data-stu-id="23ee8-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="23ee8-103">Der `System.Text.Json`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="23ee8-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="23ee8-104">Beim Entwerfen der Bibliothek wurde mehr Wert auf eine hohe Leistung und eine geringe Arbeitsspeicherbelegung gelegt als auf eine große Bandbreite von Features.</span><span class="sxs-lookup"><span data-stu-id="23ee8-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="23ee8-105">Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die am häufigsten verwendete Codierung für Daten im Web und Dateien auf Datenträgern.</span><span class="sxs-lookup"><span data-stu-id="23ee8-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="23ee8-106">Die Bibliothek stellt außerdem Klassen für die Arbeit mit einem In-Memory-Dokumentobjektmodell (DOM) bereit.</span><span class="sxs-lookup"><span data-stu-id="23ee8-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="23ee8-107">Diese Funktion ermöglicht einen zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder -Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="23ee8-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="23ee8-108">Abrufen der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="23ee8-108">How to get the library</span></span>

* <span data-ttu-id="23ee8-109">Die Bibliothek ist im freigegebenen [.NET Core 3.0](https://aka.ms/netcore3download)-Framework enthalten.</span><span class="sxs-lookup"><span data-stu-id="23ee8-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="23ee8-110">Installieren Sie für andere Zielframeworks das NuGet-Paket [System.Text.Json](https://www.nuget.org/packages/System.Text.Json).</span><span class="sxs-lookup"><span data-stu-id="23ee8-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="23ee8-111">Das Paket unterstützt:</span><span class="sxs-lookup"><span data-stu-id="23ee8-111">The package supports:</span></span>
  * <span data-ttu-id="23ee8-112">.NET Standard 2.0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="23ee8-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="23ee8-113">.NET Framework 4.7.2 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="23ee8-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="23ee8-114">.NET Core 2.0, 2.1 und 2.2</span><span class="sxs-lookup"><span data-stu-id="23ee8-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23ee8-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="23ee8-115">Additional resources</span></span>

* [<span data-ttu-id="23ee8-116">Serialisierung und Deserialisierung (Marshalling und Rückgängigmachen von Marshalling) von JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="23ee8-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="23ee8-117">[Migration von Newtonsoft.Json in System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="23ee8-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="23ee8-118">Schreiben von benutzerdefinierten Konvertern für JSON-Serialisierung (Marshalling) in .NET</span><span class="sxs-lookup"><span data-stu-id="23ee8-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="23ee8-119">[System.Text.Json-Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="23ee8-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="23ee8-120">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="23ee8-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="23ee8-121">[System.Text.Json.Serialization-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="23ee8-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
