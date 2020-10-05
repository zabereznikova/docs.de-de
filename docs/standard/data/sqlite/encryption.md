---
title: Verschlüsselung
ms.date: 09/08/2020
description: Informationen zur Verschlüsselung einer Datenbankdatei
ms.openlocfilehash: 1b33e1510a269aba87caba2cd39faab33791aa55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203409"
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

Geben Sie den Schlüssel mithilfe Schlüsselworts `Password` für Verbindungszeichenfolgen an, um die Verschlüsselung für eine neue Datenbank zu aktivieren. Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, um den Wert per Benutzereingabe hinzuzufügen oder zu aktualisieren und Angriffe durch das Einschleusen von Verbindungszeichenfolgen zu vermeiden.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> Die Methode zum Ver- und Entschlüsseln vorhandener Datenbanken variiert je nach verwendeter Lösung. Beispielsweise müssen Sie für SQLCipher die Funktion `sqlcipher_export()` verwenden. Weitere Informationen finden Sie in der Dokumentation zu Ihrer Lösung.

## <a name="rekeying-the-database"></a>Neuvergabe von Schlüsseln für Datenbanken

Wenn Sie den Schlüssel einer Datenbank ändern möchten, verwenden Sie eine `PRAGMA rekey`-Anweisung.

Allerdings unterstützt SQLite keine Parameter in `PRAGMA`-Anweisungen. Verwenden Sie stattdessen die `quote()`-Funktion, um die Einschleusung von SQL-Befehlen zu verhindern.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
