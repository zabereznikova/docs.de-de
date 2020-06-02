---
title: 'Vorgehensweise: Aktualisieren von Zeilen in der Datenbank'
description: Erfahren Sie, wie Sie Zeilen in einer Datenbank aktualisieren, indem Sie LINQ to SQL Objekte in einer Tabellen bezogenen Sammlung ändern. LINQ to SQL übersetzt Ergänzungen in SQL Update-Befehle.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: f25efb91fb5a83fb1c7c109bd018c8210edaec8b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286338"
---
# <a name="how-to-update-rows-in-the-database"></a>Vorgehensweise: Aktualisieren von Zeilen in der Datenbank

Sie können Zeilen in einer Datenbank aktualisieren, indem Sie die Element Werte der der Auflistung zugeordneten Objekte ändern [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> und dann die Änderungen an die Datenbank übermitteln. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]übersetzt die Änderungen in die entsprechenden SQL- `UPDATE` Befehle.

> [!NOTE]
> Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).
>
> Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.

In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet. Weitere Informationen finden Sie unter Gewusst [wie: Herstellen einer Verbindung mit einer Datenbank](how-to-connect-to-a-database.md).

### <a name="to-update-a-row-in-the-database"></a>So aktualisieren Sie eine Zeile in der Datenbank

1. Rufen Sie die zu aktualisierende Zeile aus der Datenbank ab.

2. Nehmen Sie die gewünschten Änderungen an Memberwerten im resultierenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objekt vor.

3. Übergeben Sie die Änderungen an die Datenbank.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Bestellung Nr. 11000 aus der Datenbank abgerufen. Anschließend werden die Werte für `ShipName` und `ShipVia` im resultierenden `Order`-Objekt geändert. Schließlich werden die Änderungen an diesen Memberwerten als Änderungen in der `ShipName`-Spalte und der `ShipVia`-Spalte an die Datenbank übergeben.

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwalten von Änderungskonflikten](how-to-manage-change-conflicts.md)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
