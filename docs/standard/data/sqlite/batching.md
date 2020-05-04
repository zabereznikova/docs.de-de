---
title: Batchverarbeitung
ms.date: 12/13/2019
description: Hier erfahren Sie, wie Sie einen Batch mit SQL-Anweisungen in einem einzelnen Befehl ausführen.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450309"
---
# <a name="batching"></a><span data-ttu-id="5e20e-103">Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="5e20e-103">Batching</span></span>

<span data-ttu-id="5e20e-104">SQLite bietet keine native Unterstützung für die Batchausführung von SQL-Anweisungen in einem einzelnen Befehl.</span><span class="sxs-lookup"><span data-stu-id="5e20e-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="5e20e-105">Wegen fehlender Netzwerkbeteiligung würde diese Vorgehensweise ohnedies zu keiner Leistungssteigerung führen.</span><span class="sxs-lookup"><span data-stu-id="5e20e-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="5e20e-106">Aus Gründen der Benutzerfreundlichkeit implementiert Microsoft.Data.Sqlite trotzdem die Batchverarbeitung von Anweisungen, damit die Benutzung der anderer ADO.NET-Anbieter ähnelt.</span><span class="sxs-lookup"><span data-stu-id="5e20e-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="5e20e-107">Durch Aufrufen von <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType> werden so lange Anweisungen ausgeführt, bis die erste Anweisung Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e20e-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="5e20e-108">Durch Aufrufen von <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> wird die Ausführung von Anweisungen so lange fortgeführt, bis die nächste Anweisung Ergebnisse zurückgibt, oder bis das Ende des Batches erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="5e20e-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="5e20e-109">Rufen Sie <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> oder <xref:System.Data.Common.DbDataReader.Close%2A> auf, um die verbleibenden Anweisungen auszuführen, die noch nicht durch `NextResult()` verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="5e20e-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="5e20e-110">Wenn Sie keinen Datenleser freigeben, versucht der Finalizer, die verbleibenden Anweisungen auszuführen und ignoriert alle auftretenden Fehler.</span><span class="sxs-lookup"><span data-stu-id="5e20e-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="5e20e-111">Daher ist es wichtig, bei der Verwendung von Batches `DbDataReader`-Objekte freizugeben.</span><span class="sxs-lookup"><span data-stu-id="5e20e-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="5e20e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e20e-112">See also</span></span>

* [<span data-ttu-id="5e20e-113">Masseneinfügung</span><span class="sxs-lookup"><span data-stu-id="5e20e-113">Bulk Insert</span></span>](bulk-insert.md)
