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
# <a name="encryption"></a><span data-ttu-id="f7ed0-103">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="f7ed0-103">Encryption</span></span>

<span data-ttu-id="f7ed0-104">SQLite unterstützt das Verschlüsseln von Datenbankdateien standardmäßig nicht.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="f7ed0-105">Stattdessen müssen Sie eine geänderte Version von SQLite wie z. b. " [Siehe](https://www.hwaci.com/sw/sqlite/see.html)", " [sqlcipher](https://www.zetetic.net/sqlcipher/)", " [SQLiteCrypt](http://www.sqlite-crypt.com/)" oder " [wxSQLite3](https://utelle.github.io/wxsqlite3)" verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="f7ed0-106">In diesem Artikel wird die Verwendung eines nicht unterstützten Open Source-Builds von sqlcipher veranschaulicht, die Informationen gelten jedoch auch für andere Lösungen, da Sie im Allgemeinen das gleiche Muster befolgen.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="f7ed0-107">Installation</span><span class="sxs-lookup"><span data-stu-id="f7ed0-107">Installation</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="f7ed0-108">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="f7ed0-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="f7ed0-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f7ed0-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="f7ed0-110">Weitere Informationen zum Verwenden einer anderen nativen Bibliothek für die Verschlüsselung finden Sie unter [benutzerdefinierte SQLite-Versionen](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="f7ed0-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="f7ed0-111">Schlüssel angeben</span><span class="sxs-lookup"><span data-stu-id="f7ed0-111">Specify the key</span></span>

<span data-ttu-id="f7ed0-112">Um die Verschlüsselung zu aktivieren, geben Sie den Schlüssel mithilfe des Schlüssel Worts `Password` Verbindungs Zeichenfolge an</span><span class="sxs-lookup"><span data-stu-id="f7ed0-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="f7ed0-113">Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, um den Wert aus der Benutzereingabe hinzuzufügen oder zu aktualisieren, und vermeiden Sie einschleusungs Angriffe</span><span class="sxs-lookup"><span data-stu-id="f7ed0-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="f7ed0-114">Die Datenbank wird neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-114">Rekeying the database</span></span>

<span data-ttu-id="f7ed0-115">Wenn Sie den Verschlüsselungsschlüssel einer Datenbank ändern möchten, geben Sie eine `PRAGMA rekey` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="f7ed0-116">Geben Sie `NULL`an, um die Datenbank zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="f7ed0-117">Leider unterstützt SQLite keine Parameter in `PRAGMA` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="f7ed0-118">Verwenden Sie stattdessen die `quote()`-Funktion, um die SQL-Injektion zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f7ed0-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
