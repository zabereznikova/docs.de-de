---
title: Serialisieren und Deserialisieren von JSON C# mit-.net
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 5ce98a7908470a402779436db43333d46f5101fc
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180159"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="bf597-102">JSON-Serialisierung in .net-Übersicht</span><span class="sxs-lookup"><span data-stu-id="bf597-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="bf597-103">Der `System.Text.Json`-Namespace stellt Funktionen zum Serialisieren und Deserialisieren von JavaScript Object Notation (JSON) bereit.</span><span class="sxs-lookup"><span data-stu-id="bf597-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="bf597-104">Der Bibliotheks Entwurf hebt eine hohe Leistung und eine geringe Speicher Belegung für eine umfangreiche Featuregruppe hervor.</span><span class="sxs-lookup"><span data-stu-id="bf597-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="bf597-105">Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die häufigste Codierung für Daten im Web und Dateien auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="bf597-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="bf597-106">Die Bibliothek stellt außerdem Klassen zum Arbeiten mit einem Dokument Objektmodell (DOM) im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="bf597-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="bf597-107">Diese Funktion ermöglicht den zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bf597-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="bf597-108">Vorgehensweise beim erhalten der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="bf597-108">How to get the library</span></span>

* <span data-ttu-id="bf597-109">Die Bibliothek ist als Teil des gemeinsamen [.net Core 3,0](https://aka.ms/netcore3download) -Frameworks integriert.</span><span class="sxs-lookup"><span data-stu-id="bf597-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="bf597-110">Installieren Sie das nuget-Paket " [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) " für andere Ziel-Frameworks.</span><span class="sxs-lookup"><span data-stu-id="bf597-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="bf597-111">Das Paket unterstützt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bf597-111">The package supports:</span></span>
  * <span data-ttu-id="bf597-112">.NET Standard 2,0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="bf597-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="bf597-113">.NET Framework 4.6.1 und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="bf597-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="bf597-114">.Net Core 2,0, 2,1 und 2,2</span><span class="sxs-lookup"><span data-stu-id="bf597-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bf597-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="bf597-115">Additional resources</span></span>

* [<span data-ttu-id="bf597-116">Verwenden der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="bf597-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="bf597-117">Quellcode</span><span class="sxs-lookup"><span data-stu-id="bf597-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="bf597-118">API-Referenz</span><span class="sxs-lookup"><span data-stu-id="bf597-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="bf597-119">Roadmap</span><span class="sxs-lookup"><span data-stu-id="bf597-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="bf597-120">GitHub-Probleme im dotnet/corefx-Repository</span><span class="sxs-lookup"><span data-stu-id="bf597-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="bf597-121">Erörterung der Entwicklung von "System. Text. JSON"</span><span class="sxs-lookup"><span data-stu-id="bf597-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="bf597-122">Alle System. Text. JSON-Probleme</span><span class="sxs-lookup"><span data-stu-id="bf597-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="bf597-123">System. Text. JSON-Probleme mit der Bezeichnung JSON-funktionsdoc</span><span class="sxs-lookup"><span data-stu-id="bf597-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
