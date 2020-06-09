---
title: 'Vorgehensweise: Implementieren von CopyToDataTable<T> mit einem anderen generischen Typ „T“ als DataRow'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: a1427747d03f01e52f1ee7ad1fc11d47d310edbe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590604"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a>Vorgehensweise: Implementieren von CopyToDataTable\<T> mit einem anderen generischen Typ „T“ als DataRow
Das <xref:System.Data.DataTable>-Objekt wird oft für die Datenbindung verwendet. Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode kopiert die Ergebnisse einer Abfrage in eine <xref:System.Data.DataTable>, die dann für die Datenbindung verwendet werden kann. Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methoden arbeiten allerdings nur mit einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle, bei der der generische Parameter `T` den Typ <xref:System.Data.DataRow> aufweist. Obwohl dies hilfreich ist, können Tabellen dabei nicht aus einer Sequenz von Skalartypen, aus Abfragen, die anonyme Typen darstellen oder aus Abfragen, die Tabellenjoins durchführen, erstellt werden.  
  
 In diesem Thema wird beschrieben, wie zwei benutzerdefinierte `CopyToDataTable<T>`-Erweiterungsmethoden implementiert werden, die einen generischen Parameter `T` annehmen, der einen anderen Typ als <xref:System.Data.DataRow> aufweist. Die Logik zum Erstellen einer <xref:System.Data.DataTable> aus einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle ist in der `ObjectShredder<T>`-Klasse enthalten, die wiederum von zwei überladenen `CopyToDataTable<T>`-Erweiterungsmethoden umschlossen wird. Die `Shred`-Methode der `ObjectShredder<T>`-Klasse gibt die gefüllte <xref:System.Data.DataTable> zurück und nimmt drei Eingabeparameter an: eine <xref:System.Collections.Generic.IEnumerable%601>-Quelle, eine <xref:System.Data.DataTable> und eine <xref:System.Data.LoadOption>-Enumeration. Das anfängliche Schema der zurückgegebenen <xref:System.Data.DataTable> basiert auf dem Schema des Typs `T`. Wenn eine vorhandene Tabelle als Eingabe bereitgestellt wird, muss deren Schema mit dem Schema des Typs `T` übereinstimmen. Jede öffentliche Eigenschaft und jedes Feld des Typs `T` wird in eine <xref:System.Data.DataColumn> in der zurückgegebenen Tabelle konvertiert. Wenn die Quellsequenz einen von `T` abgeleiteten Typ enthält, wird das zurückgegebene Tabellenschema um zusätzliche öffentliche Eigeschaften bzw. Felder erweitert.  
  
 Beispiele für die Verwendung der benutzerdefinierten `CopyToDataTable<T>`-Methoden finden Sie unter [Creating a DataTable From a Query (Erstellen einer DataTable aus einer Abfrage)](creating-a-datatable-from-a-query-linq-to-dataset.md).  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a>So implementieren Sie die benutzerdefinierten copydedatbare- \<T> Methoden in der Anwendung  
  
1. Implementieren Sie die `ObjectShredder<T>`-Klasse, um eine <xref:System.Data.DataTable> aus einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle zu erstellen:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    Im vorangehenden Beispiel wird davon ausgegangen, dass die Eigenschaften und Felder der keine auf NULL festleg `DataColumn` baren Werttypen sind. Verwenden Sie den folgenden Code, um Eigenschaften und Felder mit auf NULL festleg baren Werttypen zu behandeln:

    ```csharp
    // Nullable-aware code for properties.
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);

    // Nullable-aware code for fields.
    DataColumn dc = table.Columns.Contains(f.Name) ? table.Columns[f.Name] : table.Columns.Add(f.Name, Nullable.GetUnderlyingType(f.FieldType) ?? f.FieldType);
    ```

2. Implementieren Sie die benutzerdefinierten `CopyToDataTable<T>`-Erweiterungsmethoden in einer Klasse:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. Fügen Sie die `ObjectShredder<T>`-Klasse und die `CopyToDataTable<T>`-Erweiterungsmethoden Ihrer Anwendung hinzu.  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer DataTable aus einer Abfrage](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [Programmierhandbuch](programming-guide-linq-to-dataset.md)
