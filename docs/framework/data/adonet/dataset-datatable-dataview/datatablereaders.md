---
title: "\"DataTableReaders\""
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 9984dc9c215a34ab35524560e4dcbcd6bd12596d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602844"
---
# <a name="datatablereaders"></a>"DataTableReaders"
Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.  
  
 Bei der Erstellung einer **DataTableReader** aus einer **DataTable**, die resultierende **DataTableReader** Objekt enthält die gleichen Daten wie ein Resultset der  **DataTable** aus dem er, mit Ausnahme von Zeilen erstellt wurde, die als gelöscht markiert wurden. Die Spalten angezeigt werden, in der gleichen Reihenfolge wie in der ursprünglichen **DataTable**.  
  
 Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch den Aufruf erstellt wurde <xref:System.Data.DataSet.CreateDataReader%2A>. Die Ergebnisse werden in der gleichen Reihenfolge wie die **DataTables** in die **DataSet** des Objekts <xref:System.Data.DataSet.Tables%2A> Auflistung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen eines DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Erläutert das Erstellen einer **DataTableReader** Objekt.  
  
 [Navigieren in DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Beschreibt die Verwendung von der **lesen** -Methode durch den Inhalt des Verschieben einer **DataTableReader**.  
  
## <a name="see-also"></a>Siehe auch
- [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
