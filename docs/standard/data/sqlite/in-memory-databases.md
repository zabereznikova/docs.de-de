---
title: In-Memory-Datenbanken
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie in-memory SQLite-Datenbanken verwenden.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391207"
---
# <a name="in-memory-databases"></a>In-Memory-Datenbanken

SQLite-In-Memory-Datenbanken sind Datenbanken, die vollständig im Arbeitsspeicher und nicht auf dem Datenträger gespeichert sind. Verwenden Sie den speziellen `:memory:` Datenquellendateinamen, um eine In-Memory-Datenbank zu erstellen. Wenn die Verbindung geschlossen wird, wird die Datenbank gelöscht. Bei `:memory:`Verwendung von erstellt jede Verbindung eine eigene Datenbank.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Gemeinsam nutzende In-Memory-Datenbanken

In-Memory-Datenbanken können zwischen mehreren Verbindungen `Mode=Memory` `Cache=Shared` mithilfe und in der Verbindungszeichenfolge gemeinsam genutzt werden. Das `Data Source` Schlüsselwort wird verwendet, um der Speicherdatenbank einen Namen zu geben. Verbindungszeichenfolgen mit demselben Namen greifen auf dieselbe Speicherdatenbank zu. Die Datenbank bleibt bestehen, solange mindestens eine Verbindung zu ihr geöffnet bleibt. Ein [Beispiel,](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) das dies veranschaulicht, ist auf GitHub verfügbar.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
