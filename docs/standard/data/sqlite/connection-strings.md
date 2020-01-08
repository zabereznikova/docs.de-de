---
title: Verbindungszeichenfolgen
ms.date: 12/13/2019
description: Die unterstützten Schlüsselwörter und Werte von Verbindungs Zeichenfolgen.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450273"
---
# <a name="connection-strings"></a>Verbindungszeichenfolgen

Eine Verbindungs Zeichenfolge wird verwendet, um anzugeben, wie eine Verbindung mit der Datenbank hergestellt wird. Verbindungs Zeichenfolgen in Microsoft. Data. sqlite Folgen der standardmäßigen [ADO.NET-Syntax](../../../framework/data/adonet/connection-strings.md) als eine durch Semikolons getrennte Liste von Schlüsselwörtern und Werten.

## <a name="keywords"></a>Stichwörter

Die folgenden Schlüsselwörter für Verbindungs Zeichenfolgen können mit "Microsoft. Data. sqlite" verwendet werden:

### <a name="data-source"></a>Datenquelle

Der Pfad zur Datenbankdatei. *DataSource* (ohne Leerzeichen) und *Dateiname* sind Aliase dieses Schlüssel Worts.

SQLite behandelt Pfade relativ zum aktuellen Arbeitsverzeichnis. Absolute Pfade können ebenfalls angegeben werden.

Wenn der Wert **leer**ist, erstellt SQLite eine temporäre Datenbank auf dem Datenträger, die gelöscht wird, wenn die Verbindung geschlossen wird.

Wenn `:memory:`, wird ein in-Memory Database verwendet. Weitere Informationen finden Sie unter [in-Memory-Datenbanken](in-memory-databases.md).

Pfade, die mit der `|DataDirectory|` Ersetzungs Zeichenfolge beginnen, werden wie relative Pfade behandelt. Wenn festgelegt, werden Pfade relativ zum Eigenschafts Wert der DataDirectory-Anwendungsdomäne erstellt.

Dieses Schlüsselwort unterstützt auch [URI-Dateinamen](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Modus

Der Verbindungs Modus.

| {2&gt;Wert&lt;2}           | Beschreibung                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| "Read-tecreate" | Öffnet die Datenbank zum Lesen und schreiben und erstellt diese, wenn Sie nicht vorhanden ist. Dies ist der Standardwert. |
| ReadWrite       | Öffnet die Datenbank zum Lesen und schreiben.                                                        |
| ReadOnly        | Öffnet die Datenbank im schreibgeschützten Modus.                                                              |
| Arbeitsspeicher          | Öffnet einen in-Memory Database.                                                                       |

### <a name="cache"></a>cache

Der von der Verbindung verwendete cachingmodus.

| {2&gt;Wert&lt;2}   | Beschreibung                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Default | Verwendet den Standardmodus der zugrunde liegenden SQLite-Bibliothek. Dies ist der Standardwert.                   |
| Private | Jede Verbindung verwendet einen privaten Cache.                                                          |
| Freigegeben  | Verbindungen nutzen einen Cache gemeinsam. Dieser Modus kann das Verhalten der Transaktion und der Tabellensperrung ändern. |

### <a name="password"></a>Kennwort

Der Verschlüsselungsschlüssel. Wenn angegeben, wird `PRAGMA key` unmittelbar nach dem Öffnen der Verbindung gesendet.

> [!WARNING]
> Das Kennwort hat keine Auswirkung, wenn die Verschlüsselung von der systemeigenen SQLite-Bibliothek nicht unterstützt

### <a name="foreign-keys"></a>Fremdschlüssel

Ein Wert, der angibt, ob Foreign Key-Einschränkungen aktiviert werden sollen.

| {2&gt;Wert&lt;2}   | Beschreibung
| ------- | --- |
| True    | Sendet `PRAGMA foreign_keys = 1` sofort nach dem Öffnen der Verbindung.
| Falsch   | Sendet `PRAGMA foreign_keys = 0` sofort nach dem Öffnen der Verbindung.
| (leer) | Sendet keine `PRAGMA foreign_keys`. Dies ist der Standardwert. |

Es ist nicht erforderlich, Fremdschlüssel zu aktivieren, wenn, wie in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS verwendet wurde, um die native SQLite-Bibliothek zu kompilieren.

### <a name="recursive-triggers"></a>Rekursive Trigger

Ein Wert, der angibt, ob rekursive Trigger aktiviert werden sollen.

| {2&gt;Wert&lt;2} | Beschreibung                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | Sendet `PRAGMA recursive_triggers` sofort nach dem Öffnen der Verbindung. |
| Falsch | Sendet keine `PRAGMA recursive_triggers`. Dies ist der Standardwert.              |

## <a name="connection-string-builder"></a>Verbindungs Zeichen folgen Generator

Sie können <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> als stark typisierte Methode zum Erstellen von Verbindungs Zeichenfolgen verwenden. Sie kann auch verwendet werden, um einschleusungs Angriffe für Verbindungs Zeichenfolgen zu

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Beispiele

### <a name="basic"></a>Standard

Eine einfache Verbindungs Zeichenfolge mit einem freigegebenen Cache für verbesserte Parallelität.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Verschlüsselt

Eine verschlüsselte Datenbank.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>Schreibgeschützt

Eine schreibgeschützte Datenbank, die nicht von der APP geändert werden kann.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>Im Arbeitsspeicher

Eine private, in-Memory Database.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>Sharable in-Memory

Ein Sharable, in-Memory Database durch den Namen *Sharable*identifiziert.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Siehe auch

* [Verbindungs Zeichenfolgen in ADO.net](../../../framework/data/adonet/connection-strings.md)
* [In-Memory-Datenbanken](in-memory-databases.md)
* [Transaktionen](transactions.md)
