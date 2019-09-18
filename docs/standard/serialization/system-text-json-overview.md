---
title: JSON-Serialisierung in .net
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 6cb45fded220b6123dbf4461f5f1cf1c3556ff69
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083096"
---
# <a name="json-serialization-in-net"></a><span data-ttu-id="10736-102">JSON-Serialisierung in .net</span><span class="sxs-lookup"><span data-stu-id="10736-102">JSON serialization in .NET</span></span>

<span data-ttu-id="10736-103">Der `System.Text.Json` -Namespace stellt Funktionen zum Serialisieren in und aus JavaScript Object Notation (JSON) bereit.</span><span class="sxs-lookup"><span data-stu-id="10736-103">The `System.Text.Json` namespace provides functionality for serializing to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="10736-104">Der Bibliotheks Entwurf hebt eine hohe Leistung und eine geringe Speicher Belegung für eine umfangreiche Featuregruppe hervor.</span><span class="sxs-lookup"><span data-stu-id="10736-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="10736-105">Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die häufigste Codierung für Daten im Web und Dateien auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="10736-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="10736-106">Die Bibliothek stellt außerdem Klassen zum Arbeiten mit einem Dokument Objektmodell (DOM) im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="10736-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="10736-107">Diese Funktion ermöglicht den zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="10736-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="10736-108">Vorgehensweise beim erhalten der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="10736-108">How to get the library</span></span>

* <span data-ttu-id="10736-109">Die Bibliothek ist als Teil des gemeinsamen [.net Core 3,0](https://aka.ms/netcore3download) -Frameworks integriert.</span><span class="sxs-lookup"><span data-stu-id="10736-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="10736-110">Installieren Sie das nuget-Paket " [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) " für andere Ziel-Frameworks.</span><span class="sxs-lookup"><span data-stu-id="10736-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="10736-111">Das Paket unterstützt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="10736-111">The package supports:</span></span>
  * <span data-ttu-id="10736-112">.NET Standard 2,0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="10736-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="10736-113">.NET Framework 4,61 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="10736-113">.NET Framework 4.61 and later versions</span></span>
  * <span data-ttu-id="10736-114">.Net Core 2,0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="10736-114">.NET Core 2.0 and later versions</span></span>

## <a name="additional-resources"></a><span data-ttu-id="10736-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="10736-115">Additional resources</span></span>

* [<span data-ttu-id="10736-116">Verwenden der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="10736-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="10736-117">Quellcode</span><span class="sxs-lookup"><span data-stu-id="10736-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="10736-118">API-Referenz</span><span class="sxs-lookup"><span data-stu-id="10736-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="10736-119">Roadmap</span><span class="sxs-lookup"><span data-stu-id="10736-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="10736-120">GitHub-Probleme im dotnet/corefx-Repository</span><span class="sxs-lookup"><span data-stu-id="10736-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="10736-121">Erörterung der Entwicklung von "System. Text. JSON"</span><span class="sxs-lookup"><span data-stu-id="10736-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="10736-122">Alle System. Text. JSON-Probleme</span><span class="sxs-lookup"><span data-stu-id="10736-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="10736-123">System. Text. JSON-Probleme mit der Bezeichnung JSON-funktionsdoc</span><span class="sxs-lookup"><span data-stu-id="10736-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
