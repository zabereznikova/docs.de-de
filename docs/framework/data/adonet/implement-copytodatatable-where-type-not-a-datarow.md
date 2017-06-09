---
title: "Vorgehensweise: Implementieren von CopyToDataTable&lt;T&gt; mit einem anderen generischen Typ T als DataRow | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Implementieren von CopyToDataTable&lt;T&gt; mit einem anderen generischen Typ T als DataRow
Das <xref:System.Data.DataTable>\-Objekt wird oft für die Datenbindung verwendet.  Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>\-Methode kopiert die Ergebnisse einer Abfrage in eine <xref:System.Data.DataTable>, die dann für die Datenbindung verwendet werden kann.  Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>\-Methoden arbeiten allerdings nur mit einer <xref:System.Collections.Generic.IEnumerable%601>\-Quelle, bei der der generische Parameter `T` den Typ <xref:System.Data.DataRow> aufweist.  Obwohl dies hilfreich ist, können Tabellen dabei nicht aus einer Sequenz von Skalartypen, aus Abfragen, die anonyme Typen darstellen oder aus Abfragen, die Tabellenjoins durchführen, erstellt werden.  
  
 In diesem Thema wird beschrieben, wie zwei benutzerdefinierte `CopyToDataTable<T>`\-Erweiterungsmethoden implementiert werden, die einen generischen Parameter `T` annehmen, der einen anderen Typ als <xref:System.Data.DataRow> aufweist.  Die Logik zum Erstellen einer <xref:System.Data.DataTable> aus einer <xref:System.Collections.Generic.IEnumerable%601>\-Quelle ist in der `ObjectShredder<T>`\-Klasse enthalten, die wiederum von zwei überladenen `CopyToDataTable<T>`\-Erweiterungsmethoden umschlossen wird.  Die `Shred`\-Methode der `ObjectShredder<T>`\-Klasse gibt die gefüllte <xref:System.Data.DataTable> zurück und nimmt drei Eingabeparameter an: eine <xref:System.Collections.Generic.IEnumerable%601>\-Quelle, eine <xref:System.Data.DataTable> und eine <xref:System.Data.LoadOption>\-Enumeration.  Das anfängliche Schema der zurückgegebenen <xref:System.Data.DataTable> basiert auf dem Schema des Typs `T`.  Wenn eine vorhandene Tabelle als Eingabe bereitgestellt wird, muss deren Schema mit dem Schema des Typs `T` übereinstimmen.  Jede öffentliche Eigenschaft und jedes Feld des Typs `T` wird in eine <xref:System.Data.DataColumn> in der zurückgegebenen Tabelle konvertiert.  Wenn die Quellsequenz einen von `T` abgeleiteten Typ enthält, wird das zurückgegebene Tabellenschema um zusätzliche öffentliche Eigeschaften bzw. Felder erweitert.  
  
 Beispiele für die Verwendung der benutzerdefinierten `CopyToDataTable<T>`\-Methoden finden Sie unter [Erstellen einer 'DataTable' aus einer Abfrage](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).  
  
### So implementieren Sie die benutzerdefinierte CopyToDataTable\<T\>\-Methode in Ihrer Anwendung  
  
1.  Implementieren Sie die `ObjectShredder<T>`\-Klasse, um eine <xref:System.Data.DataTable> aus einer <xref:System.Collections.Generic.IEnumerable%601>\-Quelle zu erstellen:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  
  
2.  Implementieren Sie die benutzerdefinierten `CopyToDataTable<T>`\-Erweiterungsmethoden in einer Klasse:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3.  Fügen Sie die `ObjectShredder<T>`\-Klasse und die `CopyToDataTable<T>`\-Erweiterungsmethoden Ihrer Anwendung hinzu.  
  
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
  
4.  ```c#  
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
  
## Siehe auch  
 [Erstellen einer 'DataTable' aus einer Abfrage](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)   
 [Informationen zum Programmieren](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)