---
title: Verbindungszeichenfolgen
ms.date: 12/13/2019
description: Die unterstützten Schlüsselwörter und Werte von Verbindungs Zeichenfolgen.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450273"
---
# <a name="connection-strings"></a><span data-ttu-id="cbcb1-103">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="cbcb1-103">Connection strings</span></span>

<span data-ttu-id="cbcb1-104">Eine Verbindungs Zeichenfolge wird verwendet, um anzugeben, wie eine Verbindung mit der Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="cbcb1-105">Verbindungs Zeichenfolgen in Microsoft. Data. sqlite Folgen der standardmäßigen [ADO.NET-Syntax](../../../framework/data/adonet/connection-strings.md) als eine durch Semikolons getrennte Liste von Schlüsselwörtern und Werten.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="cbcb1-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="cbcb1-106">Keywords</span></span>

<span data-ttu-id="cbcb1-107">Die folgenden Schlüsselwörter für Verbindungs Zeichenfolgen können mit "Microsoft. Data. sqlite" verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cbcb1-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="cbcb1-108">Datenquelle</span><span class="sxs-lookup"><span data-stu-id="cbcb1-108">Data source</span></span>

<span data-ttu-id="cbcb1-109">Der Pfad zur Datenbankdatei.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-109">The path to the database file.</span></span> <span data-ttu-id="cbcb1-110">*DataSource* (ohne Leerzeichen) und *Dateiname* sind Aliase dieses Schlüssel Worts.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="cbcb1-111">SQLite behandelt Pfade relativ zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="cbcb1-112">Absolute Pfade können ebenfalls angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="cbcb1-113">Wenn der Wert **leer**ist, erstellt SQLite eine temporäre Datenbank auf dem Datenträger, die gelöscht wird, wenn die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="cbcb1-114">Wenn `:memory:`, wird ein in-Memory Database verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="cbcb1-115">Weitere Informationen finden Sie unter [in-Memory-Datenbanken](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="cbcb1-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="cbcb1-116">Pfade, die mit der `|DataDirectory|` Ersetzungs Zeichenfolge beginnen, werden wie relative Pfade behandelt.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="cbcb1-117">Wenn festgelegt, werden Pfade relativ zum Eigenschafts Wert der DataDirectory-Anwendungsdomäne erstellt.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="cbcb1-118">Dieses Schlüsselwort unterstützt auch [URI-Dateinamen](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="cbcb1-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="cbcb1-119">Modus</span><span class="sxs-lookup"><span data-stu-id="cbcb1-119">Mode</span></span>

<span data-ttu-id="cbcb1-120">Der Verbindungs Modus.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-120">The connection mode.</span></span>

| <span data-ttu-id="cbcb1-121">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="cbcb1-121">Value</span></span>           | <span data-ttu-id="cbcb1-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbcb1-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cbcb1-123">"Read-tecreate"</span><span class="sxs-lookup"><span data-stu-id="cbcb1-123">ReadWriteCreate</span></span> | <span data-ttu-id="cbcb1-124">Öffnet die Datenbank zum Lesen und schreiben und erstellt diese, wenn Sie nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="cbcb1-125">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-125">This is the default.</span></span> |
| <span data-ttu-id="cbcb1-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cbcb1-126">ReadWrite</span></span>       | <span data-ttu-id="cbcb1-127">Öffnet die Datenbank zum Lesen und schreiben.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="cbcb1-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="cbcb1-128">ReadOnly</span></span>        | <span data-ttu-id="cbcb1-129">Öffnet die Datenbank im schreibgeschützten Modus.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="cbcb1-130">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="cbcb1-130">Memory</span></span>          | <span data-ttu-id="cbcb1-131">Öffnet einen in-Memory Database.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="cbcb1-132">cache</span><span class="sxs-lookup"><span data-stu-id="cbcb1-132">Cache</span></span>

<span data-ttu-id="cbcb1-133">Der von der Verbindung verwendete cachingmodus.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="cbcb1-134">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="cbcb1-134">Value</span></span>   | <span data-ttu-id="cbcb1-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbcb1-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cbcb1-136">Default</span><span class="sxs-lookup"><span data-stu-id="cbcb1-136">Default</span></span> | <span data-ttu-id="cbcb1-137">Verwendet den Standardmodus der zugrunde liegenden SQLite-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="cbcb1-138">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-138">This is the default.</span></span>                   |
| <span data-ttu-id="cbcb1-139">Private</span><span class="sxs-lookup"><span data-stu-id="cbcb1-139">Private</span></span> | <span data-ttu-id="cbcb1-140">Jede Verbindung verwendet einen privaten Cache.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="cbcb1-141">Freigegeben</span><span class="sxs-lookup"><span data-stu-id="cbcb1-141">Shared</span></span>  | <span data-ttu-id="cbcb1-142">Verbindungen nutzen einen Cache gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-142">Connections share a cache.</span></span> <span data-ttu-id="cbcb1-143">Dieser Modus kann das Verhalten der Transaktion und der Tabellensperrung ändern.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="cbcb1-144">Kennwort</span><span class="sxs-lookup"><span data-stu-id="cbcb1-144">Password</span></span>

<span data-ttu-id="cbcb1-145">Der Verschlüsselungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-145">The encryption key.</span></span> <span data-ttu-id="cbcb1-146">Wenn angegeben, wird `PRAGMA key` unmittelbar nach dem Öffnen der Verbindung gesendet.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="cbcb1-147">Das Kennwort hat keine Auswirkung, wenn die Verschlüsselung von der systemeigenen SQLite-Bibliothek nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="cbcb1-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="cbcb1-148">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="cbcb1-148">Foreign Keys</span></span>

<span data-ttu-id="cbcb1-149">Ein Wert, der angibt, ob Foreign Key-Einschränkungen aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="cbcb1-150">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="cbcb1-150">Value</span></span>   | <span data-ttu-id="cbcb1-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbcb1-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="cbcb1-152">True</span><span class="sxs-lookup"><span data-stu-id="cbcb1-152">True</span></span>    | <span data-ttu-id="cbcb1-153">Sendet `PRAGMA foreign_keys = 1` sofort nach dem Öffnen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="cbcb1-154">Falsch</span><span class="sxs-lookup"><span data-stu-id="cbcb1-154">False</span></span>   | <span data-ttu-id="cbcb1-155">Sendet `PRAGMA foreign_keys = 0` sofort nach dem Öffnen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="cbcb1-156">(leer)</span><span class="sxs-lookup"><span data-stu-id="cbcb1-156">(empty)</span></span> | <span data-ttu-id="cbcb1-157">Sendet keine `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="cbcb1-158">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-158">This is the default.</span></span> |

<span data-ttu-id="cbcb1-159">Es ist nicht erforderlich, Fremdschlüssel zu aktivieren, wenn, wie in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS verwendet wurde, um die native SQLite-Bibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="cbcb1-160">Rekursive Trigger</span><span class="sxs-lookup"><span data-stu-id="cbcb1-160">Recursive triggers</span></span>

<span data-ttu-id="cbcb1-161">Ein Wert, der angibt, ob rekursive Trigger aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="cbcb1-162">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="cbcb1-162">Value</span></span> | <span data-ttu-id="cbcb1-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbcb1-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="cbcb1-164">True</span><span class="sxs-lookup"><span data-stu-id="cbcb1-164">True</span></span>  | <span data-ttu-id="cbcb1-165">Sendet `PRAGMA recursive_triggers` sofort nach dem Öffnen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="cbcb1-166">Falsch</span><span class="sxs-lookup"><span data-stu-id="cbcb1-166">False</span></span> | <span data-ttu-id="cbcb1-167">Sendet keine `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="cbcb1-168">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="cbcb1-169">Verbindungs Zeichen folgen Generator</span><span class="sxs-lookup"><span data-stu-id="cbcb1-169">Connection string builder</span></span>

<span data-ttu-id="cbcb1-170">Sie können <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> als stark typisierte Methode zum Erstellen von Verbindungs Zeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="cbcb1-171">Sie kann auch verwendet werden, um einschleusungs Angriffe für Verbindungs Zeichenfolgen zu</span><span class="sxs-lookup"><span data-stu-id="cbcb1-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="cbcb1-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cbcb1-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="cbcb1-173">Standard</span><span class="sxs-lookup"><span data-stu-id="cbcb1-173">Basic</span></span>

<span data-ttu-id="cbcb1-174">Eine einfache Verbindungs Zeichenfolge mit einem freigegebenen Cache für verbesserte Parallelität.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="cbcb1-175">Verschlüsselt</span><span class="sxs-lookup"><span data-stu-id="cbcb1-175">Encrypted</span></span>

<span data-ttu-id="cbcb1-176">Eine verschlüsselte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="cbcb1-177">Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="cbcb1-177">Read-only</span></span>

<span data-ttu-id="cbcb1-178">Eine schreibgeschützte Datenbank, die nicht von der APP geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="cbcb1-179">Im Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="cbcb1-179">In-memory</span></span>

<span data-ttu-id="cbcb1-180">Eine private, in-Memory Database.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="cbcb1-181">Sharable in-Memory</span><span class="sxs-lookup"><span data-stu-id="cbcb1-181">Sharable in-memory</span></span>

<span data-ttu-id="cbcb1-182">Ein Sharable, in-Memory Database durch den Namen *Sharable*identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cbcb1-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="cbcb1-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbcb1-183">See also</span></span>

* [<span data-ttu-id="cbcb1-184">Verbindungs Zeichenfolgen in ADO.net</span><span class="sxs-lookup"><span data-stu-id="cbcb1-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="cbcb1-185">In-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="cbcb1-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="cbcb1-186">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="cbcb1-186">Transactions</span></span>](transactions.md)
