---
title: Verbindungszeichenfolgen
ms.date: 12/13/2019
description: Die unterstützten Schlüsselwörter und Werte von Verbindungszeichenfolgen.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401196"
---
# <a name="connection-strings"></a><span data-ttu-id="0e212-103">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="0e212-103">Connection strings</span></span>

<span data-ttu-id="0e212-104">Eine Verbindungszeichenfolge wird verwendet, um anzugeben, wie eine Verbindung mit der Datenbank hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e212-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="0e212-105">Verbindungszeichenfolgen in Microsoft.Data.Sqlite folgen der [Standard-ADO.NET Syntax](../../../framework/data/adonet/connection-strings.md) als semikolonngetrennte Liste von Schlüsselwörtern und Werten.</span><span class="sxs-lookup"><span data-stu-id="0e212-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="0e212-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="0e212-106">Keywords</span></span>

<span data-ttu-id="0e212-107">Die folgenden Verbindungszeichenfolgenschlüsselwörter können mit Microsoft.Data.Sqlite verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0e212-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="0e212-108">Datenquelle</span><span class="sxs-lookup"><span data-stu-id="0e212-108">Data source</span></span>

<span data-ttu-id="0e212-109">Der Pfad zur Datenbankdatei.</span><span class="sxs-lookup"><span data-stu-id="0e212-109">The path to the database file.</span></span> <span data-ttu-id="0e212-110">*DataSource* (ohne Leerzeichen) und *Filename* sind Aliase dieses Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="0e212-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="0e212-111">SQLite behandelt Pfade relativ zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0e212-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="0e212-112">Absolute Pfade können auch angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0e212-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="0e212-113">Wenn **leer**, erstellt SQLite eine temporäre Datenträgerdatenbank, die beim Schließen der Verbindung gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="0e212-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="0e212-114">Wenn `:memory:`, wird eine In-Memory-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e212-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="0e212-115">Weitere Informationen finden Sie [unter In-Memory-Datenbanken](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0e212-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="0e212-116">Pfade, die `|DataDirectory|` mit der Ersetzungszeichenfolge beginnen, werden wie relative Pfade behandelt.</span><span class="sxs-lookup"><span data-stu-id="0e212-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="0e212-117">Wenn diese Einstellung festgelegt ist, werden Pfade relativ zum Eigenschaftswert der DataDirectory-Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="0e212-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="0e212-118">Dieses Schlüsselwort unterstützt auch [URI Filenames](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="0e212-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="0e212-119">Mode</span><span class="sxs-lookup"><span data-stu-id="0e212-119">Mode</span></span>

<span data-ttu-id="0e212-120">Der Verbindungsmodus.</span><span class="sxs-lookup"><span data-stu-id="0e212-120">The connection mode.</span></span>

| <span data-ttu-id="0e212-121">value</span><span class="sxs-lookup"><span data-stu-id="0e212-121">Value</span></span>           | <span data-ttu-id="0e212-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e212-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0e212-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="0e212-123">ReadWriteCreate</span></span> | <span data-ttu-id="0e212-124">Öffnet die Datenbank zum Lesen und Schreiben und erstellt sie, wenn sie nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0e212-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="0e212-125">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="0e212-125">This is the default.</span></span> |
| <span data-ttu-id="0e212-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0e212-126">ReadWrite</span></span>       | <span data-ttu-id="0e212-127">Öffnet die Datenbank zum Lesen und Schreiben.</span><span class="sxs-lookup"><span data-stu-id="0e212-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="0e212-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="0e212-128">ReadOnly</span></span>        | <span data-ttu-id="0e212-129">Öffnet die Datenbank im schreibgeschützten Modus.</span><span class="sxs-lookup"><span data-stu-id="0e212-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="0e212-130">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="0e212-130">Memory</span></span>          | <span data-ttu-id="0e212-131">Öffnet eine In-Memory-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0e212-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="0e212-132">Cache</span><span class="sxs-lookup"><span data-stu-id="0e212-132">Cache</span></span>

<span data-ttu-id="0e212-133">Der caching-Modus, der von der Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e212-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="0e212-134">value</span><span class="sxs-lookup"><span data-stu-id="0e212-134">Value</span></span>   | <span data-ttu-id="0e212-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e212-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0e212-136">Standard</span><span class="sxs-lookup"><span data-stu-id="0e212-136">Default</span></span> | <span data-ttu-id="0e212-137">Verwendet den Standardmodus der zugrunde liegenden SQLite-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="0e212-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="0e212-138">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="0e212-138">This is the default.</span></span>                   |
| <span data-ttu-id="0e212-139">Privat</span><span class="sxs-lookup"><span data-stu-id="0e212-139">Private</span></span> | <span data-ttu-id="0e212-140">Jede Verbindung verwendet einen privaten Cache.</span><span class="sxs-lookup"><span data-stu-id="0e212-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="0e212-141">Shared</span><span class="sxs-lookup"><span data-stu-id="0e212-141">Shared</span></span>  | <span data-ttu-id="0e212-142">Verbindungen teilen sich einen Cache.</span><span class="sxs-lookup"><span data-stu-id="0e212-142">Connections share a cache.</span></span> <span data-ttu-id="0e212-143">Dieser Modus kann das Verhalten von Transaktionen und Tabellensperren ändern.</span><span class="sxs-lookup"><span data-stu-id="0e212-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="0e212-144">Kennwort</span><span class="sxs-lookup"><span data-stu-id="0e212-144">Password</span></span>

<span data-ttu-id="0e212-145">Der Verschlüsselungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="0e212-145">The encryption key.</span></span> <span data-ttu-id="0e212-146">Wenn angegeben, `PRAGMA key` wird sofort nach dem Öffnen der Verbindung gesendet.</span><span class="sxs-lookup"><span data-stu-id="0e212-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="0e212-147">Das Kennwort hat keine Auswirkungen, wenn die Verschlüsselung von der nativen SQLite-Bibliothek nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0e212-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="0e212-148">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="0e212-148">Foreign Keys</span></span>

<span data-ttu-id="0e212-149">Ein Wert, der angibt, ob Fremdschlüsseleinschränkungen aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0e212-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="0e212-150">value</span><span class="sxs-lookup"><span data-stu-id="0e212-150">Value</span></span>   | <span data-ttu-id="0e212-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e212-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="0e212-152">True</span><span class="sxs-lookup"><span data-stu-id="0e212-152">True</span></span>    | <span data-ttu-id="0e212-153">Sendet `PRAGMA foreign_keys = 1` unmittelbar nach dem Öffnen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="0e212-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="0e212-154">False</span><span class="sxs-lookup"><span data-stu-id="0e212-154">False</span></span>   | <span data-ttu-id="0e212-155">Sendet `PRAGMA foreign_keys = 0` unmittelbar nach dem Öffnen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="0e212-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="0e212-156">(leer)</span><span class="sxs-lookup"><span data-stu-id="0e212-156">(empty)</span></span> | <span data-ttu-id="0e212-157">Sendet nicht `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="0e212-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="0e212-158">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="0e212-158">This is the default.</span></span> |

<span data-ttu-id="0e212-159">Es ist nicht erforderlich, Fremdschlüssel zu aktivieren, wenn, wie in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS zum Kompilieren der nativen SQLite-Bibliothek verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0e212-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="0e212-160">Rekursive Trigger</span><span class="sxs-lookup"><span data-stu-id="0e212-160">Recursive triggers</span></span>

<span data-ttu-id="0e212-161">Ein Wert, der angibt, ob rekursive Trigger aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0e212-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="0e212-162">value</span><span class="sxs-lookup"><span data-stu-id="0e212-162">Value</span></span> | <span data-ttu-id="0e212-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e212-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="0e212-164">True</span><span class="sxs-lookup"><span data-stu-id="0e212-164">True</span></span>  | <span data-ttu-id="0e212-165">Sendet `PRAGMA recursive_triggers` unmittelbar nach dem Öffnen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="0e212-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="0e212-166">False</span><span class="sxs-lookup"><span data-stu-id="0e212-166">False</span></span> | <span data-ttu-id="0e212-167">Sendet nicht `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="0e212-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="0e212-168">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="0e212-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="0e212-169">Verbindungszeichenfolgen-Generator</span><span class="sxs-lookup"><span data-stu-id="0e212-169">Connection string builder</span></span>

<span data-ttu-id="0e212-170">Sie können <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> als stark typisierte Möglichkeit zum Erstellen von Verbindungszeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e212-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="0e212-171">Es kann auch verwendet werden, um VerbindungszeichenfolgeNinjektionsangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="0e212-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="0e212-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0e212-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="0e212-173">Basic</span><span class="sxs-lookup"><span data-stu-id="0e212-173">Basic</span></span>

<span data-ttu-id="0e212-174">Eine grundlegende Verbindungszeichenfolge mit einem freigegebenen Cache für eine verbesserte Parallelität.</span><span class="sxs-lookup"><span data-stu-id="0e212-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="0e212-175">Verschlüsselt</span><span class="sxs-lookup"><span data-stu-id="0e212-175">Encrypted</span></span>

<span data-ttu-id="0e212-176">Eine verschlüsselte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0e212-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="0e212-177">Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0e212-177">Read-only</span></span>

<span data-ttu-id="0e212-178">Eine schreibgeschützte Datenbank, die von der App nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e212-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="0e212-179">In-Memory</span><span class="sxs-lookup"><span data-stu-id="0e212-179">In-memory</span></span>

<span data-ttu-id="0e212-180">Eine private, in-Memory-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0e212-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="0e212-181">Sharable in-memory</span><span class="sxs-lookup"><span data-stu-id="0e212-181">Sharable in-memory</span></span>

<span data-ttu-id="0e212-182">Eine sharable, in-memory-Datenbank, die mit dem Namen *Sharable*identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0e212-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="0e212-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e212-183">See also</span></span>

* [<span data-ttu-id="0e212-184">Verbindungszeichenfolgen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0e212-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="0e212-185">In-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="0e212-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="0e212-186">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="0e212-186">Transactions</span></span>](transactions.md)
