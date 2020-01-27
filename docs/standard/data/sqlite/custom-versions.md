---
title: Benutzerdefinierte SQLite-Versionen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie eine benutzerdefinierte Version der systemeigenen SQLite-Bibliothek verwenden.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746990"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="79158-103">Benutzerdefinierte SQLite-Versionen</span><span class="sxs-lookup"><span data-stu-id="79158-103">Custom SQLite versions</span></span>

<span data-ttu-id="79158-104">Microsoft. Data. sqlite baut auf sqlitepclraw auf.</span><span class="sxs-lookup"><span data-stu-id="79158-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="79158-105">Sie können benutzerdefinierte Versionen der systemeigenen SQLite-Bibliothek verwenden, indem Sie ein Bündel verwenden oder einen sqlitepclraw-Anbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="79158-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="79158-106">Ven</span><span class="sxs-lookup"><span data-stu-id="79158-106">Bundles</span></span>

<span data-ttu-id="79158-107">Sqlitepclraw stellt Bündel Pakete bereit, mit denen die richtigen Abhängigkeiten auf verschiedenen Plattformen problemlos untergebracht werden können.</span><span class="sxs-lookup"><span data-stu-id="79158-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="79158-108">Das Microsoft. Data. sqlite-Hauptpaket führt standardmäßig sqlitepclraw. bundle_e_sqlite3 ein.</span><span class="sxs-lookup"><span data-stu-id="79158-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="79158-109">Wenn Sie ein anderes Paket verwenden möchten, installieren Sie das `Microsoft.Data.Sqlite.Core` Paket und das Paket Paket, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="79158-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="79158-110">Pakete werden automatisch von "Microsoft. Data. sqlite" initialisiert.</span><span class="sxs-lookup"><span data-stu-id="79158-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="79158-111">Dels</span><span class="sxs-lookup"><span data-stu-id="79158-111">Bundle</span></span> | <span data-ttu-id="79158-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79158-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="79158-113">Sqlitepclraw. bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="79158-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="79158-114">Stellt eine konsistente Version von SQLite auf allen Plattformen bereit.</span><span class="sxs-lookup"><span data-stu-id="79158-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="79158-115">Schließt die Struktur Erweiterungen FTS4, FTS5, JSON1 und R \* ein.</span><span class="sxs-lookup"><span data-stu-id="79158-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="79158-116">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="79158-116">This is the default.</span></span> |
| <span data-ttu-id="79158-117">Sqlitepclraw. bundle_green</span><span class="sxs-lookup"><span data-stu-id="79158-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="79158-118">Identisch mit bundle_e_sqlite3, mit Ausnahme von IOS, wo die System SQLite-Bibliothek verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79158-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="79158-119">Sqlitepclraw. bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="79158-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="79158-120">Verwendet die offiziellen sqlcipher-Builds aus Zetetic (nicht eingeschlossen).</span><span class="sxs-lookup"><span data-stu-id="79158-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="79158-121">Sqlitepclraw. bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="79158-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="79158-122">Verwendet winsqlite3. dll, die System SQLite-Bibliothek unter Windows 10.</span><span class="sxs-lookup"><span data-stu-id="79158-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="79158-123">Sqlitepclraw. bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="79158-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="79158-124">Stellt einen inoffiziellen Open Source-Build von sqlcipher bereit.</span><span class="sxs-lookup"><span data-stu-id="79158-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="79158-125">Um beispielsweise den inoffiziellen Open Source-Build von sqlcipher zu verwenden, verwenden Sie die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="79158-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="79158-126">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="79158-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="79158-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79158-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="79158-128">Sqlitepclraw-Anbieter</span><span class="sxs-lookup"><span data-stu-id="79158-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="79158-129">Sie können Ihren eigenen Build von SQLite verwenden, indem Sie das `SQLitePCLRaw.provider.dynamic_cdecl`-Paket nutzen.</span><span class="sxs-lookup"><span data-stu-id="79158-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="79158-130">In diesem Fall sind Sie für die Bereitstellung der nativen Bibliothek mit Ihrer APP verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="79158-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="79158-131">Beachten Sie, dass die Details der Bereitstellung von systemeigenen Bibliotheken in Ihrer APP erheblich variieren, je nachdem, welche .NET-Plattform und-Laufzeit Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="79158-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="79158-132">Zuerst muss igetfunctionpointer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="79158-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="79158-133">Die Implementierung ist in .net Core Recht trivial.</span><span class="sxs-lookup"><span data-stu-id="79158-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="79158-134">Konfigurieren Sie als nächstes den sqlitepclraw-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="79158-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="79158-135">Stellen Sie sicher, dass dies geschieht, bevor Microsoft. Data. sqlite in Ihrer APP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79158-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="79158-136">Vermeiden Sie außerdem die Verwendung eines Pakets vom sqlitepclraw-Bundle, das Ihren Anbieter außer Kraft setzen kann.</span><span class="sxs-lookup"><span data-stu-id="79158-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
