---
title: Erstellen einer "DataTable"
description: Erfahren Sie, wie Sie eine Datentabelle in ADO.NET erstellen, die eine Tabelle mit relationalen Daten im Arbeitsspeicher darstellt, die unabhängig voneinander oder von anderen .NET Framework Objekten verwendet werden können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 335137eeef02e590539c6d83e46cb39901a1e03f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286920"
---
# <a name="creating-a-datatable"></a>Erstellen einer "DataTable"
Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.  
  
 Sie können ein **Daten** Objekt mit dem entsprechenden **Daten** tabellenkonstruktor erstellen. Sie können es dem **DataSet** hinzufügen, indem Sie die **Add** -Methode verwenden, um es der Tables- **Auflistung des datables** -Objekts hinzuzufügen. **Tables**  
  
 Mithilfe der **Fill** -Methode oder der **FillSchema** -Methode des **DataAdapter** -Objekts können Sie auch **Daten** **in einem vordefinierten** oder abgelegten XML-Schema erstellen, indem Sie die Methoden "read **XML**", "read **XmlSchema**" oder " **InferXmlSchema** " des **DataSets**verwenden. Beachten Sie, dass Sie, nachdem Sie eine Datentabelle als Member der **Tables** -Auflistung eines **DataSets**hinzugefügt haben, Sie nicht zur **Auflistung** von Tabellen eines beliebigen anderen **DataSets**hinzufügen können.  
  
 Wenn Sie erstmalig eine **Daten**Tabelle erstellen, hat Sie kein Schema (d. h. eine Struktur). Um das Schema der Tabelle zu definieren, müssen Sie-Objekte erstellen und <xref:System.Data.DataColumn> der **Columns** -Auflistung der Tabelle hinzufügen. Sie können auch eine Primärschlüssel Spalte für die Tabelle definieren und Einschränkungs **Objekte erstellen** und der **Einschränkungs** Auflistung der Tabelle hinzufügen. Nachdem Sie das Schema für eine **Daten**Tabelle definiert haben, können Sie der Tabelle Daten Zeilen hinzufügen, indem Sie der **Rows** -Auflistung der Tabelle **DataRow** -Objekte hinzufügen.  
  
 Sie müssen keinen Wert für die- <xref:System.Data.DataTable.TableName%2A> Eigenschaft angeben, wenn Sie eine **Daten**Tabelle erstellen. Sie können die Eigenschaft zu einem anderen Zeitpunkt angeben, oder Sie können Sie leer lassen. Wenn Sie jedoch eine Tabelle ohne **TableName** -Wert zu einem **DataSet**hinzufügen, erhält die Tabelle einen inkrementellen Standardnamen der Tabelle*N*, beginnend mit "Table" für Table0.  
  
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
- ["DataTables"](datatables.md)
- [Auffüllen eines "DataSets" durch einen "DataAdapter"](../populating-a-dataset-from-a-dataadapter.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
