---
title: In-Memory-Datenbanken
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie in-Memory-SQLite-Datenbanken verwenden.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450465"
---
# <a name="in-memory-databases"></a>In-Memory-Datenbanken

SQLite-in-Memory-Datenbanken sind Datenbanken, die vollständig im Arbeitsspeicher gespeichert sind, nicht auf Verwenden Sie den Dateinamen der speziellen Datenquelle `:memory:`, um eine in-Memory Database zu erstellen. Wenn die Verbindung geschlossen wird, wird die Datenbank gelöscht. Wenn Sie `:memory:`verwenden, erstellt jede Verbindung eine eigene Datenbank.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Share Bare in-Memory-Datenbanken

In-Memory-Datenbanken können mithilfe von `Mode=Memory` und `Cache=Shared` in der Verbindungs Zeichenfolge von mehreren Verbindungen gemeinsam genutzt werden. Das `Data Source`-Schlüsselwort wird verwendet, um dem in-Memory Database einen Namen zu übergeben. Verbindungs Zeichenfolgen, die denselben Namen verwenden, greifen auf denselben in-Memory Database zu. Die Datenbank bleibt bestehen, solange mindestens eine Verbindung mit ihr geöffnet bleibt. Ein [Beispiel](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) , das zeigt, ist auf GitHub verfügbar.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
