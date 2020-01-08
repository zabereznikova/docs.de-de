---
title: Vergleich mit System. Data. sqlite
ms.date: 12/13/2019
description: Beschreibt einige der Unterschiede zwischen den Bibliotheken Microsoft. Data. sqlite und System. Data. sqlite.
ms.openlocfilehash: dee90c132b108f2c876c0d8becc1b02035a47b61
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450279"
---
# <a name="comparison-to-systemdatasqlite"></a>Vergleich mit System. Data. sqlite

In 2005 erstellte Robert Simpson System. Data. sqlite, einen SQLite-Anbieter für ADO.NET 2,0. In 2010 hat das SQLite-Team die Wartung und Entwicklung des Projekts übernommen. Beachten Sie auch, dass das Mono-Team den Code in 2007 als Mono. Data. sqlite verzweigt hat. "System. Data. sqlite" hat einen langen Verlauf und hat sich zu einem stabilen und voll funktionsfähigen ADO.NET-Anbieter mit Visual Studio-Tools entwickelt. Neue Releases liefern weiterhin Assemblys, die mit jeder Version von .NET Framework zurück zu Version 2,0 und sogar .NET Compact Framework 3,5 kompatibel sind.

Die erste Version von .net Core (veröffentlicht in 2016) war eine einfache, einfache, moderne und plattformübergreifende Implementierung von .net. Veraltete APIs und APIs mit moderneren Alternativen wurden absichtlich entfernt. ADO.net enthielt keine der DataSet-APIs (einschließlich databel und DataAdapter).

Das Entity Framework Team war mit der System. Data. sqlite-CodeBase etwas vertraut. Brice Lambson, ein Mitglied des EF-Teams, hatte das SQLite-Team zuvor beim Hinzufügen von Unterstützung für die Entity Framework-Versionen 5 und 6 unterstützt. Brice hat auch mit seiner eigenen Implementierung eines SQLite-ADO.NET-Anbieters experimentieren, der ungefähr zur gleichen Zeit wie .net Core geplant wurde. Nach einer langen Diskussion entschied sich das Entity Framework Team, Microsoft. Data. sqlite basierend auf dem Prototyp der Brice zu erstellen. Dies ermöglicht es Ihnen, eine neue, leichte und moderne Implementierung zu erstellen, die an den Zielen von .net Core ausgerichtet ist.

Im folgenden finden Sie ein Beispiel für eine modernere Bedeutung von Code zum Erstellen einer [benutzerdefinierten Funktion](user-defined-functions.md) in "System. Data. sqlite" und "Microsoft. Data. sqlite".

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

In 2017 hat .net Core 2,0 eine Änderung der Strategie erlebt. Es wurde entschieden, dass die Kompatibilität mit .NET Framework für den Erfolg von .net Core entscheidend war. Viele der entfernten APIs, einschließlich der DataSet-APIs, wurden wieder hinzugefügt. Wie auch für viele andere, wurde die Blockierung von System. Data. sqlite aufgehoben, sodass Sie auch nach .net Core portiert werden konnte. Das ursprüngliche Ziel von Microsoft. Data. sqlite ist, dass es einfach und modern ist, bleibt jedoch erhalten. Weitere Informationen zu ADO.NET-APIs, die nicht von Microsoft. Data. sqlite implementiert werden, finden Sie unter [ADO.net](adonet-limitations.md) .

Wenn "Microsoft. Data. sqlite" neue Funktionen hinzugefügt werden, wird der Entwurf von "System. Data. sqlite" berücksichtigt. Wir versuchen, nach Möglichkeit die Änderungen zwischen den beiden zu minimieren, um den Übergang zwischen diesen zu vereinfachen.

## <a name="data-types"></a>Datentypen

Der größte Unterschied zwischen Microsoft. Data. sqlite und System. Data. sqlite besteht darin, wie Datentypen behandelt werden. Wie in den [Datentypen](types.md)beschrieben, versucht Microsoft. Data. sqlite nicht, den zugrunde liegenden quirkiness von SQLite auszublenden, wodurch jede beliebige Zeichenfolge als Spaltentyp angegeben werden kann und nur vier primitive Typen aufweist: Integer, Real, Text und BLOB.

System. Data. sqlite wendet zusätzliche Semantik auf Spaltentypen an, die Sie direkt zu .NET-Typen hinzu ordnen. Dadurch erhält der Anbieter ein stärker typisiertes Gefühl, aber er hat einige grobe Ränder. Sie mussten z. b. eine neue SQL-Anweisung (-Typen) einführen, um die Spaltentypen von Ausdrücken in SELECT-Anweisungen anzugeben.

## <a name="connection-strings"></a>Verbindungszeichenfolgen

"Microsoft. Data. sqlite" hat viel weniger Schlüsselwörter für [Verbindungs Zeichenfolgen](connection-strings.md) . In der folgenden Tabelle werden Alternativen angezeigt, die stattdessen verwendet werden können.

| Stichwort          | Alternative                                         |
| ---------------- | --------------------------------------------------- |
| Cachegröße       | Sende `PRAGMA cache_size = <pages>`                  |
| Standardzeitlimit  | Verwenden der defaultTimeout-Eigenschaft für sqliteconnection |
| FailIf Missing    | Verwenden Sie `Mode=ReadWrite`                                |
| FullUri          | Verwenden des Schlüssel Worts für die Datenquelle                         |
| Journal Modus     | Sende `PRAGMA journal_mode = <mode>`                 |
| Legacy Format    | Sende `PRAGMA legacy_file_format = 1`                |
| Maximale Seitenanzahl   | Sende `PRAGMA max_page_count = <pages>`              |
| Seitengröße        | Sende `PRAGMA page_size = <bytes>`                   |
| Schreibgeschützt        | Verwenden Sie `Mode=ReadOnly`                                 |
| Synchronous      | Sende `PRAGMA synchronous = <mode>`                  |
| URI              | Verwenden des Schlüssel Worts für die Datenquelle                         |
| UseUTF16Encoding | Sende `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Autorisierung

Microsoft. Data. sqlite verfügt über keine API, die den Autorisierungs Rückruf von SQLite verfügbar macht. Verwenden Sie Problem [#13835](https://github.com/aspnet/EntityFrameworkCore/issues/13835) , um Feedback zu diesem Feature bereitzustellen.

## <a name="data-change-notifications"></a>Daten Änderungs Benachrichtigungen

Microsoft. Data. sqlite verfügt über keine API, die SQLite-Daten Änderungs Benachrichtigungen verfügbar macht. Verwenden Sie Problem [#13827](https://github.com/aspnet/EntityFrameworkCore/issues/13827) , um Feedback zu diesem Feature bereitzustellen.

## <a name="virtual-table-modules"></a>Module für virtuelle Tabellen

Microsoft. Data. sqlite verfügt über keine API zum Erstellen von virtuellen Tabellen Modulen. Verwenden Sie Problem [#13823](https://github.com/aspnet/EntityFrameworkCore/issues/13823) , um Feedback zu diesem Feature bereitzustellen.

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
* [Verbindungszeichenfolgen](connection-strings.md)
* [Verschlüsselung](encryption.md)
* [ADO.net Einschränkungen](adonet-limitations.md)
* [Dappereinschränkungen](dapper-limitations.md)
