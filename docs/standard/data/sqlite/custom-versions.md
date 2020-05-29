---
title: Benutzerdefinierte SQLite-Versionen
ms.date: 05/14/2020
description: Hier erfahren Sie, wie Sie eine benutzerdefinierte Version der nativen SQLite-Bibliothek verwenden.
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440836"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="f9d8e-103">Benutzerdefinierte SQLite-Versionen</span><span class="sxs-lookup"><span data-stu-id="f9d8e-103">Custom SQLite versions</span></span>

<span data-ttu-id="f9d8e-104">`Microsoft.Data.Sqlite` basiert auf `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-104">`Microsoft.Data.Sqlite` is built on top of `SQLitePCLRaw`.</span></span> <span data-ttu-id="f9d8e-105">Sie können benutzerdefinierte Versionen der nativen SQLite-Bibliothek verwenden, indem Sie ein Bundle verwenden oder einen `SQLitePCLRaw`-Anbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a `SQLitePCLRaw` provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="f9d8e-106">Bundles</span><span class="sxs-lookup"><span data-stu-id="f9d8e-106">Bundles</span></span>

<span data-ttu-id="f9d8e-107">`SQLitePCLRaw` bietet benutzerfreundliche Bundlepakete, mit denen problemlos die richtigen Abhängigkeiten auf verschiedenen Plattformen genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-107">`SQLitePCLRaw` provides convenience-based bundle packages, that make it easy to bring in the right dependencies across different platforms.</span></span> <span data-ttu-id="f9d8e-108">Im `Microsoft.Data.Sqlite`-Hauptpaket ist `SQLitePCLRaw.bundle_e_sqlite3` standardmäßig enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-108">The main `Microsoft.Data.Sqlite` package brings in `SQLitePCLRaw.bundle_e_sqlite3` by default.</span></span> <span data-ttu-id="f9d8e-109">Installieren Sie das `Microsoft.Data.Sqlite.Core`-Paket und das gewünschte Bundlepaket, wenn Sie ein anderes Bundle verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="f9d8e-110">Bundles werden automatisch von `Microsoft.Data.Sqlite` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-110">Bundles are automatically initialized by `Microsoft.Data.Sqlite`.</span></span>

| <span data-ttu-id="f9d8e-111">Paket</span><span class="sxs-lookup"><span data-stu-id="f9d8e-111">Bundle</span></span> | <span data-ttu-id="f9d8e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9d8e-112">Description</span></span> |
|--|--|
| [<span data-ttu-id="f9d8e-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="f9d8e-113">SQLitePCLRaw.bundle_e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | <span data-ttu-id="f9d8e-114">Dieses Bundle stellt eine konsistente Version von SQLite auf allen Plattformen bereit.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="f9d8e-115">Es umfasst die FTS4-, FTS5-, JSON1 und R\*Tree-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="f9d8e-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-116">This is the default.</span></span> |
| [<span data-ttu-id="f9d8e-117">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="f9d8e-117">SQLitePCLRaw.bundle_e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | <span data-ttu-id="f9d8e-118">Hiermit wird ein inoffizieller Open-Source-Build von `SQLCipher` bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-118">Provides an unofficial, open-source build of `SQLCipher`.</span></span> |
| [<span data-ttu-id="f9d8e-119">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="f9d8e-119">SQLitePCLRaw.bundle_green</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | <span data-ttu-id="f9d8e-120">Dies ist mit `bundle_e_sqlite3` identisch, mit der Ausnahme, dass unter iOS die SQLite-Systembibliothek verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-120">Same as `bundle_e_sqlite3`, except on iOS where it uses the system SQLite library.</span></span> |
| [<span data-ttu-id="f9d8e-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="f9d8e-121">SQLitePCLRaw.bundle_winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | <span data-ttu-id="f9d8e-122">Hier wird mit `winsqlite3.dll` die SQLite-Systembibliothek unter Windows 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-122">Uses `winsqlite3.dll`, the system SQLite library on Windows 10.</span></span> |
| [<span data-ttu-id="f9d8e-123">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="f9d8e-123">SQLitePCLRaw.bundle_zetetic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | <span data-ttu-id="f9d8e-124">Hier werden die offiziellen `SQLCipher`-Builds von Zetetic (nicht enthalten) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-124">Uses the official `SQLCipher` builds from Zetetic (not included).</span></span> |

<span data-ttu-id="f9d8e-125">Nutzen Sie für die Verwendung des inoffiziellen Open-Source-Builds von `SQLCipher` die folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-125">For example, to use the unofficial, open-source build of `SQLCipher` use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="f9d8e-126">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="f9d8e-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="f9d8e-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9d8e-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a><span data-ttu-id="f9d8e-128">Verfügbare SQLitePCLRaw-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f9d8e-128">SQLitePCLRaw available providers</span></span>

<span data-ttu-id="f9d8e-129">Wenn Sie nicht auf ein Bundle angewiesen sind, können Sie die verfügbaren Anbieter von SQLite mit der Kernassembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-129">When not relying on a bundle, you can use the available providers of SQLite with the core assembly.</span></span>

| <span data-ttu-id="f9d8e-130">Anbieter</span><span class="sxs-lookup"><span data-stu-id="f9d8e-130">Provider</span></span> | <span data-ttu-id="f9d8e-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9d8e-131">Description</span></span> |
|--|--|
| [<span data-ttu-id="f9d8e-132">SQLitePCLRaw.provider.dynamic</span><span class="sxs-lookup"><span data-stu-id="f9d8e-132">SQLitePCLRaw.provider.dynamic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | <span data-ttu-id="f9d8e-133">Der `dynamic`-Anbieter lädt die native Bibliothek, anstatt <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>-Attribute zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-133">The `dynamic` provider loads the native library instead of using <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> attributes.</span></span> <span data-ttu-id="f9d8e-134">Weitere Informationen zur Verwendung dieses Anbieters finden Sie unter [Verwenden des dynamischen Anbieters](#use-the-dynamic-provider).</span><span class="sxs-lookup"><span data-stu-id="f9d8e-134">For more information on using this provider, see [use the dynamic provider](#use-the-dynamic-provider).</span></span> |
| [<span data-ttu-id="f9d8e-135">SQLitePCLRaw.provider.e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="f9d8e-135">SQLitePCLRaw.provider.e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | <span data-ttu-id="f9d8e-136">`e_sqlite3` ist der Standardanbieter.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-136">The `e_sqlite3` is the default provider.</span></span> |
| [<span data-ttu-id="f9d8e-137">SQLitePCLRaw.provider.e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="f9d8e-137">SQLitePCLRaw.provider.e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | <span data-ttu-id="f9d8e-138">Der `e_sqlcipher`-Anbieter bietet das inoffizielle und nicht unterstützte `SQLCipher`.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-138">The `e_sqlcipher` provider is the unofficial and unsupported `SQLCipher`.</span></span> |
| [<span data-ttu-id="f9d8e-139">SQLitePCLRaw.provider.sqlite3</span><span class="sxs-lookup"><span data-stu-id="f9d8e-139">SQLitePCLRaw.provider.sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | <span data-ttu-id="f9d8e-140">Der `sqlite3`-Anbieter bietet ein vom System bereitgestelltes `SQLite` für iOS, macOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-140">The `sqlite3` provider is a system-provided `SQLite` for iOS, macOS, and Linux.</span></span> |
| [<span data-ttu-id="f9d8e-141">SQLitePCLRaw.provider.sqlcipher</span><span class="sxs-lookup"><span data-stu-id="f9d8e-141">SQLitePCLRaw.provider.sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | <span data-ttu-id="f9d8e-142">Der `sqlcipher`-Anbieter ist für offizielle `SQLCipher`-Builds von `Zetetic` bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-142">The `sqlcipher` provider is for official `SQLCipher` builds from `Zetetic`.</span></span> |
| [<span data-ttu-id="f9d8e-143">SQLitePCLRaw.provider.winsqlite3</span><span class="sxs-lookup"><span data-stu-id="f9d8e-143">SQLitePCLRaw.provider.winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | <span data-ttu-id="f9d8e-144">Der `winsqlite3`-Anbieter ist für Windows 10-Umgebungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-144">The `winsqlite3` provider is for Windows 10 environments.</span></span> |

<span data-ttu-id="f9d8e-145">Verwenden Sie die folgenden Befehle für den `sqlite3`-Anbieter:</span><span class="sxs-lookup"><span data-stu-id="f9d8e-145">To use the `sqlite3` provider use the following commands:</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="f9d8e-146">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="f9d8e-146">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[<span data-ttu-id="f9d8e-147">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9d8e-147">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

<span data-ttu-id="f9d8e-148">Nachdem die Pakete installiert sind, legen Sie den Anbieter auf die `sqlite3`-Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-148">With the packages installed, you then set the provider to the `sqlite3` instance.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a><span data-ttu-id="f9d8e-149">Verwenden des dynamischen Anbieters</span><span class="sxs-lookup"><span data-stu-id="f9d8e-149">Use the dynamic provider</span></span>

<span data-ttu-id="f9d8e-150">Sie können Ihren eigenen Build von SQLite verwenden, indem Sie das `SQLitePCLRaw.provider.dynamic_cdecl`-Paket nutzen.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-150">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="f9d8e-151">In diesem Fall sind Sie für die Bereitstellung der nativen Bibliothek mit Ihrer App verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-151">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="f9d8e-152">Beachten Sie, dass die Details für die Bereitstellung nativer Bibliotheken mit Ihrer App in Abhängigkeit von der verwendeten .NET-Plattform und Runtime erheblich variieren können.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-152">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="f9d8e-153">Zuerst muss `IGetFunctionPointer` implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-153">First, you'll need to implement `IGetFunctionPointer`.</span></span> <span data-ttu-id="f9d8e-154">Die Implementierung in .NET Core erfolgt so:</span><span class="sxs-lookup"><span data-stu-id="f9d8e-154">The implementation on .NET Core is as follows:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="f9d8e-155">Konfigurieren Sie als Nächstes den `SQLitePCLRaw`-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-155">Next, configure the `SQLitePCLRaw` provider.</span></span> <span data-ttu-id="f9d8e-156">Stellen Sie sicher, dass Sie diesen Schritt abgeschlossen haben, bevor `Microsoft.Data.Sqlite` in Ihrer App verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-156">Ensure this is done before `Microsoft.Data.Sqlite` is used in your app.</span></span> <span data-ttu-id="f9d8e-157">Vermeiden Sie außerdem die Verwendung eines `SQLitePCLRaw`-Bundlepakets, das Ihren Anbieter möglicherweise überschreibt.</span><span class="sxs-lookup"><span data-stu-id="f9d8e-157">Also, avoid using a `SQLitePCLRaw` bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
