---
title: Verbindungszeichenfolgen
ms.date: 12/13/2019
description: Die unterstützten Schlüsselwörter und Werte von Verbindungszeichenfolgen.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401196"
---
# <a name="connection-strings"></a>Verbindungszeichenfolgen

Eine Verbindungszeichenfolge wird verwendet, um anzugeben, wie eine Verbindung mit der Datenbank hergestellt werden soll. Verbindungszeichenfolgen in Microsoft.Data.Sqlite folgen der [Standard-ADO.NET Syntax](../../../framework/data/adonet/connection-strings.md) als semikolonngetrennte Liste von Schlüsselwörtern und Werten.

## <a name="keywords"></a>Keywords

Die folgenden Verbindungszeichenfolgenschlüsselwörter können mit Microsoft.Data.Sqlite verwendet werden:

### <a name="data-source"></a>Datenquelle

Der Pfad zur Datenbankdatei. *DataSource* (ohne Leerzeichen) und *Filename* sind Aliase dieses Schlüsselworts.

SQLite behandelt Pfade relativ zum aktuellen Arbeitsverzeichnis. Absolute Pfade können auch angegeben werden.

Wenn **leer**, erstellt SQLite eine temporäre Datenträgerdatenbank, die beim Schließen der Verbindung gelöscht wird.

Wenn `:memory:`, wird eine In-Memory-Datenbank verwendet. Weitere Informationen finden Sie [unter In-Memory-Datenbanken](in-memory-databases.md).

Pfade, die `|DataDirectory|` mit der Ersetzungszeichenfolge beginnen, werden wie relative Pfade behandelt. Wenn diese Einstellung festgelegt ist, werden Pfade relativ zum Eigenschaftswert der DataDirectory-Anwendungsdomäne erstellt.

Dieses Schlüsselwort unterstützt auch [URI Filenames](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Mode

Der Verbindungsmodus.

| value           | Beschreibung                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Öffnet die Datenbank zum Lesen und Schreiben und erstellt sie, wenn sie nicht vorhanden ist. Dies ist die Standardoption. |
| ReadWrite       | Öffnet die Datenbank zum Lesen und Schreiben.                                                        |
| ReadOnly        | Öffnet die Datenbank im schreibgeschützten Modus.                                                              |
| Arbeitsspeicher          | Öffnet eine In-Memory-Datenbank.                                                                       |

### <a name="cache"></a>Cache

Der caching-Modus, der von der Verbindung verwendet wird.

| value   | Beschreibung                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Standard | Verwendet den Standardmodus der zugrunde liegenden SQLite-Bibliothek. Dies ist die Standardoption.                   |
| Privat | Jede Verbindung verwendet einen privaten Cache.                                                          |
| Shared  | Verbindungen teilen sich einen Cache. Dieser Modus kann das Verhalten von Transaktionen und Tabellensperren ändern. |

### <a name="password"></a>Kennwort

Der Verschlüsselungsschlüssel. Wenn angegeben, `PRAGMA key` wird sofort nach dem Öffnen der Verbindung gesendet.

> [!WARNING]
> Das Kennwort hat keine Auswirkungen, wenn die Verschlüsselung von der nativen SQLite-Bibliothek nicht unterstützt wird.

### <a name="foreign-keys"></a>Fremdschlüssel

Ein Wert, der angibt, ob Fremdschlüsseleinschränkungen aktiviert werden sollen.

| value   | Beschreibung
| ------- | --- |
| True    | Sendet `PRAGMA foreign_keys = 1` unmittelbar nach dem Öffnen der Verbindung.
| False   | Sendet `PRAGMA foreign_keys = 0` unmittelbar nach dem Öffnen der Verbindung.
| (leer) | Sendet nicht `PRAGMA foreign_keys`. Dies ist die Standardoption. |

Es ist nicht erforderlich, Fremdschlüssel zu aktivieren, wenn, wie in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS zum Kompilieren der nativen SQLite-Bibliothek verwendet wurde.

### <a name="recursive-triggers"></a>Rekursive Trigger

Ein Wert, der angibt, ob rekursive Trigger aktiviert werden sollen.

| value | Beschreibung                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | Sendet `PRAGMA recursive_triggers` unmittelbar nach dem Öffnen der Verbindung. |
| False | Sendet nicht `PRAGMA recursive_triggers`. Dies ist die Standardoption.              |

## <a name="connection-string-builder"></a>Verbindungszeichenfolgen-Generator

Sie können <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> als stark typisierte Möglichkeit zum Erstellen von Verbindungszeichenfolgen verwenden. Es kann auch verwendet werden, um VerbindungszeichenfolgeNinjektionsangriffe zu verhindern.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Beispiele

### <a name="basic"></a>Basic

Eine grundlegende Verbindungszeichenfolge mit einem freigegebenen Cache für eine verbesserte Parallelität.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Verschlüsselt

Eine verschlüsselte Datenbank.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>Schreibgeschützt

Eine schreibgeschützte Datenbank, die von der App nicht geändert werden kann.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>In-Memory

Eine private, in-Memory-Datenbank.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>Sharable in-memory

Eine sharable, in-memory-Datenbank, die mit dem Namen *Sharable*identifiziert wird.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Weitere Informationen

* [Verbindungszeichenfolgen in ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [In-Memory-Datenbanken](in-memory-databases.md)
* [Transaktionen](transactions.md)
