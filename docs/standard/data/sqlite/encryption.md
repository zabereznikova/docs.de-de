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
# <a name="encryption"></a><span data-ttu-id="b30c9-103">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="b30c9-103">Encryption</span></span>

<span data-ttu-id="b30c9-104">SQLite unterstützt das Verschlüsseln von Datenbankdateien standardmäßig nicht.</span><span class="sxs-lookup"><span data-stu-id="b30c9-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="b30c9-105">Stattdessen müssen Sie eine geänderte Version von SQLite wie [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) oder [wxSQLite3](https://utelle.github.io/wxsqlite3) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b30c9-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="b30c9-106">In diesem Artikel wird die Verwendung eines nicht unterstützten Open-Source-Builds von SQLCipher veranschaulicht, die Informationen gelten jedoch auch für andere Lösungen, da sie im Allgemeinen das gleiche Muster befolgen.</span><span class="sxs-lookup"><span data-stu-id="b30c9-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="b30c9-107">Installation</span><span class="sxs-lookup"><span data-stu-id="b30c9-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="b30c9-108">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="b30c9-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="b30c9-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b30c9-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="b30c9-110">Weitere Informationen zum Verwenden einer anderen nativen Bibliothek für die Verschlüsselung finden Sie unter [Benutzerdefinierte SQLite-Versionen](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="b30c9-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="b30c9-111">Angeben des Schlüssels</span><span class="sxs-lookup"><span data-stu-id="b30c9-111">Specify the key</span></span>

<span data-ttu-id="b30c9-112">Geben Sie den Schlüssel mithilfe Schlüsselworts `Password` für Verbindungszeichenfolgen an, um die Verschlüsselung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b30c9-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="b30c9-113">Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, um den Wert per Benutzereingabe hinzuzufügen oder zu aktualisieren und Angriffe durch das Einschleusen von Verbindungszeichenfolgen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b30c9-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="b30c9-114">Neuvergabe von Schlüsseln für Datenbanken</span><span class="sxs-lookup"><span data-stu-id="b30c9-114">Rekeying the database</span></span>

<span data-ttu-id="b30c9-115">Wenn Sie den Verschlüsselungsschlüssel einer Datenbank ändern möchten, verwenden Sie eine `PRAGMA rekey`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b30c9-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="b30c9-116">Geben Sie `NULL` an, um die Datenbank zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b30c9-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="b30c9-117">Allerdings unterstützt SQLite keine Parameter in `PRAGMA`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b30c9-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="b30c9-118">Verwenden Sie stattdessen die `quote()`-Funktion, um die Einschleusung von SQL-Befehlen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b30c9-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
