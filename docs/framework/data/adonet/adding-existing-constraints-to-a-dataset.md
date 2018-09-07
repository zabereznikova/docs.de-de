---
title: Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064201"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"
Die **füllen** -Methode der der **DataAdapter** füllt eine <xref:System.Data.DataSet> nur mit Spalten und Zeilen aus einer Datenquelle jedoch Einschränkungen sind häufig festgelegt, indem die Datenquelle, die **Füllen** Methode fügt diese Schemainformationen nicht der **DataSet** standardmäßig. Zum Auffüllen einer **DataSet** mit vorhandenen primary Key-Einschränkungsinformationen aus einer Datenquelle können Sie entweder Aufruf der **FillSchema** -Methode der der **DataAdapter**, oder legen Sie die **MissingSchemaAction** Eigenschaft der **DataAdapter** zu **AddWithKey** vor dem Aufruf **füllen**. Dadurch wird sichergestellt, dass die Einschränkungen in der **DataSet** widerzuspiegeln, die in der Datenquelle. Foreign Key-Einschränkungsinformationen nicht enthalten ist, und muss erstellt werden, siehe explizit [DataTable-Einschränkungen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Schemainformationen Hinzufügen einer **DataSet** vor dem Füllen mit Daten stellt sicher, dass die primary Key-Einschränkungen enthalten sind die <xref:System.Data.DataTable> Objekte in der **DataSet**. Als Ergebnis bei weiteren Aufrufen zum Füllen der **DataSet** vorgenommen werden, wird die primäre Schlüsselspalteninformationen wird verwendet, um neue Zeilen aus der Datenquelle mit den aktuellen Zeilen in jeder entsprechen **DataTable**, und aktuellen Daten in die Tabellen mit Daten aus der Datenquelle überschrieben wird. Ohne die Schemainformationen werden die neuen Zeilen aus der Datenquelle angefügt, um die **DataSet**, wodurch doppelte Zeilen.  
  
> [!NOTE]
>  Wenn eine Spalte in einer Datenquelle als automatisch erhöht, identifiziert wird die **FillSchema** -Methode, oder die **füllen** -Methode mit einer **MissingSchemaAction** von  **AddWithKey**, erstellt eine **DataColumn** mit einer **AutoIncrement** -Eigenschaftensatz auf `true`. Allerdings müssen Sie zum Festlegen der **AutoIncrementStep** und **AutoIncrementSeed** Werte selbst. Weitere Informationen zu Spalten automatisch erhöht, finden Sie unter [Erstellen von AutoIncrement-Spalten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Mithilfe von **FillSchema** oder einer Einstellung der **MissingSchemaAction** zu **AddWithKey** erfordert zusätzliche Verarbeitungsschritte an der Datenquelle um Primärschlüsselspalte Informationen zu ermitteln. Diese zusätzlichen Verarbeitungsschritte können zu einem Leistungsabfall führen. Wenn Sie die Primärschlüsselinformationen zur Entwurfszeit kennen, empfiehlt es sich, zum Erzielen einer optimalen Leistung die Primärschlüsselspalte(n) explizit in der richtigen Reihenfolge anzugeben. Informationen zum expliziten Festlegen von Primärschlüsselinformationen für eine Tabelle finden Sie unter [Definieren von Primärschlüsseln](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Im folgenden Codebeispiel wird veranschaulicht, das Hinzufügen von Schemainformationen einer **DataSet** mit **FillSchema**.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 Im folgenden Codebeispiel wird veranschaulicht, das Hinzufügen von Schemainformationen einer **DataSet** mithilfe der **MissingSchemaAction.AddWithKey** Eigenschaft der **füllen** Methode.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>Umgang mit mehreren Resultsets  
 Wenn die **DataAdapter** erkennt mehrere Resultsets aus der **SelectCommand**, erstellt es mehrere Tabellen in der **DataSet**. Die Tabellen erhält einen standardmäßig nullbasierte Namen **Tabelle** *N*, beginnend mit **Tabelle** anstelle von "Table0". Wenn ein Tabellenname als Argument übergeben wird die **FillSchema** -Methode, die Tabellen erhält einen nullbasierten Namen **TableName** *N*, beginnend mit **TableName** anstelle von "TableName0".  
  
> [!NOTE]
>  Wenn die **FillSchema** Methode der **OleDbDataAdapter** -Objekts aufgerufen wird, für einen Befehl aus, die mehrere Resultsets zurückgibt, wird nur die Schemainformationen aus dem ersten Resultset zurückgegeben. Wenn Schemainformationen für mehrere Resultsets zurückgeben Sätze unter Verwendung der **OleDbDataAdapter**, es wird empfohlen, die Sie angeben, ein **MissingSchemaAction** von **AddWithKey** und rufen Sie die Schemainformationen beim Aufruf der **füllen** Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
