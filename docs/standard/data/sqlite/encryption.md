---
title: Verschlüsselung
ms.date: 12/13/2019
description: Informationen zur Verschlüsselung einer Datenbankdatei
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450483"
---
# <a name="encryption"></a>Verschlüsselung

SQLite unterstützt das Verschlüsseln von Datenbankdateien standardmäßig nicht. Stattdessen müssen Sie eine geänderte Version von SQLite wie [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) oder [wxSQLite3](https://utelle.github.io/wxsqlite3) verwenden. In diesem Artikel wird die Verwendung eines nicht unterstützten Open-Source-Builds von SQLCipher veranschaulicht, die Informationen gelten jedoch auch für andere Lösungen, da sie im Allgemeinen das gleiche Muster befolgen.

## <a name="installation"></a>Installation

### <a name="net-core-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Weitere Informationen zum Verwenden einer anderen nativen Bibliothek für die Verschlüsselung finden Sie unter [Benutzerdefinierte SQLite-Versionen](custom-versions.md).

## <a name="specify-the-key"></a>Angeben des Schlüssels

Geben Sie den Schlüssel mithilfe Schlüsselworts `Password` für Verbindungszeichenfolgen an, um die Verschlüsselung zu aktivieren. Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, um den Wert per Benutzereingabe hinzuzufügen oder zu aktualisieren und Angriffe durch das Einschleusen von Verbindungszeichenfolgen zu vermeiden.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>Neuvergabe von Schlüsseln für Datenbanken

Wenn Sie den Verschlüsselungsschlüssel einer Datenbank ändern möchten, verwenden Sie eine `PRAGMA rekey`-Anweisung. Geben Sie `NULL` an, um die Datenbank zu entschlüsseln.

Allerdings unterstützt SQLite keine Parameter in `PRAGMA`-Anweisungen. Verwenden Sie stattdessen die `quote()`-Funktion, um die Einschleusung von SQL-Befehlen zu verhindern.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
