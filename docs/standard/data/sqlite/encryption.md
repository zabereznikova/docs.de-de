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
# <a name="encryption"></a><span data-ttu-id="d1338-103">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="d1338-103">Encryption</span></span>

<span data-ttu-id="d1338-104">SQLite unterstützt das Verschlüsseln von Datenbankdateien standardmäßig nicht.</span><span class="sxs-lookup"><span data-stu-id="d1338-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="d1338-105">Stattdessen müssen Sie eine geänderte Version von SQLite wie [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) oder [wxSQLite3](https://utelle.github.io/wxsqlite3) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1338-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="d1338-106">In diesem Artikel wird die Verwendung eines nicht unterstützten Open-Source-Builds von SQLCipher veranschaulicht, die Informationen gelten jedoch auch für andere Lösungen, da sie im Allgemeinen das gleiche Muster befolgen.</span><span class="sxs-lookup"><span data-stu-id="d1338-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="d1338-107">Installation</span><span class="sxs-lookup"><span data-stu-id="d1338-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="d1338-108">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="d1338-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="d1338-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1338-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="d1338-110">Weitere Informationen zum Verwenden einer anderen nativen Bibliothek für die Verschlüsselung finden Sie unter [Benutzerdefinierte SQLite-Versionen](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="d1338-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="d1338-111">Angeben des Schlüssels</span><span class="sxs-lookup"><span data-stu-id="d1338-111">Specify the key</span></span>

<span data-ttu-id="d1338-112">Geben Sie den Schlüssel mithilfe Schlüsselworts `Password` für Verbindungszeichenfolgen an, um die Verschlüsselung für eine neue Datenbank zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d1338-112">To enable encryption on a new database, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="d1338-113">Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, um den Wert per Benutzereingabe hinzuzufügen oder zu aktualisieren und Angriffe durch das Einschleusen von Verbindungszeichenfolgen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d1338-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> <span data-ttu-id="d1338-114">Die Methode zum Ver- und Entschlüsseln vorhandener Datenbanken variiert je nach verwendeter Lösung.</span><span class="sxs-lookup"><span data-stu-id="d1338-114">The method for encrypting and decrypting existing databases varies depending on which solution you're using.</span></span> <span data-ttu-id="d1338-115">Beispielsweise müssen Sie für SQLCipher die Funktion `sqlcipher_export()` verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1338-115">For example, you need to use the `sqlcipher_export()` function on SQLCipher.</span></span> <span data-ttu-id="d1338-116">Weitere Informationen finden Sie in der Dokumentation zu Ihrer Lösung.</span><span class="sxs-lookup"><span data-stu-id="d1338-116">Check your solution's documentation for details.</span></span>

## <a name="rekeying-the-database"></a><span data-ttu-id="d1338-117">Neuvergabe von Schlüsseln für Datenbanken</span><span class="sxs-lookup"><span data-stu-id="d1338-117">Rekeying the database</span></span>

<span data-ttu-id="d1338-118">Wenn Sie den Schlüssel einer Datenbank ändern möchten, verwenden Sie eine `PRAGMA rekey`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d1338-118">If you want to change the key of an encrypted database, issue a `PRAGMA rekey` statement.</span></span>

<span data-ttu-id="d1338-119">Allerdings unterstützt SQLite keine Parameter in `PRAGMA`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d1338-119">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="d1338-120">Verwenden Sie stattdessen die `quote()`-Funktion, um die Einschleusung von SQL-Befehlen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d1338-120">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
