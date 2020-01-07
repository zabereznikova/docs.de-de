---
title: Batchverarbeitung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie einen Batch von SQL-Anweisungen in einem einzelnen Befehl ausführen.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450309"
---
# <a name="batching"></a><span data-ttu-id="9b443-103">Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="9b443-103">Batching</span></span>

<span data-ttu-id="9b443-104">SQLite unterstützt die Batch Verarbeitung von SQL-Anweisungen nicht in einem einzigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="9b443-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="9b443-105">Aber da kein Netzwerk beteiligt ist, würde die Leistung trotzdem nicht beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="9b443-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="9b443-106">Microsoft. Data. sqlite implementiert jedoch die Anweisungs Batch Verarbeitung als Vereinfachung, damit Sie sich besser verhält wie andere ADO.NET-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="9b443-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="9b443-107">Wenn Sie <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>aufrufen, werden-Anweisungen bis zum ersten ausgeführt, der Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9b443-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="9b443-108">Das Aufrufen von <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> setzt die Ausführung von-Anweisungen bis zum nächsten zurück, das Ergebnisse zurückgibt, oder bis das Ende des Batches erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="9b443-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="9b443-109">Durch Aufrufen von <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> oder <xref:System.Data.Common.DbDataReader.Close%2A> werden alle verbleibenden-Anweisungen ausgeführt, die nicht von `NextResult()`verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="9b443-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="9b443-110">Wenn Sie keinen Daten Leser verwerfen, versucht der Finalizer, die restlichen Anweisungen auszuführen, aber alle auftretenden Fehler werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9b443-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="9b443-111">Aus diesem Grund ist es wichtig, `DbDataReader` Objekte bei der Verwendung von Batches zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="9b443-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="9b443-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b443-112">See also</span></span>

* [<span data-ttu-id="9b443-113">Massen Einfügung</span><span class="sxs-lookup"><span data-stu-id="9b443-113">Bulk Insert</span></span>](bulk-insert.md)
