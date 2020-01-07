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
# <a name="bulk-insert"></a>Massen Einfügung

SQLite hat keine besondere Möglichkeit zum Massen Einfügen von Daten. Stellen Sie Folgendes sicher, um beim Einfügen oder Aktualisieren von Daten eine optimale Leistung zu erzielen:

- Verwenden Sie eine Transaktion.
- Verwenden Sie denselben parametrisierten Befehl erneut. Bei nachfolgenden Ausführungen wird die Kompilierung der ersten erneut verwendet.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
