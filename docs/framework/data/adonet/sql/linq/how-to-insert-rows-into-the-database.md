---
title: 'Vorgehensweise: Einfügen von Zeilen in die Datenbank'
description: Erfahren Sie, wie Sie Zeilen in eine Datenbank einfügen, indem Sie LINQ to SQL Objekte zu einer Tabellen bezogenen Auflistung hinzufügen. LINQ to SQL übersetzt Ergänzungen in SQL INSERT-Befehle.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 39eee6edf59d2adb7de41efd88899050fbe69fd8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286351"
---
# <a name="how-to-insert-rows-into-the-database"></a>Vorgehensweise: Einfügen von Zeilen in die Datenbank

Sie fügen Zeilen in eine Datenbank ein, indem Sie der zugeordneten Auflistung Objekte hinzufügen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> und dann die Änderungen an die Datenbank übermitteln. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]übersetzt die Änderungen in die entsprechenden SQL- `INSERT` Befehle.

> [!NOTE]
> Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).
>
> Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.

In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet. Weitere Informationen finden Sie unter Gewusst [wie: Herstellen einer Verbindung mit einer Datenbank](how-to-connect-to-a-database.md).

### <a name="to-insert-a-row-into-the-database"></a>So fügen Sie eine Zeile in die Datenbank ein

1. Erstellen Sie ein neues Objekt, das die zu übermittelnden Spaltendaten enthält.

2. Fügen Sie das neue-Objekt der-Auflistung hinzu, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` der Ziel Tabelle in der-Datenbank zugeordnet ist.

3. Übergeben Sie die Änderung an die Datenbank.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird ein neues Objekt des Typs `Order` erstellt und mit entsprechenden Werten aufgefüllt. Anschließend wird das neue Objekt der `Order`-Auflistung hinzugefügt. Schließlich wird die Änderung an der Datenbank als neue Zeile in der `Orders`-Tabelle übergeben.

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwalten von Änderungskonflikten](how-to-manage-change-conflicts.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
