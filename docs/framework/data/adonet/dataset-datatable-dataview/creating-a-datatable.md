---
title: Erstellen einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 64ba7a8e6bd6361e14d1f16576e377575b088bbe
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205143"
---
# <a name="creating-a-datatable"></a>Erstellen einer "DataTable"
Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.  
  
 Sie können ein **Daten** Objekt mit dem entsprechenden **Daten** tabellenkonstruktor erstellen. Sie können es dem **DataSet** hinzufügen, indem Sie die **Add** -Methode verwenden, um es der Tables- **Auflistung** des **datables** -Objekts hinzuzufügen.  
  
 Sie können mithilfe der **Fill** -Methode oder der **FillSchema** -Methode des **DataAdapter** -Objekts oder aus einem vordefinierten oder abgelegten XML-Schema mithilfe von "read **XML**" und "Read XmlSchema" auch **Daten** in einem **DataSet** erstellen.oder **InferXmlSchema** -Methoden des **DataSets**. Beachten Sie, dass Sie, nachdem Sie eine Datentabelle als Member der **Tables** -Auflistung eines **DataSets**hinzugefügt haben, Sie nicht zur **Auflistung** von Tabellen eines beliebigen anderen **DataSets**hinzufügen können.  
  
 Wenn Sie erstmalig eine **Daten**Tabelle erstellen, hat Sie kein Schema (d. h. eine Struktur). Um das Schema der Tabelle zu definieren, müssen Sie-Objekte erstellen <xref:System.Data.DataColumn> und der **Columns** -Auflistung der Tabelle hinzufügen. Sie können auch eine Primärschlüssel Spalte für die Tabelle definieren und Einschränkungs Objekte erstellen und der Einschränkungs Auflistung der Tabelle hinzufügen. Nachdem Sie das Schema für eine **Daten**Tabelle definiert haben, können Sie der Tabelle Daten Zeilen hinzufügen, indem Sie der **Rows** -Auflistung der Tabelle **DataRow** -Objekte hinzufügen.  
  
 Sie müssen keinen Wert für die <xref:System.Data.DataTable.TableName%2A> -Eigenschaft angeben, wenn Sie eine **Daten**Tabelle erstellen. Sie können die Eigenschaft zu einem anderen Zeitpunkt angeben, oder Sie können Sie leer lassen. Wenn Sie jedoch eine Tabelle ohne **TableName** -Wert zu einem **DataSet**hinzufügen, erhält die Tabelle einen inkrementellen Standardnamen der Tabelle*N*, beginnend mit "Table" für Table0.  
  
> [!NOTE]
> Es wird empfohlen, dass Sie die Benennungs Konvention "Table*N*" vermeiden, wenn Sie einen **TableName** -Wert angeben, da der von Ihnen bereitgestellte Name möglicherweise mit einem vorhandenen Standard Tabellennamen im **DataSet**in Konflikt steht. Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel wird eine Instanz eines **Daten** Tabelle-Objekts erstellt und dem Namen "Customers" zugewiesen.  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 Im folgenden Beispiel wird eine Instanz einer Datentabelle erstellt, indem Sie der **Tables** - **Auflistung** eines **DataSets**hinzugefügt wird.  
  
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
- [DataTables](datatables.md)
- [Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)](../populating-a-dataset-from-a-dataadapter.md)
- [Laden eines DataSet aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
