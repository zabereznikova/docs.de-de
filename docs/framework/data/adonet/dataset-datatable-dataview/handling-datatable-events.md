---
title: Behandeln von DataTable-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62f404a5-13ea-4b93-a29f-55b74a16c9d3
ms.openlocfilehash: c00e5e42508160a210d16f058c46afbf62ae0ee0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164726"
---
# <a name="handling-datatable-events"></a>Behandeln von DataTable-Ereignissen

Das <xref:System.Data.DataTable>-Objekt stellt eine Reihe von Ereignissen bereit, die von einer Anwendung verarbeitet werden können. Eine Beschreibung dieser `DataTable`-Ereignisse finden Sie in der folgenden Tabelle:  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Data.DataTable.Initialized>|Tritt ein, nachdem die <xref:System.Data.DataTable.EndInit%2A>-Methode einer `DataTable` aufgerufen wurde. Dieses Ereignis ist hauptsächlich zur Unterstützung von Szenarien zur Entwurfszeit gedacht.|  
|<xref:System.Data.DataTable.ColumnChanged>|Tritt ein, nachdem ein Wert in einer <xref:System.Data.DataColumn> erfolgreich geändert wurde.|  
|<xref:System.Data.DataTable.ColumnChanging>|Tritt ein, wenn ein Wert für eine `DataColumn` übermittelt wurde.|  
|<xref:System.Data.DataTable.RowChanged>|Tritt ein, nachdem ein `DataColumn`-Wert oder der <xref:System.Data.DataRow.RowState%2A> einer <xref:System.Data.DataRow> in der `DataTable` erfolgreich geändert wurde.|  
|<xref:System.Data.DataTable.RowChanging>|Tritt ein, wenn eine Änderung für einen `DataColumn`-Wert oder für den `RowState` einer `DataRow` in der `DataTable` übermittelt wurde.|  
|<xref:System.Data.DataTable.RowDeleted>|Tritt ein, nachdem eine `DataRow` in der `DataTable` als `Deleted` gekennzeichnet wurde.|  
|<xref:System.Data.DataTable.RowDeleting>|Tritt ein, bevor eine `DataRow` in der `DataTable` als `Deleted` gekennzeichnet wird.|  
|<xref:System.Data.DataTable.TableCleared>|Tritt ein, nachdem ein Aufruf der <xref:System.Data.DataTable.Clear%2A>-Methode der `DataTable` jede `DataRow` erfolgreich gelöscht hat.|  
|<xref:System.Data.DataTable.TableClearing>|Tritt ein, nachdem die `Clear`-Methode aufgerufen wurde, aber bevor der `Clear`-Vorgang beginnt.|  
|<xref:System.Data.DataTable.TableNewRow>|Tritt ein, nachdem durch einen Aufruf der `DataRow`-Methode der `NewRow` eine neue `DataTable` erstellt wurde.|  
|<xref:System.ComponentModel.MarshalByValueComponent.Disposed>|Tritt ein, wenn die `DataTable` in den `Disposed`-Status versetzt wurde. Wird von <xref:System.ComponentModel.MarshalByValueComponent> geerbt.|  
  
> [!NOTE]
> Die meisten Operationen, die Zeilen hinzufügen oder löschen, führen nicht zum Auslösen der Ereignisse `ColumnChanged` und `ColumnChanging`. Die `ReadXml`-Methode löst jedoch weiterhin das `ColumnChanged`-Ereignis und das `ColumnChanging`-Ereignis aus, bis `XmlReadMode` auf `DiffGram` oder auf `Auto` festgelegt ist, wenn das gelesene XML-Dokument ein `DiffGram` ist.  
  
> [!WARNING]
> Wenn Daten in einem `DataSet` geändert werden, über das das `RowChanged`-Ereignis ausgelöst wird, können Daten beschädigt werden. Bei einer solchen Datenbeschädigung wird keine Ausnahme ausgelöst.  
  
