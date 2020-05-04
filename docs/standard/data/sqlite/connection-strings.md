---
title: Verbindungszeichenfolgen
ms.date: 12/13/2019
description: Hier werden die von Verbindungszeichenfolgen unterstützten Schlüsselwörter und Werte erläutert.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401196"
---
# <a name="connection-strings"></a>Verbindungszeichenfolgen

Mit einer Verbindungszeichenfolge wird angegeben, wie eine Verbindung zur Datenbank hergestellt werden soll. Verbindungszeichenfolgen in Microsoft.Data.Sqlite folgen als durch Semikolons getrennte Liste von Schlüsselwörtern und Werten auf die [ADO.NET-Standardsyntax](../../../framework/data/adonet/connection-strings.md).

## <a name="keywords"></a>Stichwörter

Die folgenden Schlüsselwörter für Verbindungszeichenfolgen können mit Microsoft.Data.Sqlite verwendet werden:

### <a name="data-source"></a>Datenquelle

Der Pfad zur Datenbankdatei. *DataSource* (ohne Leerzeichen) und *Filename* (Dateiname) sind Aliase dieses Schlüsselworts.

SQLite behandelt Pfade relativ zum aktuellen Arbeitsverzeichnis. Absolute Pfade können ebenfalls angegeben werden.

Im Falle von **empty** (leer) erstellt SQLite eine temporäre Datenbank auf dem Datenträger, die gelöscht wird, wenn diese Verbindung geschlossen wird.

Bei `:memory:` wird eine In-Memory-Datenbank verwendet. Weitere Informationen finden Sie unter [In-Memory-Datenbanken](in-memory-databases.md).

Pfade, die mit der Ersatzzeichenfolge `|DataDirectory|` beginnen, werden wie relative Pfade behandelt. Wenn dies festgelegt ist, werden Pfade relativ zum Eigenschaftswert der Anwendungsdomäne für DataDirectory erstellt.

Dieses Schlüsselwort unterstützt auch [URI-Dateinamen](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Modus

Dies ist der Verbindungsmodus.

| Wert           | Beschreibung                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Hiermit wird die Datenbank für Lese- und Schreibvorgänge geöffnet und ggf. erstellt, wenn sie nicht vorhanden ist. Dies ist die Standardeinstellung. |
| ReadWrite       | Hiermit wird die Datenbank für Lese- und Schreibvorgänge geöffnet.                                                        |
| ReadOnly        | Hiermit wird die Datenbank im schreibgeschützten Modus geöffnet.                                                              |
| Arbeitsspeicher          | Hiermit wird eine In-Memory-Datenbank geöffnet.                                                                       |

### <a name="cache"></a>cache

Hierbei handelt es sich um den von der Verbindung verwendeten Cachemodus.

| Wert   | Beschreibung                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Standard | Hiermit wird der Standardmodus der zugrunde liegenden SQLite-Bibliothek verwendet. Dies ist die Standardeinstellung.                   |
| Private | Jede Verbindung verwendet einen privaten Cache.                                                          |
| Shared  | Verbindungen nutzen einen Cache gemeinsam. Dieser Modus kann das Verhalten der Transaktion und der Tabellensperrung ändern. |

### <a name="password"></a>Kennwort

Der Verschlüsselungsschlüssel. Wenn dieser angegeben ist, wird `PRAGMA key` unmittelbar nach dem Öffnen der Verbindung gesendet.

> [!WARNING]
> Das Kennwort hat keine Auswirkung, wenn die Verschlüsselung von der nativen SQLite-Bibliothek nicht unterstützt wird.

### <a name="foreign-keys"></a>Fremdschlüssel

Dieser Wert gibt an, ob Fremdschlüsseleinschränkungen aktiviert werden sollen.

| Wert   | Beschreibung
| ------- | --- |
| True    | Hier wird `PRAGMA foreign_keys = 1` unmittelbar nach dem Öffnen der Verbindung gesendet.
| False   | Hier wird `PRAGMA foreign_keys = 0` unmittelbar nach dem Öffnen der Verbindung gesendet.
| (leer) | Hier wird `PRAGMA foreign_keys` nicht gesendet. Dies ist die Standardeinstellung. |

Fremdschlüssel müssen nicht aktiviert werden, wenn wie im Fall von e_sqlite3 „SQLITE_DEFAULT_FOREIGN_KEYS“ zum Kompilieren der nativen SQLite-Bibliothek verwendet wurde.

### <a name="recursive-triggers"></a>Rekursive Trigger

Mit diesem Wert wird angegeben, ob rekursive Trigger aktiviert werden sollen.

| Wert | Beschreibung                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | Hier wird `PRAGMA recursive_triggers` unmittelbar nach dem Öffnen der Verbindung gesendet. |
| False | Hier wird `PRAGMA recursive_triggers` nicht gesendet. Dies ist die Standardeinstellung.              |

## <a name="connection-string-builder"></a>Verbindungszeichenfolgen-Generator

Sie können <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> als stark typisierte Methode zum Erstellen von Verbindungszeichenfolgen verwenden. Außerdem können damit Angriffe durch das Einschleusen von Verbindungszeichenfolgen verhindert werden.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Beispiele

### <a name="basic"></a>Standard

Dies ist eine einfache Verbindungszeichenfolge mit freigegebenem Cache für verbesserte Parallelität.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Verschlüsselt

Dies ist eine verschlüsselte Datenbank.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>Schreibgeschützt

Dies ist eine schreibgeschützte Datenbank, die nicht von der App geändert werden kann.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>Im Arbeitsspeicher

Dies ist eine private In-Memory-Datenbank.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>Sharable In-Memory

Dies ist eine In-Memory-Datenbank, die wie anhand des Namens *Sharable* bereits zu erkennen ist freigegeben werden kann.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Siehe auch

* [Verbindungszeichenfolgen in ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [In-Memory-Datenbanken](in-memory-databases.md)
* [Transaktionen](transactions.md)
