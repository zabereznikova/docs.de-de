---
title: Datenbankfehler
ms.date: 12/13/2019
description: Beschreibt, wie Datenbankfehler und-Zurückhaltung von der Bibliothek behandelt werden.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450489"
---
# <a name="database-errors"></a><span data-ttu-id="6684e-103">Datenbankfehler</span><span class="sxs-lookup"><span data-stu-id="6684e-103">Database errors</span></span>

<span data-ttu-id="6684e-104"><xref:Microsoft.Data.Sqlite.SqliteException> wird ausgelöst, wenn ein sqlite-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="6684e-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="6684e-105">Die Meldung wird von SQLite bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6684e-105">The message is provided by SQLite.</span></span> <span data-ttu-id="6684e-106">Die Eigenschaften `SqliteErrorCode` und `SqliteExtendedErrorCode` enthalten den SQLite- [Ergebniscode](https://www.sqlite.org/rescode.html) des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="6684e-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="6684e-107">Fehler können immer auftreten, wenn "Microsoft. Data. sqlite" mit der systemeigenen SQLite-Bibliothek interagiert.</span><span class="sxs-lookup"><span data-stu-id="6684e-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="6684e-108">In der folgenden Liste werden häufige Szenarien angezeigt, in denen Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="6684e-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="6684e-109">Öffnen einer Verbindung.</span><span class="sxs-lookup"><span data-stu-id="6684e-109">Opening a connection.</span></span>
* <span data-ttu-id="6684e-110">Beginnen einer Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6684e-110">Beginning a transaction.</span></span>
* <span data-ttu-id="6684e-111">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="6684e-111">Executing a command.</span></span>
* <span data-ttu-id="6684e-112">Aufrufen von <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span><span class="sxs-lookup"><span data-stu-id="6684e-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="6684e-113">Berücksichtigen Sie sorgfältig, wie Ihre APP diese Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="6684e-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="6684e-114">Sperren, Wiederholungen und Timeouts</span><span class="sxs-lookup"><span data-stu-id="6684e-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="6684e-115">SQLite ist aggressiv, wenn es um das Sperren von Tabellen und Datenbankdateien geht.</span><span class="sxs-lookup"><span data-stu-id="6684e-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="6684e-116">Wenn Ihre APP gleichzeitigen Datenbankzugriff ermöglicht, treten wahrscheinlich Fehler aufgrund von ausgelasteten und gesperrten Fehlern auf.</span><span class="sxs-lookup"><span data-stu-id="6684e-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="6684e-117">Sie können viele Fehler verringern, indem Sie einen frei [gegebenen Cache](connection-strings.md#cache) und eine [Write-Ahead-Protokollierung](async.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="6684e-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="6684e-118">Wenn "Microsoft. Data. sqlite" einen stark ausgelasteten oder gesperrten Fehler feststellt, wird der Vorgang automatisch wiederholt, bis der Vorgang erfolgreich ist oder das Befehls Timeout erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="6684e-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="6684e-119">Sie können das Timeout des Befehls erhöhen, indem Sie <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>festlegen.</span><span class="sxs-lookup"><span data-stu-id="6684e-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="6684e-120">Der Standardwert für das Timeout beträgt 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="6684e-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="6684e-121">Der Wert `0` bedeutet, dass kein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="6684e-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="6684e-122">Microsoft. Data. sqlite muss manchmal ein implizites Befehls Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="6684e-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="6684e-123">Beispielsweise während BeginTransaction.</span><span class="sxs-lookup"><span data-stu-id="6684e-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="6684e-124">Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>, um das Timeout für diese Befehle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6684e-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="6684e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6684e-125">See also</span></span>

* [<span data-ttu-id="6684e-126">SQLite-Fehler Codes</span><span class="sxs-lookup"><span data-stu-id="6684e-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="6684e-127">Dateisperren in SQLite</span><span class="sxs-lookup"><span data-stu-id="6684e-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="6684e-128">Modus für freigegebenen Cache</span><span class="sxs-lookup"><span data-stu-id="6684e-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="6684e-129">Write-Ahead-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="6684e-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
