---
title: In-Memory-Datenbanken
ms.date: 12/13/2019
description: In diesem Artikel erfahren Sie, wie Sie SQLite-In-Memory-Datenbanken verwenden.
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555366"
---
# <a name="in-memory-databases"></a>In-Memory-Datenbanken

SQLite-In-Memory-Datenbanken sind Datenbanken, die vollständig auf dem Arbeitsspeicher gespeichert sind, nicht auf einem Datenträger. Verwenden Sie den speziellen Datenquellendateiname `:memory:`, um eine In-Memory-Datenbank zu erstellen. Wenn die Verbindung beendet wird, wird die Datenbank gelöscht. Wenn `:memory:` verwendet wird, erstellt jede Verbindung ihre eigene Datenbank.

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Freigabefähige In-Memory-Datenbanken

In-Memory-Datenbanken können für mehrere Verbindungen freigegeben werden, indem in der Verbindungszeichenfolge `Mode=Memory` und `Cache=Shared` verwendet werden. Das `Data Source`-Schlüsselwort wird verwendet, um die In-Memory-Datenbank zu benennen. Verbindungszeichenfolgen, für die derselbe Name verwendet wird, greifen auf dieselbe In-Memory-Datenbank zu. Die Datenbank besteht, solange mindestens eine Verbindung zu ihr offen bleibt. Ein [Beispiel](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) hierfür finden Sie auf GitHub.

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
