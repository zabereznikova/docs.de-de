---
title: Benutzerdefinierte SQLite-Versionen
ms.date: 12/13/2019
description: Hier erfahren Sie, wie Sie eine benutzerdefinierte Version der nativen SQLite-Bibliothek verwenden.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746990"
---
# <a name="custom-sqlite-versions"></a>Benutzerdefinierte SQLite-Versionen

Microsoft.Data.Sqlite basiert auf SQLitePCLRaw. Sie können benutzerdefinierte Versionen der nativen SQLite-Bibliothek verwenden, indem Sie ein Bundle verwenden oder einen SQLitePCLRaw-Anbieter konfigurieren.

## <a name="bundles"></a>Bundles

SQLitePCLRaw bietet Bundlepakete, mit denen die richtigen Abhängigkeiten auf verschiedenen Plattformen problemlos genutzt werden können.

Das Microsoft.Data.Sqlite-Hauptpaket fügt „SQLitePCLRaw.bundle_e_sqlite3“ standardmäßig hinzu.

Installieren Sie das `Microsoft.Data.Sqlite.Core`-Paket und das gewünschte Bundlepaket, wenn Sie ein anderes Bundle verwenden möchten. Bundles werden automatisch von Microsoft.Data.Sqlite initialisiert.

| Paket | Beschreibung |
| --- | --- |
| SQLitePCLRaw.bundle_e_sqlite3 | Dieses Bundle stellt eine konsistente Version von SQLite auf allen Plattformen bereit. Es umfasst die FTS4-, FTS5-, JSON1 und R*Tree-Erweiterungen. Dies ist die Standardeinstellung. |
| SQLitePCLRaw.bundle_green | Dies ist mit bundle_e_sqlite3 identisch, mit der Ausnahme, dass unter iOS die SQLite-Systembibliothek verwendet wird. |
| SQLitePCLRaw.bundle_zetetic | Hier werden die offiziellen SQLCipher-Builds von Zetetic (nicht enthalten) verwendet. |
| SQLitePCLRaw.bundle_winsqlite3 | Hier wird mit winsqlite3.dll die SQLite-Systembibliothek unter Windows 10 verwendet. |
| SQLitePCLRaw.bundle_e_sqlcipher | Hiermit wird ein inoffizieller Open-Source-Build von SQLCipher bereitgestellt. |

Nutzen Sie für die Verwendung des inoffiziellen Open-Source-Builds von SQLCipher die folgenden Befehle.

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

## <a name="sqlitepclraw-providers"></a>SQLitePCLRaw-Anbieter

Sie können Ihren eigenen Build von SQLite verwenden, indem Sie das `SQLitePCLRaw.provider.dynamic_cdecl`-Paket nutzen. In diesem Fall sind Sie für die Bereitstellung der nativen Bibliothek mit Ihrer App verantwortlich. Beachten Sie, dass die Details für die Bereitstellung nativer Bibliotheken mit Ihrer App in Abhängigkeit von der verwendeten .NET-Plattform und Runtime erheblich variieren können.

Zuerst muss IGetFunctionPointer implementiert werden. Die Implementierung ist in .NET Core trivial.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Danach konfigurieren Sie den SQLitePCLRaw-Anbieter. Stellen Sie sicher, dass Sie diesen Schritt abgeschlossen haben, bevor Microsoft.Data.Sqlite in Ihrer App verwendet wird. Vermeiden Sie außerdem die Verwendung eines SQLitePCLRaw-Bundlepakets, das Ihren Anbieter möglicherweise überschreibt.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
