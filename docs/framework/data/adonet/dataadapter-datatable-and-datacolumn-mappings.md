---
title: "\"DataTable\" und \"DataColumn\"-Zuordnungen mit \"DataAdapter\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 9f33ae085bef2b611d1ce95bed1b26f9101a10b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505241"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>"DataTable" und "DataColumn"-Zuordnungen mit "DataAdapter"
Ein **DataAdapter** enthält eine Auflistung von NULL oder mehr <xref:System.Data.Common.DataTableMapping> Objekte in der **TableMappings** Eigenschaft. Ein **DataTableMapping** stellt eine masterzuordnung zwischen den Daten, die von einer Abfrage für eine Datenquelle zurückgegeben und ein <xref:System.Data.DataTable>. Die **DataTableMapping** Namen übergeben werden kann, anstelle von der **DataTable** -Namens an die **füllen** -Methode der der **DataAdapter**. Das folgende Beispiel erstellt eine **DataTableMapping** mit dem Namen **AuthorsMapping** für die **Autoren** Tabelle.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Ein **DataTableMapping** können Sie mit der Spaltennamen in einer **DataTable** , die sich von denen in der Datenbank sind. Die **DataAdapter** mithilfe der Zuordnung der Spalten entsprechen, wenn die Tabelle aktualisiert wird.  
  
 Wenn Sie nicht angeben eine **TableName** oder ein **DataTableMapping** Namen beim Aufruf der **füllen** oder **Update** -Methode der der  **DataAdapter**, **DataAdapter** sucht nach einem **DataTableMapping** mit dem Namen "Table". Wenn das **DataTableMapping** ist nicht vorhanden, die **TableName** von der **DataTable** "Table". Sie können einen Standardwert angeben **DataTableMapping** durch das Erstellen einer **DataTableMapping** mit dem Namen "Table".  
  
 Das folgende Codebeispiel erstellt eine **DataTableMapping** (aus der <xref:System.Data.Common> Namespace) und erleichtert die standardzuordnung für den angegebenen **DataAdapter** durch benennen "Table". Das Beispiel ordnet dann die Spalten aus der ersten Tabelle im Ergebnis Abfrage (die **Kunden** Tabelle mit den **Northwind** Datenbank) auf eine Gruppe von benutzerfreundlicheren Namen in der **Northwind-Kunden**  -Tabelle in der <xref:System.Data.DataSet>. Für Spalten, die nicht zugeordnet werden, wird der Name der Spalte in der Datenquelle verwendet.  
  
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
  
 In komplexeren Situationen, Sie können festlegen, dass Sie dasselbe **DataAdapter** um Laden verschiedener Tabellen mit verschiedenen Zuordnungen zu unterstützen. Zu diesem Zweck fügen Sie einfach zusätzliche **DataTableMapping** Objekte.  
  
 Wenn die **füllen** -Methode übergeben eine Instanz von eine **DataSet** und ein **DataTableMapping** Namen, sofern eine Zuordnung mit diesem Namen vorhanden ist, andernfalls eine  **DataTable** , wird der Name wird verwendet.  
  
 Erstellen Sie in den folgenden Beispielen ein **DataTableMapping** mit dem Namen **Kunden** und **DataTable** Name des **BizTalkSchema**. Das Beispiel ordnet dann die von der SELECT-Anweisung zurückgegebenen Zeilen der **BizTalkSchema** **DataTable**.  
  
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
>  Wenn für eine Spaltenzuordnung kein Quellspaltenname bzw. für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, werden automatisch Standardnamen generiert. Wenn keine Spalte "Quelle" für eine spaltenzuordnung angegeben ist, erhält die spaltenzuordnung einen Standardnamen der **SourceColumn** *N,* ab **SourceColumn1**. Wenn für eine tabellenzuordnung kein Quelltabellenname angegeben wird, erhält die tabellenzuordnung einen Standardnamen der **SourceTable** *N*, beginnend mit **SourceTable1**.  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie vermeiden, dass die Namenskonvention des **SourceColumn** *N* für eine spaltenzuordnung, oder **SourceTable** *N* für eine Tabelle Zuordnung, die der Namen, die Sie angeben, ein Konflikt mit einer vorhandenen Zuordnung Standardspaltennamen in kann die **ColumnMappingCollection** oder Zuordnung Tabellennamen in der **DataTableMappingCollection** . Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
## <a name="handling-multiple-result-sets"></a>Umgang mit mehreren Resultsets  
 Wenn Ihre **SelectCommand** mehrere Tabellen gibt **füllen** generiert automatisch Tabellennamen mit inkrementellen Werten für die Tabellen in der **DataSet**, beginnend mit der Tabellennamen und weiter auf im Formular angegeben habe **TableName** *N*, beginnend mit **TableName1**. Sie können mit tabellenzuordnungen können Sie den automatisch generierten Tabellennamen einem Namen zuordnen für die Tabelle im angegebenen soll die **DataSet**. Z. B. für eine **SelectCommand** , die zwei Tabellen zurückgibt **Kunden** und **Bestellungen**, geben Sie den folgenden Aufruf **füllen**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Werden zwei Tabellen erstellt, der **DataSet**: **Kunden** und **Customers1**. Sie können die tabellenzuordnungen verwenden, um sicherzustellen, dass die zweite Tabelle den Namen **Bestellungen** anstelle von **Customers1**. Zu diesem Zweck ordnen Sie die Quelltabelle **Customers1** auf die **DataSet** Tabelle **Bestellungen**, wie im folgenden Beispiel gezeigt.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
