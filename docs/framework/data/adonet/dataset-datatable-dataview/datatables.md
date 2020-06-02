---
title: "\"DataTables\""
description: Erfahren Sie mehr über eine ADO.net-Datentabelle, die eine Tabelle mit relationalen Daten im Arbeitsspeicher darstellt. NET-basierte Anwendung, in der es sich befindet.
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: da6c9201951a6c7916067011c0a4f01ef9fdeffd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286907"
---
# <a name="datatables"></a>"DataTables"
Ein <xref:System.Data.DataSet> besteht aus einer Auflistung von Tabellen, Beziehungen und Einschränkungen. In ADO.net <xref:System.Data.DataTable> werden-Objekte verwendet, um die Tabellen in einem **DataSet**darzustellen. Eine **Daten** Tabelle stellt eine Tabelle mit relationalen Daten im Arbeitsspeicher dar. die Daten sind in der lokal. Eine netzwerkbasierte Anwendung, in der Sie sich befindet, aber aus einer Datenquelle wie Microsoft SQL Server mit einem **DataAdapter** aufgefüllt werden kann, um weitere Informationen zu erhalten, finden Sie unter Auffüllen [eines Datasets von einem DataAdapter](../populating-a-dataset-from-a-dataadapter.md).  
  
 Die **datdatababel** -Klasse ist ein Member des **System. Data** -Namespace innerhalb der .NET Framework-Klassenbibliothek. Sie können eine **Daten** Tabelle unabhängig oder als Member eines **DataSets**erstellen und verwenden, und **Daten** Tabelle kann auch zusammen mit anderen .NET Framework Objekten verwendet werden, einschließlich der <xref:System.Data.DataView> . Sie greifen auf die Auflistung von Tabellen in einem **DataSet** über die **Tables** -Eigenschaft des **DataSet** -Objekts zu.  
  
 Das Schema oder die Struktur einer Tabelle wird durch Spalten und Einschränkungen dargestellt. Sie definieren das Schema einer **Daten** Tabelle mithilfe von <xref:System.Data.DataColumn> -Objekten sowie mit <xref:System.Data.ForeignKeyConstraint> -und- <xref:System.Data.UniqueConstraint> Objekten. Die Spalten einer Tabelle können Spalten in einer Datenquelle zugeordnet sein, berechnete Werte aus Ausdrücken enthalten, Werte automatisch erhöhen oder primäre Schlüsselwerte enthalten.  
  
 Zusätzlich zu einem Schema muss eine Datentabelle auch Zeilen enthalten, um Daten zu **Speichern** und zu sortieren. Die <xref:System.Data.DataRow>-Klasse stellt die tatsächlich in einer Tabelle enthaltenen Daten dar. Verwenden Sie die **DataRow** und die zugehörigen Eigenschaften und Methoden, um die Daten in einer Tabelle abzurufen, auszuwerten und zu bearbeiten. Wenn Sie auf die Daten innerhalb einer Zeile zugreifen und diese ändern, behält das **DataRow** -Objekt sowohl den aktuellen als auch den ursprünglichen Zustand bei.  
  
 Sie können mithilfe einer oder mehrerer zugehöriger Spalten in Tabellen diese Tabellen als über- und untergeordnete Tabellen in Beziehung zueinander setzen. Sie erstellen mithilfe eines eine Beziehung zwischen **datentierbaren** Objekten <xref:System.Data.DataRelation> . **DataRelations** -Objekte können dann verwendet werden, um die zugehörigen untergeordneten oder übergeordneten Zeilen einer bestimmten Zeile zurückzugeben. Weitere Informationen finden Sie unter [Hinzufügen von DataRelations](adding-datarelations.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen einer "DataTable"](creating-a-datatable.md)  
 Erläutert, wie eine **Daten** Tabelle erstellt und einem **DataSet**hinzugefügt wird.  
  
 [DataTable-Schemadefinition](datatable-schema-definition.md)  
 Enthält Informationen zum Erstellen und Verwenden von **datacolumschlag** -Objekten und-Einschränkungen.  
  
 [Bearbeiten von Daten in einer "DataTable"](manipulating-data-in-a-datatable.md)  
 Erläutert, wie Daten in einer Tabelle hinzugefügt, bearbeitet oder gelöscht werden. Erläutert, **wie Datentabellen Ereignisse verwendet** werden, um Änderungen an Daten in der Tabelle zu untersuchen.  
  
 [Behandeln von DataTable-Ereignissen](handling-datatable-events.md)  
 Stellt Informationen zu den Ereignissen bereit, die für die Verwendung mit einer **Daten**Tabelle verfügbar sind, einschließlich Ereignissen, wenn Spaltenwerte geändert werden und Zeilen hinzugefügt oder gelöscht werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ADO.NET](../index.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese dazu verwendet werden, auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.  
  
 ["DataSets", "DataTables" und "DataViews"](index.md)  
 Stellt Informationen zum ADO.net- **DataSet** bereit, einschließlich der Erstellung von Beziehungen zwischen Tabellen.  
  
 <xref:System.Data.Constraint>  
 Stellt Referenz **Informationen zum Einschränkungs Objekt bereit** .  
  
 <xref:System.Data.DataColumn>  
 Stellt Referenzinformationen zum **datacolenn** -Objekt bereit.  
  
 <xref:System.Data.DataSet>  
 Stellt Referenzinformationen über das **DataSet** -Objekt bereit.  
  
 <xref:System.Data.DataTable>  
 Enthält Referenzinformationen zum **datbare** -Objekt.  
  
 [Übersicht über die Klassenbibliothek](../../../../standard/class-library-overview.md)  
 Bietet eine Übersicht über die .NET Framework-Klassenbibliothek, einschließlich des **System** Namespace und des Namespace der zweiten Ebene, **System. Data**.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../ado-net-overview.md)
