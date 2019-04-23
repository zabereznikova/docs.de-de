---
title: Erstellen einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 272976d3c581d3e8a5860ba5cf3f9695ca370d8c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112384"
---
# <a name="creating-a-datatable"></a>Erstellen einer "DataTable"
Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.  
  
 Sie erstellen eine **DataTable** Objekt mit der entsprechenden **DataTable** Konstruktor. Hinzuzufügen, können Sie auf die **DataSet** mithilfe der **hinzufügen** Methode zum Hinzufügen der **DataTable** des Objekts **Tabellen** Auflistung.  
  
 Können Sie auch erstellen **DataTable** Objekte innerhalb einer **DataSet** mithilfe der **füllen** oder **FillSchema** Methoden der  **DataAdapter** -Objekt, oder aus einem vordefinierten oder abgeleiteten XML-Schema mithilfe der **ReadXml**, **ReadXmlSchema**, oder **InferXmlSchema** Methoden der **DataSet**. Beachten Sie, dass nach dem Hinzufügen von einer **DataTable** als Mitglied der **Tabellen** Auflistung von einem **DataSet**, Sie können nicht auf die Auflistung von Tabellen mit jedem anderen Hinzufügen**DataSet**.  
  
 Beim ersten Erstellen einer **DataTable**, er verfügt nicht über ein Schema (d. h. eine Struktur). Um das Schema der Tabelle zu definieren, müssen Sie erstellen und hinzufügen <xref:System.Data.DataColumn> Objekte die **Spalten** -Auflistung der Tabelle. Sie können auch eine Primärschlüsselspalte für die Tabelle definieren, und erstellen, und fügen **Einschränkung** Objekte die **Einschränkungen** -Auflistung der Tabelle. Nachdem Sie das Schema für definiert haben eine **DataTable**, Sie können Zeilen mit Daten zur Tabelle hinzufügen, durch Hinzufügen von **DataRow** Objekte die **Zeilen** -Auflistung der Tabelle.  
  
 Sie sind nicht erforderlich, geben Sie einen Wert für die <xref:System.Data.DataTable.TableName%2A> Eigenschaft bei der Erstellung einer **DataTable**; Sie können diese Eigenschaft zu einem späteren Zeitpunkt festlegen, oder Sie lassen ihn leer. Jedoch beim Hinzufügen einer Tabelle ohne einen **TableName** -Werts in einen **DataSet**, in der Tabelle erhält einen Standardnamen der Tabelle*N*, beginnend mit "Table" für Table0.  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie vermeiden, die "Tabelle*N*" Benennungskonvention, wenn Sie angeben einer **TableName** Wert, der der Namen, die Sie angeben, ein Konflikt mit einem bereits vorhandenen Standardtabellennamen im kann die **DataSet** . Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Das folgende Beispiel erstellt eine Instanz von einem **DataTable** -Objekt und weist ihr den Namen "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 Das folgende Beispiel erstellt eine Instanz von einem **DataTable** fügen es zu der **Tabellen** Auflistung von einer **DataSet**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
