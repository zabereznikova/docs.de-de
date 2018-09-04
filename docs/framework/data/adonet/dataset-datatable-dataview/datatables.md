---
title: "\"DataTables\""
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 2849d159fbfdb0c0739b76fd288a987d4ce3d02f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560144"
---
# <a name="datatables"></a>"DataTables"
Ein <xref:System.Data.DataSet> besteht aus einer Auflistung von Tabellen, Beziehungen und Einschränkungen. In ADO.NET können <xref:System.Data.DataTable> Objekte werden verwendet, um die Tabellen in repräsentiert eine **DataSet**. Ein **DataTable** stellt eine Tabelle mit relationalen Daten im Speicher; die Daten sind lokal auf dem. NET-basierten Anwendung, in dem sich befindet, sondern kann aus einer Datenquelle, z. B. die Verwendung von Microsoft SQL Server gefüllt werden, eine **DataAdapter** Weitere Informationen finden Sie unter [Auffüllen eines Datasets mit einen "DataAdapter"](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 Die **DataTable** Klasse ist ein Mitglied der **"System.Data"** -Namespace innerhalb der .NET Framework-Klassenbibliothek. Sie erstellen und verwenden Sie eine **DataTable** unabhängig oder als Mitglied eine **DataSet**, und **DataTable** können Objekte auch in Verbindung mit anderen .NET Framework-Objekte verwendet werden einschließlich der <xref:System.Data.DataView>. Sie Zugriff auf die Auflistung von Tabellen in einem **DataSet** über die **Tabellen** Eigenschaft der **DataSet** Objekt.  
  
 Das Schema oder die Struktur einer Tabelle wird durch Spalten und Einschränkungen dargestellt. Definieren Sie das Schema von einem **DataTable** mit <xref:System.Data.DataColumn> Objekte als auch <xref:System.Data.ForeignKeyConstraint> und <xref:System.Data.UniqueConstraint> Objekte. Die Spalten einer Tabelle können Spalten in einer Datenquelle zugeordnet sein, berechnete Werte aus Ausdrücken enthalten, Werte automatisch erhöhen oder primäre Schlüsselwerte enthalten.  
  
 Zusätzlich zu einem Schema eine **DataTable** benötigen auch Zeilen zum aufnehmen und Sortieren von Daten. Die <xref:System.Data.DataRow>-Klasse stellt die tatsächlich in einer Tabelle enthaltenen Daten dar. Sie verwenden die **DataRow** und dessen Eigenschaften und Methoden abzurufen, auszuwerten und zu bearbeiten Sie die Daten in einer Tabelle. Beim Zugriff auf und ändern Sie die Daten in einer Zeile, die **DataRow** -Objekt verwaltet den aktuellen und ursprünglichen Zustand.  
  
 Sie können mithilfe einer oder mehrerer zugehöriger Spalten in Tabellen diese Tabellen als über- und untergeordnete Tabellen in Beziehung zueinander setzen. Sie erstellen eine Beziehung zwischen **DataTable** -Objekte mit einer <xref:System.Data.DataRelation>. **DataRelation** Objekte können dann verwendet werden, um die zugehörigen untergeordneten oder übergeordneten Zeilen einer bestimmten Zeile zurückzugeben. Weitere Informationen finden Sie unter [Hinzufügen von "DataRelations"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Erläutert das Erstellen einer **DataTable** und Hinzufügen zu einem **DataSet**.  
  
 [DataTable-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Enthält Informationen zum Erstellen und verwenden **DataColumn** -Objekten und Einschränkungen.  
  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Erläutert, wie Daten in einer Tabelle hinzugefügt, bearbeitet oder gelöscht werden. Erläutert, wie **DataTable** Ereignisse, um Änderungen an Daten in der Tabelle zu untersuchen.  
  
 [Behandeln von DataTable-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Enthält Informationen über die verfügbaren Ereignisse zur Verwendung mit einem **DataTable**, einschließlich der Ereignisse, die beim Ändern von Spaltenwerten und Zeilen hinzugefügt oder gelöscht werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese dazu verwendet werden, auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Enthält Informationen zu ADO.NET **DataSet** einschließlich der Beziehungen zwischen Tabellen erstellen.  
  
 <xref:System.Data.Constraint>  
 Enthält Referenzinformationen zu den **Einschränkung** Objekt.  
  
 <xref:System.Data.DataColumn>  
 Enthält Referenzinformationen zu den **DataColumn** Objekt.  
  
 <xref:System.Data.DataSet>  
 Enthält Referenzinformationen zu den **DataSet** Objekt.  
  
 <xref:System.Data.DataTable>  
 Enthält Referenzinformationen zu den **DataTable** Objekt.  
  
 [Übersicht über die Klassenbibliothek](../../../../../docs/standard/class-library-overview.md)  
 Bietet eine Übersicht über die .NET Framework-Klassenbibliothek, einschließlich der **System** Namespace sowie den Namespace auf zweiter Ebene **"System.Data"**.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
