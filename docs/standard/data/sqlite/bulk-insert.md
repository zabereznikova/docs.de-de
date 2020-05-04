---
title: Masseneinfügung
ms.date: 12/13/2019
description: Tipps für die Leistung, die Sie verwenden können, wenn Sie zahlreiche Änderungen an der Datenbank vornehmen
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450297"
---
# <a name="bulk-insert"></a>Masseneinfügung

SQLite verfügt über keine besondere Möglichkeit zur Masseneinfügung von Daten. Stellen Sie sicher, dass Sie wie folgt vorgehen, um beim Einfügen oder Aktualisieren von Daten eine optimale Leistung zu erzielen:

- Verwenden Sie eine Transaktion.
- Verwenden Sie den gleichen parametrisierten Befehl mehrmals. Bei nachfolgenden Ausführungen wird die Kompilierung des ersten Befehls erneut verwendet.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
