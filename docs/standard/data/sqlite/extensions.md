---
title: Erweiterungen
ms.date: 12/13/2019
description: Erfahren Sie, wie SQLite-Erweiterungen geladen werden.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242958"
---
# <a name="extensions"></a><span data-ttu-id="756ac-103">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="756ac-103">Extensions</span></span>

<span data-ttu-id="756ac-104">SQLite unterstützt das Laden von Erweiterungen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="756ac-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="756ac-105">Erweiterungen umfassen beispielsweise zusätzliche SQL-Funktionen, Sortierungen und virtuelle Tabellen.</span><span class="sxs-lookup"><span data-stu-id="756ac-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="756ac-106">.NET Core enthält zusätzliche Logik für die Suche nach nativen Bibliotheken an zusätzlichen Orten wie NuGet-Paketen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="756ac-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="756ac-107">Leider kann SQLite diese Logik nicht nutzen, sondern ruft die Plattform-API direkt auf, um Bibliotheken zu laden.</span><span class="sxs-lookup"><span data-stu-id="756ac-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="756ac-108">Daher müssen Sie möglicherweise vor dem Laden von SQLite-Erweiterungen den Pfad, LD_LIBRARY_PATH, oder DYLD_LIBRARY_PATH-Umgebungsvariablen ändern.</span><span class="sxs-lookup"><span data-stu-id="756ac-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="756ac-109">In [einem Beispiel](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) auf GitHub wird gezeigt, wie Binärdateien für die aktuelle Runtime in einem NuGet-Paket gefunden werden können, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="756ac-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="756ac-110">Rufen Sie die Methode <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> auf, um Erweiterungen zu laden.</span><span class="sxs-lookup"><span data-stu-id="756ac-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="756ac-111">Microsoft.Data.Sqlite stellt sicher, dass die Erweiterung geladen bleibt, auch wenn die Verbindung geschlossen und erneut geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="756ac-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="756ac-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="756ac-112">See also</span></span>

* [<span data-ttu-id="756ac-113">Zur Laufzeit ladbare Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="756ac-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
