---
title: Benutzerdefinierte SQLite-Versionen
ms.date: 05/14/2020
description: Hier erfahren Sie, wie Sie eine benutzerdefinierte Version der nativen SQLite-Bibliothek verwenden.
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440836"
---
# <a name="custom-sqlite-versions"></a>Benutzerdefinierte SQLite-Versionen

`Microsoft.Data.Sqlite` basiert auf `SQLitePCLRaw`. Sie können benutzerdefinierte Versionen der nativen SQLite-Bibliothek verwenden, indem Sie ein Bundle verwenden oder einen `SQLitePCLRaw`-Anbieter konfigurieren.

## <a name="bundles"></a>Bundles

`SQLitePCLRaw` bietet benutzerfreundliche Bundlepakete, mit denen problemlos die richtigen Abhängigkeiten auf verschiedenen Plattformen genutzt werden können. Im `Microsoft.Data.Sqlite`-Hauptpaket ist `SQLitePCLRaw.bundle_e_sqlite3` standardmäßig enthalten. Installieren Sie das `Microsoft.Data.Sqlite.Core`-Paket und das gewünschte Bundlepaket, wenn Sie ein anderes Bundle verwenden möchten. Bundles werden automatisch von `Microsoft.Data.Sqlite` initialisiert.

| Paket | Beschreibung |
|--|--|
| [SQLitePCLRaw.bundle_e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | Dieses Bundle stellt eine konsistente Version von SQLite auf allen Plattformen bereit. Es umfasst die FTS4-, FTS5-, JSON1 und R*Tree-Erweiterungen. Dies ist die Standardeinstellung. |
| [SQLitePCLRaw.bundle_e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | Hiermit wird ein inoffizieller Open-Source-Build von `SQLCipher` bereitgestellt. |
| [SQLitePCLRaw.bundle_green](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | Dies ist mit `bundle_e_sqlite3` identisch, mit der Ausnahme, dass unter iOS die SQLite-Systembibliothek verwendet wird. |
| [SQLitePCLRaw.bundle_winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | Hier wird mit `winsqlite3.dll` die SQLite-Systembibliothek unter Windows 10 verwendet. |
| [SQLitePCLRaw.bundle_zetetic](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | Hier werden die offiziellen `SQLCipher`-Builds von Zetetic (nicht enthalten) verwendet. |

Nutzen Sie für die Verwendung des inoffiziellen Open-Source-Builds von `SQLCipher` die folgenden Befehle.

### <a name="net-core-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a>Verfügbare SQLitePCLRaw-Anbieter

Wenn Sie nicht auf ein Bundle angewiesen sind, können Sie die verfügbaren Anbieter von SQLite mit der Kernassembly verwenden.

| Anbieter | Beschreibung |
|--|--|
| [SQLitePCLRaw.provider.dynamic](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | Der `dynamic`-Anbieter lädt die native Bibliothek, anstatt <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>-Attribute zu verwenden. Weitere Informationen zur Verwendung dieses Anbieters finden Sie unter [Verwenden des dynamischen Anbieters](#use-the-dynamic-provider). |
| [SQLitePCLRaw.provider.e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | `e_sqlite3` ist der Standardanbieter. |
| [SQLitePCLRaw.provider.e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | Der `e_sqlcipher`-Anbieter bietet das inoffizielle und nicht unterstützte `SQLCipher`. |
| [SQLitePCLRaw.provider.sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | Der `sqlite3`-Anbieter bietet ein vom System bereitgestelltes `SQLite` für iOS, macOS und Linux. |
| [SQLitePCLRaw.provider.sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | Der `sqlcipher`-Anbieter ist für offizielle `SQLCipher`-Builds von `Zetetic` bestimmt. |
| [SQLitePCLRaw.provider.winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | Der `winsqlite3`-Anbieter ist für Windows 10-Umgebungen bestimmt. |

Verwenden Sie die folgenden Befehle für den `sqlite3`-Anbieter:

### <a name="net-core-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

Nachdem die Pakete installiert sind, legen Sie den Anbieter auf die `sqlite3`-Instanz fest.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a>Verwenden des dynamischen Anbieters

Sie können Ihren eigenen Build von SQLite verwenden, indem Sie das `SQLitePCLRaw.provider.dynamic_cdecl`-Paket nutzen. In diesem Fall sind Sie für die Bereitstellung der nativen Bibliothek mit Ihrer App verantwortlich. Beachten Sie, dass die Details für die Bereitstellung nativer Bibliotheken mit Ihrer App in Abhängigkeit von der verwendeten .NET-Plattform und Runtime erheblich variieren können.

Zuerst muss `IGetFunctionPointer` implementiert werden. Die Implementierung in .NET Core erfolgt so:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Konfigurieren Sie als Nächstes den `SQLitePCLRaw`-Anbieter. Stellen Sie sicher, dass Sie diesen Schritt abgeschlossen haben, bevor `Microsoft.Data.Sqlite` in Ihrer App verwendet wird. Vermeiden Sie außerdem die Verwendung eines `SQLitePCLRaw`-Bundlepakets, das Ihren Anbieter möglicherweise überschreibt.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
