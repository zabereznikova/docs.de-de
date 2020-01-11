---
title: -Erweiterungen
ms.date: 12/13/2019
description: Erfahren Sie, wie SQLite-Erweiterungen geladen werden.
ms.openlocfilehash: a85b1227be4274dd20156d2475d6d2d68e250f99
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901295"
---
# <a name="extensions"></a><span data-ttu-id="645d2-103">-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="645d2-103">Extensions</span></span>

<span data-ttu-id="645d2-104">SQLite unterstützt das Laden von Erweiterungen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="645d2-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="645d2-105">Erweiterungen umfassen beispielsweise zusätzliche SQL-Funktionen, Sortierungen, virtuelle Tabellen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="645d2-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="645d2-106">.Net Core enthält zusätzliche Logik für die Suche nach nativen Bibliotheken an zusätzlichen Stellen wie referenzierte nuget-Pakete.</span><span class="sxs-lookup"><span data-stu-id="645d2-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="645d2-107">Leider kann SQLite diese Logik nicht nutzen. Sie ruft die Platform-API direkt zum Laden von Bibliotheken auf.</span><span class="sxs-lookup"><span data-stu-id="645d2-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="645d2-108">Aus diesem Grund müssen Sie möglicherweise die Pfad-, LD_LIBRARY_PATH-oder DYLD_LIBRARY_PATH Umgebungsvariablen vor dem Laden von SQLite-Erweiterungen ändern.</span><span class="sxs-lookup"><span data-stu-id="645d2-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="645d2-109">Auf GitHub finden Sie [ein Beispiel](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) , das die Suche nach Binärdateien für die aktuelle Laufzeit innerhalb eines referenzierten nuget-Pakets veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="645d2-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="645d2-110">Zum Laden einer Erweiterung wird die <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="645d2-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="645d2-111">Microsoft. Data. sqlite stellt sicher, dass die Erweiterung weiterhin geladen wird, auch wenn die Verbindung geschlossen und erneut geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="645d2-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="645d2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="645d2-112">See also</span></span>

* [<span data-ttu-id="645d2-113">Ausführbare Lauf Zeit Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="645d2-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
