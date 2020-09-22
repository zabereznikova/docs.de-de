---
title: Verbindungszeichenfolgen
ms.date: 12/13/2019
description: Hier werden die von Verbindungszeichenfolgen unterstützten Schlüsselwörter und Werte erläutert.
ms.openlocfilehash: 3c50b31689abf6d47aa8f83a6f6f755bcfec0ea3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555392"
---
# <a name="connection-strings"></a><span data-ttu-id="15868-103">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="15868-103">Connection strings</span></span>

<span data-ttu-id="15868-104">Mit einer Verbindungszeichenfolge wird angegeben, wie eine Verbindung zur Datenbank hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="15868-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="15868-105">Verbindungszeichenfolgen in Microsoft.Data.Sqlite folgen als durch Semikolons getrennte Liste von Schlüsselwörtern und Werten auf die [ADO.NET-Standardsyntax](../../../framework/data/adonet/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="15868-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="15868-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="15868-106">Keywords</span></span>

<span data-ttu-id="15868-107">Die folgenden Schlüsselwörter für Verbindungszeichenfolgen können mit Microsoft.Data.Sqlite verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="15868-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="15868-108">Datenquelle</span><span class="sxs-lookup"><span data-stu-id="15868-108">Data source</span></span>

<span data-ttu-id="15868-109">Der Pfad zur Datenbankdatei.</span><span class="sxs-lookup"><span data-stu-id="15868-109">The path to the database file.</span></span> <span data-ttu-id="15868-110">*DataSource* (ohne Leerzeichen) und *Filename* (Dateiname) sind Aliase dieses Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="15868-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="15868-111">SQLite behandelt Pfade relativ zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="15868-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="15868-112">Absolute Pfade können ebenfalls angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="15868-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="15868-113">Im Falle von **empty** (leer) erstellt SQLite eine temporäre Datenbank auf dem Datenträger, die gelöscht wird, wenn diese Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="15868-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="15868-114">Bei `:memory:` wird eine In-Memory-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="15868-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="15868-115">Weitere Informationen finden Sie unter [In-Memory-Datenbanken](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="15868-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="15868-116">Pfade, die mit der Ersatzzeichenfolge `|DataDirectory|` beginnen, werden wie relative Pfade behandelt.</span><span class="sxs-lookup"><span data-stu-id="15868-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="15868-117">Wenn dies festgelegt ist, werden Pfade relativ zum Eigenschaftswert der Anwendungsdomäne für DataDirectory erstellt.</span><span class="sxs-lookup"><span data-stu-id="15868-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="15868-118">Dieses Schlüsselwort unterstützt auch [URI-Dateinamen](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="15868-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="15868-119">Modus</span><span class="sxs-lookup"><span data-stu-id="15868-119">Mode</span></span>

<span data-ttu-id="15868-120">Dies ist der Verbindungsmodus.</span><span class="sxs-lookup"><span data-stu-id="15868-120">The connection mode.</span></span>

| <span data-ttu-id="15868-121">Wert</span><span class="sxs-lookup"><span data-stu-id="15868-121">Value</span></span>           | <span data-ttu-id="15868-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15868-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="15868-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="15868-123">ReadWriteCreate</span></span> | <span data-ttu-id="15868-124">Hiermit wird die Datenbank für Lese- und Schreibvorgänge geöffnet und ggf. erstellt, wenn sie nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="15868-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="15868-125">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="15868-125">This is the default.</span></span> |
| <span data-ttu-id="15868-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="15868-126">ReadWrite</span></span>       | <span data-ttu-id="15868-127">Hiermit wird die Datenbank für Lese- und Schreibvorgänge geöffnet.</span><span class="sxs-lookup"><span data-stu-id="15868-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="15868-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="15868-128">ReadOnly</span></span>        | <span data-ttu-id="15868-129">Hiermit wird die Datenbank im schreibgeschützten Modus geöffnet.</span><span class="sxs-lookup"><span data-stu-id="15868-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="15868-130">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="15868-130">Memory</span></span>          | <span data-ttu-id="15868-131">Hiermit wird eine In-Memory-Datenbank geöffnet.</span><span class="sxs-lookup"><span data-stu-id="15868-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="15868-132">cache</span><span class="sxs-lookup"><span data-stu-id="15868-132">Cache</span></span>

<span data-ttu-id="15868-133">Hierbei handelt es sich um den von der Verbindung verwendeten Cachemodus.</span><span class="sxs-lookup"><span data-stu-id="15868-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="15868-134">Wert</span><span class="sxs-lookup"><span data-stu-id="15868-134">Value</span></span>   | <span data-ttu-id="15868-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15868-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="15868-136">Standard</span><span class="sxs-lookup"><span data-stu-id="15868-136">Default</span></span> | <span data-ttu-id="15868-137">Hiermit wird der Standardmodus der zugrunde liegenden SQLite-Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="15868-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="15868-138">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="15868-138">This is the default.</span></span>                   |
| <span data-ttu-id="15868-139">Private</span><span class="sxs-lookup"><span data-stu-id="15868-139">Private</span></span> | <span data-ttu-id="15868-140">Jede Verbindung verwendet einen privaten Cache.</span><span class="sxs-lookup"><span data-stu-id="15868-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="15868-141">Shared</span><span class="sxs-lookup"><span data-stu-id="15868-141">Shared</span></span>  | <span data-ttu-id="15868-142">Verbindungen nutzen einen Cache gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="15868-142">Connections share a cache.</span></span> <span data-ttu-id="15868-143">Dieser Modus kann das Verhalten der Transaktion und der Tabellensperrung ändern.</span><span class="sxs-lookup"><span data-stu-id="15868-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="15868-144">Kennwort</span><span class="sxs-lookup"><span data-stu-id="15868-144">Password</span></span>

<span data-ttu-id="15868-145">Der Verschlüsselungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="15868-145">The encryption key.</span></span> <span data-ttu-id="15868-146">Wenn dieser angegeben ist, wird `PRAGMA key` unmittelbar nach dem Öffnen der Verbindung gesendet.</span><span class="sxs-lookup"><span data-stu-id="15868-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="15868-147">Das Kennwort hat keine Auswirkung, wenn die Verschlüsselung von der nativen SQLite-Bibliothek nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="15868-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="15868-148">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="15868-148">Foreign Keys</span></span>

<span data-ttu-id="15868-149">Dieser Wert gibt an, ob Fremdschlüsseleinschränkungen aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15868-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="15868-150">Wert</span><span class="sxs-lookup"><span data-stu-id="15868-150">Value</span></span>   | <span data-ttu-id="15868-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15868-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="15868-152">True</span><span class="sxs-lookup"><span data-stu-id="15868-152">True</span></span>    | <span data-ttu-id="15868-153">Hier wird `PRAGMA foreign_keys = 1` unmittelbar nach dem Öffnen der Verbindung gesendet.</span><span class="sxs-lookup"><span data-stu-id="15868-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="15868-154">False</span><span class="sxs-lookup"><span data-stu-id="15868-154">False</span></span>   | <span data-ttu-id="15868-155">Hier wird `PRAGMA foreign_keys = 0` unmittelbar nach dem Öffnen der Verbindung gesendet.</span><span class="sxs-lookup"><span data-stu-id="15868-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="15868-156">(leer)</span><span class="sxs-lookup"><span data-stu-id="15868-156">(empty)</span></span> | <span data-ttu-id="15868-157">Hier wird `PRAGMA foreign_keys` nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="15868-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="15868-158">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="15868-158">This is the default.</span></span> |

<span data-ttu-id="15868-159">Fremdschlüssel müssen nicht aktiviert werden, wenn wie im Fall von e_sqlite3 „SQLITE_DEFAULT_FOREIGN_KEYS“ zum Kompilieren der nativen SQLite-Bibliothek verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="15868-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="15868-160">Rekursive Trigger</span><span class="sxs-lookup"><span data-stu-id="15868-160">Recursive triggers</span></span>

<span data-ttu-id="15868-161">Mit diesem Wert wird angegeben, ob rekursive Trigger aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15868-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="15868-162">Wert</span><span class="sxs-lookup"><span data-stu-id="15868-162">Value</span></span> | <span data-ttu-id="15868-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15868-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="15868-164">True</span><span class="sxs-lookup"><span data-stu-id="15868-164">True</span></span>  | <span data-ttu-id="15868-165">Hier wird `PRAGMA recursive_triggers` unmittelbar nach dem Öffnen der Verbindung gesendet.</span><span class="sxs-lookup"><span data-stu-id="15868-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="15868-166">False</span><span class="sxs-lookup"><span data-stu-id="15868-166">False</span></span> | <span data-ttu-id="15868-167">Hier wird `PRAGMA recursive_triggers` nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="15868-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="15868-168">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="15868-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="15868-169">Verbindungszeichenfolgen-Generator</span><span class="sxs-lookup"><span data-stu-id="15868-169">Connection string builder</span></span>

<span data-ttu-id="15868-170">Sie können <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> als stark typisierte Methode zum Erstellen von Verbindungszeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="15868-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="15868-171">Außerdem können damit Angriffe durch das Einschleusen von Verbindungszeichenfolgen verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="15868-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="15868-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="15868-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="15868-173">Standard</span><span class="sxs-lookup"><span data-stu-id="15868-173">Basic</span></span>

<span data-ttu-id="15868-174">Dies ist eine einfache Verbindungszeichenfolge mit freigegebenem Cache für verbesserte Parallelität.</span><span class="sxs-lookup"><span data-stu-id="15868-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```connectionstring
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="15868-175">Verschlüsselt</span><span class="sxs-lookup"><span data-stu-id="15868-175">Encrypted</span></span>

<span data-ttu-id="15868-176">Dies ist eine verschlüsselte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="15868-176">An encrypted database.</span></span>

```connectionstring
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="15868-177">Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="15868-177">Read-only</span></span>

<span data-ttu-id="15868-178">Dies ist eine schreibgeschützte Datenbank, die nicht von der App geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="15868-178">A read-only database that cannot be modified by the app.</span></span>

```connectionstring
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="15868-179">Im Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="15868-179">In-memory</span></span>

<span data-ttu-id="15868-180">Dies ist eine private In-Memory-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="15868-180">A private, in-memory database.</span></span>

```connectionstring
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="15868-181">Sharable In-Memory</span><span class="sxs-lookup"><span data-stu-id="15868-181">Sharable in-memory</span></span>

<span data-ttu-id="15868-182">Dies ist eine In-Memory-Datenbank, die wie anhand des Namens *Sharable* bereits zu erkennen ist freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="15868-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```connectionstring
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="15868-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15868-183">See also</span></span>

* [<span data-ttu-id="15868-184">Verbindungszeichenfolgen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="15868-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="15868-185">In-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="15868-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="15868-186">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="15868-186">Transactions</span></span>](transactions.md)
