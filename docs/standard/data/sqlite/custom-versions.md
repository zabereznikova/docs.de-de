---
title: Benutzerdefinierte SQLite-Versionen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie eine benutzerdefinierte Version der systemeigenen SQLite-Bibliothek verwenden.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746990"
---
# <a name="custom-sqlite-versions"></a>Benutzerdefinierte SQLite-Versionen

Microsoft. Data. sqlite baut auf sqlitepclraw auf. Sie können benutzerdefinierte Versionen der systemeigenen SQLite-Bibliothek verwenden, indem Sie ein Bündel verwenden oder einen sqlitepclraw-Anbieter konfigurieren.

## <a name="bundles"></a>Ven

Sqlitepclraw stellt Bündel Pakete bereit, mit denen die richtigen Abhängigkeiten auf verschiedenen Plattformen problemlos untergebracht werden können.

Das Microsoft. Data. sqlite-Hauptpaket führt standardmäßig sqlitepclraw. bundle_e_sqlite3 ein.

Wenn Sie ein anderes Paket verwenden möchten, installieren Sie das `Microsoft.Data.Sqlite.Core` Paket und das Paket Paket, das Sie verwenden möchten. Pakete werden automatisch von "Microsoft. Data. sqlite" initialisiert.

| Paket | BESCHREIBUNG |
| --- | --- |
| Sqlitepclraw. bundle_e_sqlite3 | Stellt eine konsistente Version von SQLite auf allen Plattformen bereit. Schließt die Struktur Erweiterungen FTS4, FTS5, JSON1 und R * ein. Dies ist die Standardoption. |
| Sqlitepclraw. bundle_green | Identisch mit bundle_e_sqlite3, mit Ausnahme von IOS, wo die System SQLite-Bibliothek verwendet wird. |
| Sqlitepclraw. bundle_zetetic | Verwendet die offiziellen sqlcipher-Builds aus Zetetic (nicht eingeschlossen). |
| Sqlitepclraw. bundle_winsqlite3 | Verwendet winsqlite3. dll, die System SQLite-Bibliothek unter Windows 10. |
| Sqlitepclraw. bundle_e_sqlcipher | Stellt einen inoffiziellen Open Source-Build von sqlcipher bereit. |

Um beispielsweise den inoffiziellen Open Source-Build von sqlcipher zu verwenden, verwenden Sie die folgenden Befehle.

### <a name="net-core-clitabnetcore-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>Sqlitepclraw-Anbieter

Sie können Ihren eigenen Build von SQLite verwenden, indem Sie das `SQLitePCLRaw.provider.dynamic_cdecl`-Paket nutzen. In diesem Fall sind Sie für die Bereitstellung der nativen Bibliothek mit Ihrer APP verantwortlich. Beachten Sie, dass die Details der Bereitstellung von systemeigenen Bibliotheken in Ihrer APP erheblich variieren, je nachdem, welche .NET-Plattform und-Laufzeit Sie verwenden.

Zuerst muss igetfunctionpointer implementiert werden. Die Implementierung ist in .net Core Recht trivial.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Konfigurieren Sie als nächstes den sqlitepclraw-Anbieter. Stellen Sie sicher, dass dies geschieht, bevor Microsoft. Data. sqlite in Ihrer APP verwendet wird. Vermeiden Sie außerdem die Verwendung eines Pakets vom sqlitepclraw-Bundle, das Ihren Anbieter außer Kraft setzen kann.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
