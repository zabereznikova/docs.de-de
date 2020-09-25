---
title: "\"DataTable\" und \"DataColumn\"-Zuordnungen mit \"DataAdapter\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: b979431836b55b23ac9ba6ec4535f33765dce555
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177734"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>"DataTable" und "DataColumn"-Zuordnungen mit "DataAdapter"

Ein **DataAdapter** enthält eine Auflistung von 0 (null) oder mehr <xref:System.Data.Common.DataTableMapping> Objekten in der **TableMappings** -Eigenschaft. Eine **DataTableMapping** bietet eine Master Zuordnung zwischen den Daten, die von einer Abfrage an eine Datenquelle zurückgegeben werden, und einem <xref:System.Data.DataTable> . Der **DataTableMapping** -Name kann anstelle des Namen der **Daten** Tabelle an die **Fill** -Methode von **DataAdapter**weitergegeben werden. Im folgenden Beispiel wird eine **DataTableMapping** mit dem Namen " **AuthorsMapping** " für die Tabelle " **Authors** " erstellt.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Eine **DataTableMapping** -Funktion ermöglicht es Ihnen, Spaltennamen in einer **Daten** Tabelle zu verwenden, die sich von denen in der Datenbank unterscheiden. Der **DataAdapter** verwendet die Zuordnung, um die Spalten zu vergleichen, wenn die Tabelle aktualisiert wird.  
  
 Wenn Sie beim Aufrufen der **Fill** -oder **Update** -Methode von **DataAdapter**keinen **TableName** -oder **DataTableMapping** -Namen angeben, sucht der **DataAdapter** nach einem **DataTableMapping** mit dem Namen "Table". Wenn dieses **DataTableMapping** -Element nicht vorhanden ist, lautet der **TableName** der **Daten** Tabelle "Table". Sie können eine **DataTableMapping** -Standard Zuordnung angeben, indem Sie eine **DataTableMapping** mit dem Namen "Table" erstellen.  
  
 Im folgenden Codebeispiel wird eine **DataTableMapping** (aus dem- <xref:System.Data.Common> Namespace) erstellt und als Standard Zuordnung für den angegebenen **DataAdapter** festgelegt, indem Sie "Table" benannt wird. Im Beispiel werden dann die Spalten aus der ersten Tabelle im Abfrageergebnis (die **Customers** -Tabelle der **Northwind** -Datenbank) einem Satz benutzerfreundlicher Namen in der **Northwind-Kunden** Tabelle in zugeordnet <xref:System.Data.DataSet> . Für Spalten, die nicht zugeordnet werden, wird der Name der Spalte in der Datenquelle verwendet.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 In komplexeren Situationen können Sie festlegen, dass der gleiche **DataAdapter** das Laden verschiedener Tabellen mit unterschiedlichen Zuordnungen unterstützt. Fügen Sie zu diesem Zweck einfach weitere **DataTableMapping** -Objekte hinzu.  
  
 Wenn die **Fill** -Methode an eine Instanz eines **DataSets** und einen **DataTableMapping** -Namen übertragen wird, wird Sie verwendet, wenn eine Zuordnung mit diesem Namen vorhanden ist. Andernfalls wird eine **Daten** Tabelle mit diesem Namen verwendet.  
  
 In den folgenden Beispielen wird eine **DataTableMapping** mit dem Namen **Customers** und dem Namen der **Daten** Tabelle **BizTalkSchema**erstellt. Im Beispiel werden dann die von der SELECT-Anweisung zurückgegebenen Zeilen der **BizTalkSchema** - **Daten**Tabelle zugeordnet.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> Wenn für eine Spaltenzuordnung kein Quellspaltenname bzw. für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, werden automatisch Standardnamen generiert. Wenn für eine Spalten Zuordnung keine Quell Spalte bereitgestellt wird, erhält die Spalten Zuordnung den inkrementellen Standardnamen **sourcecolnumn** *N,* beginnend mit **SourceColumn1**. Wenn für eine Tabellen Zuordnung kein Quell Tabellenname angegeben wird, erhält die Tabellen Zuordnung einen inkrementellen Standardnamen für **SourceTable** *N*, beginnend mit **SourceTable1**.  
  
> [!NOTE]
> Es wird empfohlen, dass Sie die Benennungs Konvention von **sourcecolnumn** *N* für eine Spalten Zuordnung oder **SourceTable** *n* für eine Tabellen Zuordnung vermeiden, da der von Ihnen bereitgestellte Name möglicherweise mit einem vorhandenen Standard Spalten-Zuordnungsnamen in der **ColumnMappingCollection** oder dem Tabellen Zuordnungsnamen in der **DataTableMappingCollection**in Konflikt steht. Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
## <a name="handling-multiple-result-sets"></a>Umgang mit mehreren Resultsets  

 Wenn der **SelectCommand** mehrere Tabellen zurückgibt, generiert **Fill** automatisch Tabellennamen mit inkrementellen Werten für die Tabellen im **DataSet**, beginnend mit dem angegebenen Tabellennamen und fortsetzen in der Form **TableName** *N*, beginnend mit **TableName1**. Sie können Tabellen Zuordnungen verwenden, um den automatisch generierten Tabellennamen einem Namen zuzuordnen, den Sie für die Tabelle im **DataSet**angeben möchten. Geben Sie beispielsweise für einen **SelectCommand** , der zwei Tabellen, **Kunden** und **Bestellungen**zurückgibt, den folgenden **Auffüll**Befehl aus.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 Im **DataSet**werden zwei Tabellen erstellt: " **Customers** " und " **Customers1**". Sie können Tabellen **Zuordnungen** verwenden, um sicherzustellen, dass die zweite Tabelle den Namen Orders anstelle von **Customers1**hat. Ordnen Sie zu diesem Zweck die Quell Tabelle von **Customers1** den **DataSet** -Tabellen **Bestellungen**zu, wie im folgenden Beispiel gezeigt.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>Weitere Informationen

- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
