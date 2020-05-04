---
title: Datenbankfehler
ms.date: 12/13/2019
description: In diesem Artikel wird beschrieben, wie die Bibliothek Datenbankfehler und erneute Versuche behandelt.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450489"
---
# <a name="database-errors"></a><span data-ttu-id="5dab3-103">Datenbankfehler</span><span class="sxs-lookup"><span data-stu-id="5dab3-103">Database errors</span></span>

<span data-ttu-id="5dab3-104"><xref:Microsoft.Data.Sqlite.SqliteException> wird ausgelöst, wenn ein SQLite-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="5dab3-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="5dab3-105">Die Meldung wird von SQLite bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5dab3-105">The message is provided by SQLite.</span></span> <span data-ttu-id="5dab3-106">Die Eigenschaften `SqliteErrorCode` und `SqliteExtendedErrorCode` enthalten den SQLite-[Ergebniscode](https://www.sqlite.org/rescode.html) des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="5dab3-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="5dab3-107">Fehler können immer dann auftreten, wenn Microsoft.Data.Sqlite mit der nativen SQLite-Bibliothek interagiert.</span><span class="sxs-lookup"><span data-stu-id="5dab3-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="5dab3-108">In der folgenden Liste sind die Szenarios aufgeführt, in denen üblicherweise Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="5dab3-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="5dab3-109">Öffnen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="5dab3-109">Opening a connection.</span></span>
* <span data-ttu-id="5dab3-110">Beginnen einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="5dab3-110">Beginning a transaction.</span></span>
* <span data-ttu-id="5dab3-111">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="5dab3-111">Executing a command.</span></span>
* <span data-ttu-id="5dab3-112">Aufrufen von <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dab3-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="5dab3-113">Denken Sie sorgfältig darüber nach, wie Ihre App diese Fehler behandeln soll.</span><span class="sxs-lookup"><span data-stu-id="5dab3-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="5dab3-114">Sperrung, erneute Versuche und Timeouts</span><span class="sxs-lookup"><span data-stu-id="5dab3-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="5dab3-115">SQLite ist aggressiv, was das Sperren von Tabellen und Datenbankdateien betrifft.</span><span class="sxs-lookup"><span data-stu-id="5dab3-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="5dab3-116">Wenn Ihre App gleichzeitigen Datenbankzugriff ermöglicht, treten wahrscheinlich Fehler aufgrund von starker Auslastung und Sperrung auf.</span><span class="sxs-lookup"><span data-stu-id="5dab3-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="5dab3-117">Sie können viele Fehler minimieren, indem Sie einen [gemeinsamen Cache](connection-strings.md#cache) und [Write-Ahead-Protokollierung](async.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dab3-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="5dab3-118">Wenn Microsoft.Data.Sqlite einen Fehler aufgrund von starker Auslastung oder Sperrung feststellt, wird automatisch erneut versucht, den entsprechenden Befehl auszuführen, bis er erfolgreich ausgeführt wurde oder ein Timeout für den Befehl auftritt.</span><span class="sxs-lookup"><span data-stu-id="5dab3-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="5dab3-119">Sie können den Zeitraum für das Timeout von Befehlen verlängern, indem Sie <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="5dab3-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="5dab3-120">Der Standardzeitraum bis zum Timeout beträgt 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="5dab3-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="5dab3-121">Der Wert `0` bedeutet, dass kein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="5dab3-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="5dab3-122">Manchmal muss Microsoft.Data.Sqlite ein implizites Befehlsobjekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dab3-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="5dab3-123">Zum Beispiel bei BeginTransaction.</span><span class="sxs-lookup"><span data-stu-id="5dab3-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="5dab3-124">Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>, um den Zeitraum bis zum Timeout für diese Befehle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5dab3-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="5dab3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dab3-125">See also</span></span>

* [<span data-ttu-id="5dab3-126">Ergebnis- und Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="5dab3-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="5dab3-127">Dateisperrung und Parallelität in SQLite 3</span><span class="sxs-lookup"><span data-stu-id="5dab3-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="5dab3-128">Modus mit gemeinsamem Cache in SQLite</span><span class="sxs-lookup"><span data-stu-id="5dab3-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="5dab3-129">Write-Ahead-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="5dab3-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
