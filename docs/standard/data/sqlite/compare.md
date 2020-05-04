---
title: Vergleich mit „System.Data.SQLite“
ms.date: 12/13/2019
description: Hier werden einige der Unterschiede zwischen den Bibliotheken „Microsoft.Data.Sqlite“ und „System.Data.SQLite“ beschrieben.
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900712"
---
# <a name="comparison-to-systemdatasqlite"></a>Vergleich mit „System.Data.SQLite“

Im Jahr 2005 erstellte Robert Simpson „System.Data.SQLite“, einen SQLite-Anbieter für ADO.NET 2.0. Im Jahr 2010 übernahm das SQLite-Team die Wartung und Verwaltung des Projekts. Beachten Sie auch, dass das Mono-Team den Code im Jahr 2007 als „Mono.Data.Sqlite“ geforkt hat. „System.Data.SQLite“ blickt auf eine lange Geschichte zurück und hat sich zu einem stabilen ADO.NET-Anbieter mit vollem Funktionsumfang entwickelt, der durch Visual Studio-Tools abgerundet wird. Neue Releases liefern weiterhin Assemblys, die mit jeder Version von .NET Framework bis zurück zu Version 2.0 und sogar mit .NET Compact Framework 3.5 kompatibel sind.

Die erste Version von .NET Core (2016 veröffentlicht) war eine einzelne, einfache, moderne und plattformübergreifende Implementierung von .NET. Veraltete APIs und APIs mit moderneren Alternativen wurden absichtlich entfernt. ADO.NET enthielt keine der DataSet-APIs (einschließlich DataTable und DataAdapter).

Das Entity Framework-Team war mit der System.Data.SQLite-Codebasis einigermaßen vertraut. Brice Lambson, ein Mitglied des EF-Teams, hatte dem SQLite-Team zuvor dabei geholfen, Unterstützung für die Entity Framework-Versionen 5 und 6 hinzuzufügen. Brice experimentierte auch zur gleichen Zeit, zu der .NET Core geplant wurde, mit seiner eigenen Implementierung eines SQLite-ADO.NET-Anbieters. Nach einer langen Diskussion entschied sich das Entity Framework-Team dazu, basierend auf dem Prototyp von Brice „Microsoft.Data.Sqlite“ zu erstellen. Dadurch konnten sie eine neue einfache und moderne Implementierung erstellen, die auf die Ziele von .NET Core abgestimmt ist.

Als Beispiel dafür, was wir mit „moderner“ meinen, finden Sie nachstehend Code zum Erstellen einer [benutzerdefinierten Funktion](user-defined-functions.md) in „System.Data.SQLite“ und „Microsoft.Data.Sqlite“.

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

Im Jahr 2017 wurde die .NET Core 2.0-Strategie geändert. Es wurde entschieden, dass die Kompatibilität mit .NET Framework entscheidend für den Erfolg von .NET Core ist. Viele der entfernten APIs, einschließlich der DataSet-APIs, wurden wieder hinzugefügt. Dadurch wurde die Blockierung von „System.Data.SQLite“ (wie von vielen anderen auch) aufgehoben, sodass diese ebenfalls zu .NET Core portiert werden konnte. Das ursprüngliche Ziel von „Microsoft.Data.Sqlite“, einfach und modern zu sein, bleibt jedoch weiterhin bestehen. Weiter Informationen zu ADO.NET-APIs, die nicht von „Microsoft.Data.Sqlite“ implementiert wurden, finden Sie unter [ADO.NET-Einschränkungen](adonet-limitations.md).

Wenn neue Funktionen zu „Microsoft.Data.Sqlite“ hinzugefügt werden, wird das Design von „System.Data.SQLite“ berücksichtigt. Wir versuchen, die Änderungen zwischen den beiden so gering wie möglich zu halten, um den Übergang zwischen ihnen zu erleichtern.

## <a name="data-types"></a>Datentypen

Der größte Unterschied zwischen „Microsoft.Data.Sqlite“ und „System.Data.SQLite“ besteht in der Verarbeitung von Datentypen. Wie unter [Datentypen](types.md) beschrieben, versucht „Microsoft.Data.Sqlite“ nicht, die zugrunde liegende Eigenwilligkeit von SQLite zu verbergen, wodurch jede beliebige Zeichenfolge als Spaltentyp angegeben werden kann, und verfügt über nur vier primitive Typen: INTEGER, REAL, TEXT und BLOB.

„System.Data.SQLite“ wendet zusätzliche Semantiken auf Spaltentypen an, indem diese direkt .NET-Typen zugeordnet werden. Dadurch erhält der Anbieter ein stärker typisiertes Erscheinungsbild, weist aber einige Ecken und Kanten auf. Sie mussten beispielsweise eine neue SQL-Anweisung (TYPES) einführen, um die Spaltentypen von Ausdrücken in SELECT-Anweisungen anzugeben.

## <a name="connection-strings"></a>Verbindungszeichenfolgen

„Microsoft.Data.Sqlite“ verfügt über deutlich weniger Schlüsselwörter für [Verbindungszeichenfolgen](connection-strings.md). In der folgenden Tabelle werden Alternativen angezeigt, die stattdessen verwendet werden können.

| Stichwort          | Alternative                                         |
| ---------------- | --------------------------------------------------- |
| Cachegröße       | Senden von `PRAGMA cache_size = <pages>`                  |
| Standardzeitlimit  | Verwenden der DefaultTimeout-Eigenschaft für SqliteConnection |
| FailIfMissing    | Verwenden Sie `Mode=ReadWrite`                                |
| FullUri          | Verwenden des Schlüsselworts für die Datenquelle                         |
| Journal Mode     | Senden von `PRAGMA journal_mode = <mode>`                 |
| Legacy Format    | Senden von `PRAGMA legacy_file_format = 1`                |
| Max Page Count   | Senden von `PRAGMA max_page_count = <pages>`              |
| Page Size        | Senden von `PRAGMA page_size = <bytes>`                   |
| Nur Leseberechtigung        | Verwenden Sie `Mode=ReadOnly`                                 |
| Synchron      | Senden von `PRAGMA synchronous = <mode>`                  |
| URI              | Verwenden des Schlüsselworts für die Datenquelle                         |
| UseUTF16Encoding | Senden von `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Autorisierung

„Microsoft.Data.Sqlite“ verfügt über keine API, die den Autorisierungsrückruf von SQLite verfügbar macht. Verwenden Sie das Problem [#13835](https://github.com/dotnet/efcore/issues/13835), um Feedback zu diesem Feature zu geben.

## <a name="data-change-notifications"></a>Benachrichtigung über Datenänderungen

„Microsoft.Data.Sqlite“ verfügt über keine API, die Benachrichtigungen über Datenänderungen verfügbar macht. Verwenden Sie das Problem [#13827](https://github.com/dotnet/efcore/issues/13827), um Feedback zu diesem Feature zu geben.

## <a name="virtual-table-modules"></a>Module für virtuelle Tabellen

„Microsoft.Data.Sqlite“ verfügt über keine API zum Erstellen von Modulen für virtuelle Tabellen. Verwenden Sie das Problem [#13823](https://github.com/dotnet/efcore/issues/13823), um Feedback zu diesem Feature zu geben.

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
* [Verbindungszeichenfolgen](connection-strings.md)
* [Verschlüsselung](encryption.md)
* [ADO.NET-Einschränkungen](adonet-limitations.md)
* [Dapper-Einschränkungen](dapper-limitations.md)
