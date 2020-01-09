---
title: Verschlüsselung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie Ihre Datenbankdatei verschlüsseln.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450483"
---
# <a name="encryption"></a>Verschlüsselung

SQLite unterstützt das Verschlüsseln von Datenbankdateien standardmäßig nicht. Stattdessen müssen Sie eine geänderte Version von SQLite wie z. b. " [Siehe](https://www.hwaci.com/sw/sqlite/see.html)", " [sqlcipher](https://www.zetetic.net/sqlcipher/)", " [SQLiteCrypt](http://www.sqlite-crypt.com/)" oder " [wxSQLite3](https://utelle.github.io/wxsqlite3)" verwenden. In diesem Artikel wird die Verwendung eines nicht unterstützten Open Source-Builds von sqlcipher veranschaulicht, die Informationen gelten jedoch auch für andere Lösungen, da Sie im Allgemeinen das gleiche Muster befolgen.

## <a name="installation"></a>Installation

### <a name="net-core-clitabnetcore-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Weitere Informationen zum Verwenden einer anderen nativen Bibliothek für die Verschlüsselung finden Sie unter [benutzerdefinierte SQLite-Versionen](custom-versions.md).

## <a name="specify-the-key"></a>Schlüssel angeben

Um die Verschlüsselung zu aktivieren, geben Sie den Schlüssel mithilfe des Schlüssel Worts `Password` Verbindungs Zeichenfolge an Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, um den Wert aus der Benutzereingabe hinzuzufügen oder zu aktualisieren, und vermeiden Sie einschleusungs Angriffe

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>Die Datenbank wird neu erstellt.

Wenn Sie den Verschlüsselungsschlüssel einer Datenbank ändern möchten, geben Sie eine `PRAGMA rekey` Anweisung aus. Geben Sie `NULL`an, um die Datenbank zu entschlüsseln.

Leider unterstützt SQLite keine Parameter in `PRAGMA` Anweisungen. Verwenden Sie stattdessen die `quote()`-Funktion, um die SQL-Injektion zu verhindern.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
