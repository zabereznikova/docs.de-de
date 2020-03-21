---
title: "\"DataTable\" und \"DataColumn\"-Zuordnungen mit \"DataAdapter\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151558"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>"DataTable" und "DataColumn"-Zuordnungen mit "DataAdapter"
Ein **DataAdapter** enthält eine Auflistung <xref:System.Data.Common.DataTableMapping> von null oder mehr Objekten in seiner **TableMappings-Eigenschaft.** Ein **DataTableMapping** stellt eine Masterzuordnung zwischen den Daten, die <xref:System.Data.DataTable>von einer Abfrage für eine Datenquelle zurückgegeben werden, und einer . Der **Name DataTableMapping** kann anstelle des **DataTable-Namens** an die **Fill-Methode** des **DataAdapter**übergeben werden. Im folgenden Beispiel wird ein **DataTableMapping** mit dem Namen **AuthorsMapping** für die **Tabelle Authors** erstellt.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Mit **DataTableMapping** können Sie Spaltennamen in einer **DataTable** verwenden, die sich von denen in der Datenbank unterscheiden. Der **DataAdapter** verwendet die Zuordnung, um die Spalten zu entsprechen, wenn die Tabelle aktualisiert wird.  
  
 Wenn Sie beim Aufrufen der **Fill-** oder **Update-Methode** des **DataAdapter**keinen **TableName** oder einen **DataTableMapping-Namen** angeben, sucht der **DataAdapter** nach einem **DataTableMapping** mit dem Namen "Table". Wenn **dataTableMapping** nicht vorhanden ist, lautet der **TableName** der **DataTable** "Tabelle". Sie können eine **Standarddatentabelle-Zuordnung** angeben, indem Sie ein **DataTableMapping** mit dem Namen "Table" erstellen.  
  
 Im folgenden Codebeispiel wird ein **DataTableMapping** (aus dem <xref:System.Data.Common> Namespace) erstellt und zur Standardzuordnung für den angegebenen **DataAdapter** gemacht, indem es "Table" genannt wird. Im Beispiel werden dann die Spalten aus der ersten Tabelle im Abfrageergebnis (der **Tabelle Customers** der **Northwind-Datenbank)** einer Reihe benutzerfreundlicherer Namen in der **Tabelle Northwind Customers** im <xref:System.Data.DataSet>zugeordnet. Für Spalten, die nicht zugeordnet werden, wird der Name der Spalte in der Datenquelle verwendet.  
  
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
  
 In fortgeschritteneren Situationen können Sie entscheiden, dass derselbe **DataAdapter** das Laden verschiedener Tabellen mit unterschiedlichen Zuordnungen unterstützen soll. Fügen Sie dazu einfach zusätzliche **DataTableMapping-Objekte** hinzu.  
  
 Wenn die **Fill-Methode** eine Instanz eines **DataSet** und eines **DataTableMapping-Namens** übergeben wird, wird eine Zuordnung mit diesem Namen verwendet. Andernfalls wird eine **DataTable** mit diesem Namen verwendet.  
  
 In den folgenden Beispielen wird ein **DataTableMapping** mit dem Namen **Customers** und dem **DataTable-Namen** **BizTalkSchema**erstellt. Im Beispiel werden dann die von der SELECT-Anweisung zurückgegebenen Zeilen der **BizTalkSchema** **DataTable**zugeordnet.  
  
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
> Wenn für eine Spaltenzuordnung kein Quellspaltenname bzw. für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, werden automatisch Standardnamen generiert. Wenn keine Quellspalte für eine Spaltenzuordnung angegeben wird, erhält die Spaltenzuordnung einen inkrementellen Standardnamen von **SourceColumn** *N,* beginnend mit **SourceColumn1**. Wenn für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, wird der Tabellenzuordnung ein inkrementeller Standardname von **SourceTable** *N*, beginnend mit **SourceTable1**, angezeigt.  
  
> [!NOTE]
> Es wird empfohlen, die Namenskonvention von **SourceColumn** *N* für eine Spaltenzuordnung oder **SourceTable** *N* für eine Tabellenzuordnung zu vermeiden, da der von Ihnen gelieferte Name möglicherweise mit einem vorhandenen Standardspaltenzuordnungsnamen in der **ColumnMappingCollection** oder dem Tabellenzuordnungsnamen in der **DataTableMappingCollection**in Konflikt steht. Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
## <a name="handling-multiple-result-sets"></a>Umgang mit mehreren Resultsets  
 Wenn Ihr **SelectCommand** mehrere Tabellen zurückgibt, generiert **Fill** automatisch Tabellennamen mit inkrementellen Werten für die Tabellen im **DataSet**, beginnend mit dem angegebenen Tabellennamen und weiter in der Form **TableName** *N*, beginnend mit **TableName1**. Sie können Tabellenzuordnungen verwenden, um den automatisch generierten Tabellennamen einem Namen zuzuordnen, den Sie für die Tabelle im **DataSet**angegeben haben sollen. Geben Sie z. B. für einen **SelectCommand,** der zwei Tabellen, **Kunden** und **Aufträge,** zurückgibt, den folgenden Aufruf von **Fill**aus.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 Im **DataSet**werden zwei Tabellen erstellt: **Kunden** und **Kunden1**. Sie können Tabellenzuordnungen verwenden, um sicherzustellen, dass die zweite Tabelle den Namen **Orders** anstelle von **Customers1**trägt. Ordnen Sie dazu die Quelltabelle von **Customers1** der **DataSet-Tabelle** **Orders**zu, wie im folgenden Beispiel gezeigt.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>Weitere Informationen

- [DataAdapters und DataReaders](dataadapters-and-datareaders.md)
- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
