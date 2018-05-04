---
title: Erstellen einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: a374c7c6e7dfc04cd8828208d6762f8d8665072e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-a-datatable"></a>Erstellen einer "DataTable"
Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.  
  
 Sie erstellen eine **DataTable** Objekt mit der entsprechenden **DataTable** Konstruktor. Können Sie ihn zum Hinzufügen der **DataSet** mithilfe der **hinzufügen** Methode zum Hinzufügen der **DataTable** des Objekts **Tabellen** Auflistung.  
  
 Sie können auch erstellen **DataTable** Objekte innerhalb einer **DataSet** mithilfe der **ausfüllen** oder **FillSchema** Methoden der der  **"DataAdapter"** -Objekt, oder aus einem vordefinierten oder abgeleiteten XML-Schema mithilfe der **ReadXml**, **ReadXmlSchema**, oder **InferXmlSchema** Methoden der **DataSet**. Beachten Sie, dass nach dem Hinzufügen einer **DataTable** als Mitglied der **Tabellen** Auflistung von einem **DataSet**, können Sie es auf die Auflistung von Tabellen von jeder anderen Hinzufügen**DataSet**.  
  
 Beim ersten Erstellen einer **DataTable**, er verfügt nicht über ein Schema (d. h. eine Struktur). Um das Schema der Tabelle zu definieren, müssen Sie erstellen und hinzufügen <xref:System.Data.DataColumn> -Objekte und die **Spalten** -Auflistung der Tabelle. Sie können auch eine Primärschlüsselspalte für die Tabelle definieren, und erstellen, und fügen **Einschränkung** -Objekte und die **Einschränkungen** -Auflistung der Tabelle. Nachdem Sie das Schema für definiert haben eine **DataTable**, Sie können Zeilen mit Daten zur Tabelle hinzufügen, durch Hinzufügen von **DataRow** -Objekte und die **Zeilen** -Auflistung der Tabelle.  
  
 Sie müssen nicht zur Bereitstellung eines Werts für die <xref:System.Data.DataTable.TableName%2A> Eigenschaft bei der Erstellung einer **DataTable**; Geben Sie die Eigenschaft zu einem späteren Zeitpunkt, oder Sie können leer bleiben. Allerdings wird beim Hinzufügen einer Tabelle ohne eine **TableName** -Wert an eine **DataSet**, in der Tabelle erhält einen Standardnamen der Tabelle*N*, beginnend mit "Table" für Table0.  
  
> [!NOTE]
>  Sollten Sie vermeiden die "Tabelle*N*" Benennungskonvention, wenn Sie angeben, eine **TableName** Wert, der Namen, die Sie angeben, ein Konflikt mit einem bereits vorhandenen Standardtabellennamen in kann die **DataSet** . Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Das folgende Beispiel erstellt eine Instanz von einem **DataTable** Objekt, und weist ihm den Namen "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 Das folgende Beispiel erstellt eine Instanz von einem **DataTable** durch Hinzufügen zu der **Tabellen** Auflistung von einer **DataSet**.  
  
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
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
