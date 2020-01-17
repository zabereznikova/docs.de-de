---
title: Serialisieren und Deserialisieren von JSON C# mit-.net
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: acb83be9b20a155b6b6a9fb5ade38e099f54e71d
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163591"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="25bcd-102">JSON-Serialisierung und-Deserialisierung (Marshalling und Unmarshalling) in .net-Overview</span><span class="sxs-lookup"><span data-stu-id="25bcd-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="25bcd-103">Der `System.Text.Json`-Namespace stellt Funktionen zum Serialisieren und Deserialisieren von JavaScript Object Notation (JSON) bereit.</span><span class="sxs-lookup"><span data-stu-id="25bcd-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="25bcd-104">Der Bibliotheks Entwurf hebt eine hohe Leistung und eine geringe Speicher Belegung für eine umfangreiche Featuregruppe hervor.</span><span class="sxs-lookup"><span data-stu-id="25bcd-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="25bcd-105">Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die häufigste Codierung für Daten im Web und Dateien auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="25bcd-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="25bcd-106">Die Bibliothek stellt außerdem Klassen zum Arbeiten mit einem Dokument Objektmodell (DOM) im Arbeitsspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="25bcd-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="25bcd-107">Diese Funktion ermöglicht den zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="25bcd-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="25bcd-108">Vorgehensweise beim erhalten der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="25bcd-108">How to get the library</span></span>

* <span data-ttu-id="25bcd-109">Die Bibliothek ist als Teil des gemeinsamen [.net Core 3,0](https://aka.ms/netcore3download) -Frameworks integriert.</span><span class="sxs-lookup"><span data-stu-id="25bcd-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="25bcd-110">Installieren Sie für andere Ziel-Frameworks das [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) nuget-Paket.</span><span class="sxs-lookup"><span data-stu-id="25bcd-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="25bcd-111">Das Paket unterstützt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="25bcd-111">The package supports:</span></span>
  * <span data-ttu-id="25bcd-112">.NET Standard 2,0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="25bcd-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="25bcd-113">.NET Framework 4.7.2 und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="25bcd-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="25bcd-114">.Net Core 2,0, 2,1 und 2,2</span><span class="sxs-lookup"><span data-stu-id="25bcd-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25bcd-115">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="25bcd-115">Additional resources</span></span>

* [<span data-ttu-id="25bcd-116">Verwenden der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="25bcd-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="25bcd-117">[Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="25bcd-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="25bcd-118">Schreiben von Konvertern</span><span class="sxs-lookup"><span data-stu-id="25bcd-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="25bcd-119">[System.Text.Json Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="25bcd-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="25bcd-120">[API-Referenz für System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="25bcd-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="25bcd-121">[System.Text.Json. API-Referenz für die Serialisierung](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="25bcd-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
