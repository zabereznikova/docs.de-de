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
# <a name="batching"></a>Batchverarbeitung

SQLite bietet keine native Unterstützung für die Batchausführung von SQL-Anweisungen in einem einzelnen Befehl. Wegen fehlender Netzwerkbeteiligung würde diese Vorgehensweise ohnedies zu keiner Leistungssteigerung führen. Aus Gründen der Benutzerfreundlichkeit implementiert Microsoft.Data.Sqlite trotzdem die Batchverarbeitung von Anweisungen, damit die Benutzung der anderer ADO.NET-Anbieter ähnelt.

Durch Aufrufen von <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType> werden so lange Anweisungen ausgeführt, bis die erste Anweisung Ergebnisse zurückgibt. Durch Aufrufen von <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> wird die Ausführung von Anweisungen so lange fortgeführt, bis die nächste Anweisung Ergebnisse zurückgibt, oder bis das Ende des Batches erreicht ist. Rufen Sie <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> oder <xref:System.Data.Common.DbDataReader.Close%2A> auf, um die verbleibenden Anweisungen auszuführen, die noch nicht durch `NextResult()` verarbeitet wurden. Wenn Sie keinen Datenleser freigeben, versucht der Finalizer, die verbleibenden Anweisungen auszuführen und ignoriert alle auftretenden Fehler. Daher ist es wichtig, bei der Verwendung von Batches `DbDataReader`-Objekte freizugeben.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>Siehe auch

* [Masseneinfügung](bulk-insert.md)
