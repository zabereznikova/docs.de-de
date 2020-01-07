---
title: Massen Einfügung
ms.date: 12/13/2019
description: Leistungs Tipps, die Sie verwenden können, wenn Sie zahlreiche Änderungen an der Datenbank vornehmen.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450297"
---
# <a name="bulk-insert"></a><span data-ttu-id="a60dd-103">Massen Einfügung</span><span class="sxs-lookup"><span data-stu-id="a60dd-103">Bulk insert</span></span>

<span data-ttu-id="a60dd-104">SQLite hat keine besondere Möglichkeit zum Massen Einfügen von Daten.</span><span class="sxs-lookup"><span data-stu-id="a60dd-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="a60dd-105">Stellen Sie Folgendes sicher, um beim Einfügen oder Aktualisieren von Daten eine optimale Leistung zu erzielen:</span><span class="sxs-lookup"><span data-stu-id="a60dd-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="a60dd-106">Verwenden Sie eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="a60dd-106">Use a transaction.</span></span>
- <span data-ttu-id="a60dd-107">Verwenden Sie denselben parametrisierten Befehl erneut.</span><span class="sxs-lookup"><span data-stu-id="a60dd-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="a60dd-108">Bei nachfolgenden Ausführungen wird die Kompilierung der ersten erneut verwendet.</span><span class="sxs-lookup"><span data-stu-id="a60dd-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
