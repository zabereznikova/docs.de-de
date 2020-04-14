---
title: Erweiterungen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie SQLite-Erweiterungen laden.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242958"
---
# <a name="extensions"></a><span data-ttu-id="efecb-103">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="efecb-103">Extensions</span></span>

<span data-ttu-id="efecb-104">SQLite unterstützt das Laden von Erweiterungen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="efecb-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="efecb-105">Erweiterungen umfassen Dinge wie zusätzliche SQL-Funktionen, Sortierungen, virtuelle Tabellen und mehr.</span><span class="sxs-lookup"><span data-stu-id="efecb-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="efecb-106">.NET Core enthält zusätzliche Logik zum Auffinden systemeigener Bibliotheken an zusätzlichen Orten wie nuGet-Paketen.</span><span class="sxs-lookup"><span data-stu-id="efecb-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="efecb-107">Leider kann SQLite diese Logik nicht nutzen; Die Plattform-API wird direkt zum Laden von Bibliotheken auf.</span><span class="sxs-lookup"><span data-stu-id="efecb-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="efecb-108">Aus diesem Grund müssen Sie möglicherweise die Umgebungsvariablen PATH, LD_LIBRARY_PATH oder DYLD_LIBRARY_PATH ändern, bevor Sie SQLite-Erweiterungen laden.</span><span class="sxs-lookup"><span data-stu-id="efecb-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="efecb-109">Es gibt [ein Beispiel](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) auf GitHub, das das Suchen von Binärdateien für die aktuelle Laufzeit in einem referenzierten NuGet-Paket veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="efecb-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="efecb-110">Um eine Erweiterung zu <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> laden, rufen Sie die Methode auf.</span><span class="sxs-lookup"><span data-stu-id="efecb-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="efecb-111">Microsoft.Data.Sqlite stellt sicher, dass die Erweiterung auch dann geladen bleibt, wenn die Verbindung geschlossen und erneut geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="efecb-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="efecb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efecb-112">See also</span></span>

* [<span data-ttu-id="efecb-113">Laufzeit-Ladeerweiterungen</span><span class="sxs-lookup"><span data-stu-id="efecb-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