## <a name="additional-related-events"></a>Weitere verwandte Ereignisse  

 Die <xref:System.Data.DataTable.Constraints%2A>-Eigenschaft enthält eine <xref:System.Data.ConstraintCollection>-Instanz. Die <xref:System.Data.ConstraintCollection>-Klasse macht ein <xref:System.Data.ConstraintCollection.CollectionChanged>-Ereignis verfügbar. Dieses Ereignis wird ausgelöst, wenn eine Einschränkung hinzugefügt, geändert oder aus der `ConstraintCollection` entfernt wird.  
  
 Die <xref:System.Data.DataTable.Columns%2A>-Eigenschaft enthält eine <xref:System.Data.DataColumnCollection>-Instanz. Die `DataColumnCollection`-Klasse macht ein <xref:System.Data.DataColumnCollection.CollectionChanged>-Ereignis verfügbar. Dieses Ereignis wird ausgelöst, wenn eine `DataColumn` hinzugefügt, geändert oder aus der `DataColumnCollection` entfernt wird. Zu den Änderungen, die das Ereignis auslösen, gehören Änderungen des Namens, des Typs, des Ausdrucks oder der Ordinalposition einer Spalte.  
  
 Die <xref:System.Data.DataSet.Tables%2A>-Eigenschaft eines <xref:System.Data.DataSet> enthält eine <xref:System.Data.DataTableCollection>-Instanz. Die `DataTableCollection`-Klasse macht sowohl ein `CollectionChanged`-Ereignis als auch ein `CollectionChanging`-Ereignis verfügbar. Diese Ereignisse werden ausgelöst, wenn eine `DataTable` hinzugefügt oder aus dem `DataSet` entfernt wird.  
  
 Änderungen an `DataRows` können auch Ereignisse für eine verknüpfte <xref:System.Data.DataView> auslösen. Die `DataView`-Klasse macht ein <xref:System.Data.DataView.ListChanged>-Ereignis verfügbar, das ausgelöst wird, wenn sich ein `DataColumn`-Wert ändert oder wenn sich die Zusammensetzung oder Sortierreihenfolge der Ansicht ändert. Die <xref:System.Data.DataRowView>-Klasse macht ein <xref:System.Data.DataRowView.PropertyChanged>-Ereignis verfügbar, das ausgelöst wird, wenn sich ein verknüpfter `DataColumn`-Wert ändert.  
  
## <a name="sequence-of-operations"></a>Abfolge der Vorgänge  

 Beim Hinzufügen, Ändern oder Löschen einer `DataRow` laufen die Vorgänge in der folgenden Reihenfolge ab:  
  
1. Der vorgeschlagene Datensatz wird erstellt, und alle Änderungen werden übernommen.  
  
2. Die Einschränkungen für Nicht-Ausdruck-Spalten werden überprüft.  
  
3. Das `RowChanging`-Ereignis oder das `RowDeleting`-Ereignis wird ausgelöst.  
  
4. Der vorgeschlagene Datensatz wird als aktueller Datensatz festgelegt.  
  
5. Alle zugeordneten Indizes werden aktualisiert.  
  
6. Die `ListChanged`-Ereignisse für zugeordnete `DataView`-Objekte und die `PropertyChanged`-Ereignisse für zugeordnete `DataRowView`-Objekte werden ausgelöst.  
  
7. Alle Ausdrucksspalten werden ausgewertet, wobei aber die Überprüfung der Einschränkungen für diese Spalten verzögert wird.  
  
8. Die `ListChanged`-Ereignisse für die zugeordneten `DataView`-Objekte und die `PropertyChanged`-Ereignisse für die zugeordneten `DataRowView`-Objekte, auf die sich die Auswertung der Ausdrucksspalten auswirkt, werden ausgelöst.  
  
9. Das `RowChanged`-Ereignis oder das `RowDeleted`-Ereignis wird ausgelöst.  
  
10. Die Einschränkungen für Ausdrucksspalten werden überprüft.  
  
> [!NOTE]
> Änderungen an Ausdrucksspalten führen nie dazu, dass `DataTable`-Ereignisse ausgelöst werden. Änderungen an Ausdrucksspalten lösen lediglich die Ereignisse `DataView` und `DataRowView` aus. Ausdrucksspalten können Abhängigkeiten von mehreren anderen Spalten besitzen und während eines einzelnen `DataRow`-Vorgangs mehrmals ausgewertet werden. Jede Ausdrucksauswertung löst Ereignisse aus, und ein einzelner `DataRow`-Vorgang kann mehrere `ListChanged`- und `PropertyChanged`-Ereignisse auslösen, sofern Ausdrucksspalten betroffen sind. Dabei ist es auch möglich, dass für ein und dieselbe Ausdrucksspalte mehrere Ereignisse ausgelöst werden.  
  
> [!WARNING]
> Lösen Sie keine <xref:System.NullReferenceException> im `RowChanged`-Ereignishandler aus. Wenn eine <xref:System.NullReferenceException> im `RowChanged`-Ereignis einer `DataTable` ausgelöst wird, führt dies zur Beschädigung der `DataTable`.  
  
### <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt, wie Ereignishandler für die Ereignisse `RowChanged`, `RowChanging`, `RowDeleted`, `RowDeleting`, `ColumnChanged`, `ColumnChanging`, `TableNewRow`, `TableCleared` und `TableClearing` erstellt werden können. Jeder Ereignishandler zeigt die Ausgabe beim Auslösen der Ereignisse im Konsolenfenster an.  
  
 [!code-csharp[DataWorks DataTable.Events#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.Events/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.Events#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.Events/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Bearbeiten von Daten in einer "DataTable"](manipulating-data-in-a-datatable.md)
- [Behandeln von DataAdapter-Ereignissen](../handling-dataadapter-events.md)
- [Behandeln von DataSet-Ereignissen](handling-dataset-events.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
