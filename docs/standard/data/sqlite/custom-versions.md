---
title: Benutzerdefinierte SQLite-Versionen
ms.date: 12/13/2019
description: Hier erfahren Sie, wie Sie eine benutzerdefinierte Version der nativen SQLite-Bibliothek verwenden.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746990"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="13d1f-103">Benutzerdefinierte SQLite-Versionen</span><span class="sxs-lookup"><span data-stu-id="13d1f-103">Custom SQLite versions</span></span>

<span data-ttu-id="13d1f-104">Microsoft.Data.Sqlite basiert auf SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="13d1f-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="13d1f-105">Sie können benutzerdefinierte Versionen der nativen SQLite-Bibliothek verwenden, indem Sie ein Bundle verwenden oder einen SQLitePCLRaw-Anbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13d1f-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="13d1f-106">Bundles</span><span class="sxs-lookup"><span data-stu-id="13d1f-106">Bundles</span></span>

<span data-ttu-id="13d1f-107">SQLitePCLRaw bietet Bundlepakete, mit denen die richtigen Abhängigkeiten auf verschiedenen Plattformen problemlos genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="13d1f-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="13d1f-108">Das Microsoft.Data.Sqlite-Hauptpaket fügt „SQLitePCLRaw.bundle_e_sqlite3“ standardmäßig hinzu.</span><span class="sxs-lookup"><span data-stu-id="13d1f-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="13d1f-109">Installieren Sie das `Microsoft.Data.Sqlite.Core`-Paket und das gewünschte Bundlepaket, wenn Sie ein anderes Bundle verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="13d1f-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="13d1f-110">Bundles werden automatisch von Microsoft.Data.Sqlite initialisiert.</span><span class="sxs-lookup"><span data-stu-id="13d1f-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="13d1f-111">Paket</span><span class="sxs-lookup"><span data-stu-id="13d1f-111">Bundle</span></span> | <span data-ttu-id="13d1f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13d1f-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="13d1f-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="13d1f-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="13d1f-114">Dieses Bundle stellt eine konsistente Version von SQLite auf allen Plattformen bereit.</span><span class="sxs-lookup"><span data-stu-id="13d1f-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="13d1f-115">Es umfasst die FTS4-, FTS5-, JSON1 und R\*Tree-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="13d1f-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="13d1f-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="13d1f-116">This is the default.</span></span> |
| <span data-ttu-id="13d1f-117">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="13d1f-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="13d1f-118">Dies ist mit bundle_e_sqlite3 identisch, mit der Ausnahme, dass unter iOS die SQLite-Systembibliothek verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13d1f-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="13d1f-119">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="13d1f-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="13d1f-120">Hier werden die offiziellen SQLCipher-Builds von Zetetic (nicht enthalten) verwendet.</span><span class="sxs-lookup"><span data-stu-id="13d1f-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="13d1f-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="13d1f-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="13d1f-122">Hier wird mit winsqlite3.dll die SQLite-Systembibliothek unter Windows 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="13d1f-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="13d1f-123">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="13d1f-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="13d1f-124">Hiermit wird ein inoffizieller Open-Source-Build von SQLCipher bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="13d1f-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="13d1f-125">Nutzen Sie für die Verwendung des inoffiziellen Open-Source-Builds von SQLCipher die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="13d1f-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="13d1f-126">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="13d1f-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="13d1f-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="13d1f-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="13d1f-128">SQLitePCLRaw-Anbieter</span><span class="sxs-lookup"><span data-stu-id="13d1f-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="13d1f-129">Sie können Ihren eigenen Build von SQLite verwenden, indem Sie das `SQLitePCLRaw.provider.dynamic_cdecl`-Paket nutzen.</span><span class="sxs-lookup"><span data-stu-id="13d1f-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="13d1f-130">In diesem Fall sind Sie für die Bereitstellung der nativen Bibliothek mit Ihrer App verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="13d1f-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="13d1f-131">Beachten Sie, dass die Details für die Bereitstellung nativer Bibliotheken mit Ihrer App in Abhängigkeit von der verwendeten .NET-Plattform und Runtime erheblich variieren können.</span><span class="sxs-lookup"><span data-stu-id="13d1f-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="13d1f-132">Zuerst muss IGetFunctionPointer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="13d1f-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="13d1f-133">Die Implementierung ist in .NET Core trivial.</span><span class="sxs-lookup"><span data-stu-id="13d1f-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="13d1f-134">Danach konfigurieren Sie den SQLitePCLRaw-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="13d1f-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="13d1f-135">Stellen Sie sicher, dass Sie diesen Schritt abgeschlossen haben, bevor Microsoft.Data.Sqlite in Ihrer App verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13d1f-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="13d1f-136">Vermeiden Sie außerdem die Verwendung eines SQLitePCLRaw-Bundlepakets, das Ihren Anbieter möglicherweise überschreibt.</span><span class="sxs-lookup"><span data-stu-id="13d1f-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
